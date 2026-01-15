---title: Knihovny v Praze
description: Knihovny 
Stackslug: libraries
date: 2026-01-15 00:00:00+0000
#image: cover.jpg
tags:
    - Library review
weight: 1
---

Ahoj,

nějakou zvláštní náhodou jsem si dal ambiciózní úkol na tento rok - Navštívit, co nejvíce knihoven v Praze. Tohle je první příspěvek v sérii Library Review, kde postupně projdu, co nejvíce institucemi. Ideál je, že o každé napišu nějaký krátký text a postupně si tak projdeme celou Prahu. 

Jak ale získat knihovny? Národní knihovna má databalíček (ADR - 	Centrální adresář knihoven a informačních institucí v ČR). Ten je přístupný v [otevřených datech](https://www.nkp.cz/o-knihovne/odborne-cinnosti/otevrena-data). To jsem samozřejmě nepoužil, ja si to poctivě nascrapoval pomocí tohodle kódu:

```
import asyncio
from playwright.async_api import async_playwright

async def main():
    with open("libraries.txt", "a", encoding="utf-8") as file:
        try:
            async with async_playwright() as pw:
                browser = await pw.chromium.launch(headless=False)
                context = await browser.new_context(
                    user_agent="Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/96.0.4664.45 Safari/537.36"
                )
                page = await context.new_page()

                for i in range(1, 1031):
                    print(f"Processing {i}")
                    set_entry = f"{i:06d}"

                    url = f"https://aleph.nkp.cz/F/2KUPKEFI2YJBY3KA4TLPB1H8QJQ5NQE59481CD8FUYPKM1SV7U-01633?func=full-set-set&set_number=189908&set_entry={set_entry}&format=999" # Tahle URL po nějaké době přestane fungovat (viz ten "token" mezi /F/ a ?), takže je potřeba ji znovu navštívit a zkopírovat. Když by to spadlo, tak kód appenduje, takže je možný prostě na změnit range v tom for i in range
                    await page.goto(url, timeout=120_000)
                    await page.wait_for_timeout(2000)

                    table_rows = await page.query_selector_all('//td[@class="td1"]')
                    closed = await table_rows[1].inner_text()
                    if "ZRUŠENA" in closed or "ZRUŠENÁ" in closed:
                        continue

                    name_tr = await page.query_selector('//tr[@id="Název instituce"]')
                    name = ""
                    if name_tr:
                        tds = await name_tr.query_selector_all("td")
                        if len(tds) > 1:
                            name = (await tds[1].inner_text()).strip()

                    address_tr = await page.query_selector('//tr[@id="Adresa"]')
                    address = ""
                    if address_tr:
                        tds = await address_tr.query_selector_all("td")
                        if len(tds) > 1:
                            address = (await tds[1].inner_text()).strip()

                    

                    print(f"{name}: {address}")
                    file.write(f"{name}: {address}\n")
                    file.flush()

                await browser.close()

        except Exception as e:
            print("Error:", e)

if __name__ == '__main__':
    asyncio.run(main())
```

To mi udělalo soubor, který jsem pomocí dalšího kódu změnil v následující mapku:
```
import folium
import re

def dms_to_decimal(d, m, s, direction):
    dec = float(d) + float(m) / 60 + float(s) / 3600
    if direction in ("S", "W"):
        dec = -dec
    return dec

pattern = re.compile(
    r'(\d+)°(\d+)’([\d.]+)"([NS]),\s*(\d+)°(\d+)’([\d.]+)"([EW])'
)

m = folium.Map(location=[50.08, 14.42], zoom_start=12)

marker_count = 0
current_name = None

with open("links.txt", encoding="utf-8") as f:
    for line in f:
        line = line.strip()
        if not line:
            continue

        if ":" in line and "GPS" not in line:
            current_name = line.split(":", 1)[0].strip()
            continue

        if "GPS" in line and current_name:
            match = pattern.search(line)
            if match:
                lat = dms_to_decimal(match.group(1), match.group(2), match.group(3), match.group(4))
                lon = dms_to_decimal(match.group(5), match.group(6), match.group(7), match.group(8))

                folium.Marker(
                    location=[lat, lon],
                    tooltip=current_name
                ).add_to(m)

                marker_count += 1
                current_name = None

print(marker_count)
m.save("map.html")
```

Používám k tomu folium, který jsem náhodou našel a od tý doby ho miluju. Vytváření map v pythonu nebylo nikdy jednodušší (než najdu ještě něco jednoduššího)

Viz mapka!!!
<iframe
  src="/leaflet-map/map.html"
  width="70%"
  height="600"
  style="border:0;"
  loading="lazy">
</iframe>

Teď už je postupně jen prochodit. Určitě některý budou zavřený (třeba archiv a knihovna Poštovního muzea, které je teď nově pod Technickým muzeem, tak je do skoro dubna zavřeno.)

(Jurnal entry za listopad až prosinec dodám, co nejdříve. V listopadu jsem skoro vůbec neprogramoval, v prosinci maličko. Tak nebylo moc o čem psát. Ale o tom později.)