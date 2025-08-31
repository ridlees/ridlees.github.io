---title: Srpen 2025
description: Zápisek za měsíc 
Stackslug: srpen2025
date: 2025-08-31 00:00:00+0000
#image: cover.jpg
tags:
    - Journal Entry
weight: 1
---

První zápis mého deníku - mělo to přijít mnohem dřívěji. 

Napsal jsem downloader z [Krameria](https://github.com/ridlees/Kramerius-text-scrapper). Původně to začalo jako jednovečerní projekt, kdy jsem prokrastinoval od psaní seminárky, co měla kritizovat moji bakalářku (do čehož jsem se nemohl donutit strašně dlouho, mívám silný strach, že nepíšu smysluplné věci, což tam zdůrazňuji). První verze byla playwright skript, co klikal na tlačítko. Až den potom mě napadlo kouknout se do network tabu a vidět na jakej endpoint je request. Pak jen zjištění, že to nemá origin (či jak se to jmenuje, že to prostě můžu volat odkudkoliv a máme to). Moje selhání v projektu pro Akademii věd se projevilo tím, že jsem měl napsaný kód, co mi vrací PID stránek (ID identifikátory) pro ROOT PID (identifikátor publikace). Takže jsem to jen spojil dohromady. Funguje to docela v pohodě, tak v klidu stahujme. Třeba z toho vznikne zajímavá datařina. Já bych chtěl udělat databázi kuchařek první republiky a mapovat jak se chápalo jídlo, zatím vím, že **sekaná se jedla spíše se zelím**. S jejich doporučeními na jednotlivé dny, s cenami (porovnat ceny dnes a tehdy).

---------------

Pro INN jsem opravil můj scrapper S-realit, o němž stále nemám jistotu, že plně funguje. Trochu mám strach, že nesbírá všechny data (kdyby mi někdo chtěl udělat code review, ocením). Každopádně, Vojta mi ukázal Streamlit, jehož jsem se stal milovníkem. Tak jsem v tom napsal malou appku v čistým Pythonu, co ty data jednoduše zobrazuje (protože nutit lidi z INNu ať si furt stahují csv, to analyzují v Excelu... nesmysl). 65 LOC a máte docela přehledné UI. Jediné, čeho se bojím je škálování, protože při každém kliku se celá obrazovka refreshuje, což znamená, že se spustí celý kód znova. Dá se s tím bojovat cachováním, ale už teď tam narážím na problémy, které musím vyřešit při nasazení na real železe. (Edit: Přidal jsem i view mapy nad dalším datovým zdrojem). 

---------------

Byl jsem na dvou filmech. Na Supermanovi mě nejvíce potěšila [písnička](https://www.youtube.com/watch?v=4lYIhKhgIuY), jinak film nebyl úplně tragický (I když Markéta nesouhlasila), ale bylo tam spoustu pokusů o vtip, co už mi jiskru v očích neudělají. Škoda. Druhý byl Bláznivá střela, a to jsem se chechtal jak hejkal. Parodie jsou velká část mého dospívání a zde se potkalo to dobré s tím špatným v takovém mixu, že výsledný beton udrží celý film. Jen skutečnost, že to je parodie na Kingsmen mě bavila ještě den potom. 

---------------
> If we think about technology as an existential task, it cannot be assessed within any simple moralism. The concept of existential technologies that this essay proposes would operate across vast temporal scales and elude familiar ethical categories. Rather than moving us toward a better world in any straightforward sense, they would generate alienating or turbulent changes at the limits of our comprehension. With its sustained interest in evolutionary theory and long-term prognostication and its clear-eyed understanding of agency and control sharpened by the brutal twentieth-century history of Eastern Europe, Summa Technologiae becomes a compelling lens for thinking through this idea
                              
--- [Existential Technologies by Bogna Konior with Noviki Studio, DOI 10.1162/ANTI.5CZV](https://existentialtech.antikythera.org)

---------------

Našel jsem starou vizualizaci, co jsem neklikal v flourish, která mapuje jak se vyvíjela místa na táborské radnici. To byly časy, kdy jsem přemýšlel jak vizualizovat politická data a cpal to do každého předmětu, jak mi to chybí!
<div class="flourish-embed flourish-parliament" data-src="visualisation/1761986"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/1761986/thumbnail" width="100%" alt="parliament visualization" /></noscript></div>

---------------

Poslední programovací projekt byl nástin [emailového kurzu](https://github.com/ridlees/email-courses), což je jednoduchý skript, co posílá v pravidelných vlnách emaily s definovanými kroky (jeden týden pošle 1., druhý týden pošle 2.) V budoucnu udělám kurz o něčem z mých studií, zadarmo, samozřejmě. Zatím přemýšlím nad úvodem do republikanismu či něčem z nových medií (například malý kurz o mediální archeologii). 


