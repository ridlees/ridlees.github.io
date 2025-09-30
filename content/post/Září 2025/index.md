---title: Září 2025
description: Zápisek za měsíc 
Stackslug: zari2025
date: 2025-09-30 00:00:00+0000
#image: cover.jpg
tags:
    - Journal Entry
weight: 1
---

První řádky tohoto zápisu píšu v tramvaji číslo 10. Je v něčem strašně zvláštní pracovat v tramvaji, ale zároveň i to je vlak. Tenhle měsíc jsem dvakrát jel vlakem - do České Třebové a pak samozřejmě zpátky. Bylo to mé první zastavení v Pardubickém kraji, už mi zbývá přespat jen v Libereckém, Zlínském (v kterém jsem nikdy nebyl) a v Olomouckém. 

---------------

První programovací jednohubka byla jednoduché využití Google TTS (text to speech) pro můj Kramerius stahovač. V malém skriptu TTS (který přijímá právě jeden systémový argument - odkaz na soubor v txt) se ukrývá jednoduchý kód, a vychází z něj né úplně nejpříjemnější audio kniha. Původně jsem to dělal pro online hackathon (napsat ten skript bylo na 5 minut), kdy jsem chtěl udělat celou službu - dej odkaz knihy, dostaň audionahrávku, což je třeba zajímavé pro pohádky a nevidomé. Ale nevymyslel jsem jak udělat UI, v kterém se nevidomý vyzná, takže jsem to dal k ledu.

---------------

Druhá programovaná věc je další scrapper nájemních dat. Již je získávám ze 3 zdrojů (do budoucna chci pokrýt, co nejvíce to půjde). Bude se to zobrazovat v tom UI napsáném v Streamlit, ale ještě jsem pro to neudělal chlívečky. To UI budu muset trochu překopat, protože načítání hlavní databáze je pomalé (2 vteřiny), tak to trochu upravím, aby to bylo lehčí. Kdy na to najdu čas, ještě nevím. 

---------------

Rozepsal jsem jednoduchý UI nad one-way (jednosměrným) SMS senderem od Twilia (chtěl bych nějakého jejich konkurenta, pro jednoho jsem pracoval, ale nemají tak dobrý pricing a já nejsem nejbohatší čávo v téhle tramvaji). Je to jednoduchý input, kam dáte zprávu a ono to pošle předem definovanému listu (odsuď to už nepíšu v tramvaji) příjemců. (Tuto pasáž píši v Tečce) UI se zdá, že funguje, ještě musím otestovat Twilio a obalit to keycloackem.

---------------

Čtu [Own this!](https://www.versobooks.com/products/2839-own-this?srsltid=AfmBOoqOWTLX4zhec-Z3BaPJcygDUaoZFFyP0nGgVrNEzmJyV08-37zT) O družstevnictví a odborech, do toho se mi míchají texty 37signals, přemýšlím tak o platformách sdružující malé podniky a pro ně poskytování software, ale i o družstvech v péči (družstevní psychoterapeutství??), což jsou všechno způsoby jak udržet peníze v lokální komunitě. Vzpomínám na takový ten obrázek na Facebooku, kde byla vývěsní cedule, co říkala, že nákupem zde přispíváte malé holčičce na kroužky. (Na pozadí v Tečce hraje španělský politický rap, ale nedokážu poznat jaký.) Jedna z mých diplomek se věnuje kutilství, což je produkce pro svou konzumaci. Ještě nevím jak to popíšu (bojím se, že budu hodně koukat prismatem DIY (Do it yourself), kdežto já potřebuju zkoumat DIT (do it together). Nedokážu říci moc o ekonomice, ale můžu říci to, že bych byl rád, kdyby byla víc lokální (Zrovna přišla pizza, co si tu nějací anglicky mluvící lidé objednali). 

---------------

V příštím měsíci to vypadá, že se nerdsnipnu tiskárnou na účtenky, co mi bude tisknout úkoly z mého údolíčku - [Idea vypůjčena odsud](https://www.laurieherault.com/articles/a-thermal-receipt-printer-cured-my-procrastination). Přemýšlím, kde bude databáze pro hostování těchto úkolů, kdysi jsem hodně používal trello, ale nechci za něj platit. Možná si pro to udělám GitHub repo a využiji jejich kanban, možná najdu nějakou kanban knihovnu a napíšu si jednoduchý web... A pak jen narvání všech úkolů ze všech míst do tohoto systému. 

---------------

Byl jsem právě jednou v kině a na jednom živém nahrávání podcastu (bylo strašně dlouhý). V kině mé zraky viděly [Žít svůj život](https://www.csfd.cz/film/35196-zit-svuj-zivot/prehled/) v Ponrepu. 11. kapitola byla velmi zajímavá, ale celý snímek se mi tuze líbil. [Podcast](https://www.respekt.cz/podcast/kdyz-frankenstein-potka-babicku-a-superman-ferdu-mravence-co-patri-na-popkuluturni-kanon) mě donutil přemýšlet nad kánonem svoji popkultury. Rozhodně by tam byl film Gladiátor, který jsem jako malý viděl furt dokola. Nebo Wasabi či Drž hubu (oboje z Francie). Filmy s Belmondem mi přijdou víc artové, i když nejsou. Ale mám je rád. 

---------------

> Pro politiky je přinejmenším snazší říct: „Pojďme se bavit o algoritmech,“ než přiznat: „Lidé nemají žádnou budoucnost.“ To první umožňuje strašit a regulovat, to druhé by vyžadovalo spravedlivou transformaci k udržitelnějšímu a žitelnějšímu systému na strukturální úrovni.
-- [Marie Heřmanová](https://denikreferendum.cz/clanek/237955-za-agresi-muze-beznadej-nesocialni-site-rika-antropolozka-hermanova).
