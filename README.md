# Humanizer Slovak

![Version](https://img.shields.io/badge/version-2.4.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)

![Slovak Humanizer](assets/slovak-humaniser.jpg)

Humanizer Slovak je skill pre jazykové modely. Prepíše slovenský text tak, aby neznel ako od AI. Hľadá v ňom 47 vzorov: 27 základných štýlových, 15 špecificky slovenských (gramatika, pravopis a typografia) a 5 univerzálnych vzorov prevzatých z novších verzií anglického humanizeru.

Spravil som ho, lebo som potreboval slovenský text od AI, ktorý nesmrdí AI. Anglické nástroje slovenčinu nepokryjú. Model videl oveľa viac češtiny než slovenčiny a myslí akoby po anglicky, takže keď si nie je istý, skĺzne do češtiny alebo do angličtiny. Práve na to sú špecificky slovenské gramatické a typografické vzory.

## Ako to funguje

Skill text prepíše, potom sa sám spýta, čo na ňom ešte prezrádza AI, a dorobí opravy. Ak štýl nezadáš, najprv sa naň opýta. Na výber sú štyri:

- akademický: odborný a presný, na výskum a odborné práce
- formálny: profesionálny, na firemnú komunikáciu a produktové texty
- priateľský: vrelý tón, na blogy, newslettery a sociálne siete
- konverzačný: neformálny, akoby si písal kamarátovi

Hľadá slovenské AI klišé („V dnešnej dobe“, „Je dôležité zdôrazniť“, „Na záver možno konštatovať“), anglický slovosled, kalky, nominalizácie, nafúknutý jazyk, trpný rod a vágne atribúcie. Nielen škrtá, snaží sa dodať aj hlas. Má tiež zoznam vecí, ktoré opravovať netreba, lebo dokonalá gramatika ešte nie je dôkaz AI, a znaky ľudského písania, ktoré má nechať na pokoji.

## Pomlčky

Najviditeľnejší prezradca AI textu je dlhý znak „—“ (em dash). Slovenské pravopisné pravidlá ho nepoznajú, rozlišujú len pomlčku a spojovník. Skill ho preto do výstupu nepustí vôbec. Dá pomlčku „–“ s medzerami, alebo vetu radšej prestaví. Spojovník pomlčku nenahrádza.

Tri znaky, ktoré sa v slovenčine nesmú zamieňať:

| Znak | Názov | Kód | Použitie |
|------|-------|-----|----------|
| - | spojovník | U+002D | zložené slová a mená bez medzier (slovensko-poľský) |
| – | pomlčka | U+2013 | vetná pomlčka a rozpätie, s medzerami (text – pokračovanie, 1980 – 1990) |
| — | em dash | U+2014 | slovenské pravopisné pravidlá ho nepoznajú |

## Príklad

Vstup (typický AI text):

> V dnešnej rýchlo sa meniacej digitálnej dobe je čoraz dôležitejšie venovať pozornosť oblasti umelej inteligencie. Je dôležité zdôrazniť, že AI predstavuje revolučnú technológiu, ktorá zásadným spôsobom mení krajinu moderného podnikania.

Výstup (štýl priateľský):

> AI v podnikaní riešia firmy teraz, nie o päť rokov. Ale úprimne, väčšina z nich ešte len skúša, čo to vlastne vie.

## Vzory

Číslovanie zodpovedá SKILL.md.

Štýlové (1 – 27), aby to neznelo ako AI:

| # | Vzor | Príklad |
|---|------|---------|
| 1 | Nafúknuté otváracie frázy | „V dnešnej dobe…“ |
| 2 | Prehnané zdôrazňovanie | „Je dôležité zdôrazniť…“ |
| 3 | Formulaické závery | „Na záver možno konštatovať…“ |
| 4 | Nadužívanie spojok | „Napriek tomu“, „Okrem toho“, „V neposlednom rade“ |
| 5 | Prehnaná formálnosť | „Dosiahol sa“, „Je potrebné“ |
| 6 | Pravidlo troch | Trojice prídavných mien alebo príkladov |
| 7 | Propagačný jazyk | „Revolučný“, „Inovatívny“, „Komplexné riešenie“ |
| 8 | Vágne atribúcie | „Odborníci sa zhodujú“, „Štúdie ukazujú“ |
| 9 | Nadužívanie pomlčiek | Prehnaný em dash (—) |
| 10 | Prehnané formátovanie | Tučné nadpisy v zoznamoch |
| 11 | Emoji dekorácie | Emoji v nadpisoch |
| 12 | Chatbot artefakty | „Skvelá otázka!“, „Rád pomôžem“ |
| 13 | Synonymické koliesko | Spoločnosť, firma, podnik, korporácia |
| 14 | Falošné rozsahy | „Od startupov po korporácie“ |
| 15 | Generické závery | „Budúcnosť vyzerá sľubne“ |
| 16 | Výplňové frázy | „S cieľom dosiahnuť“, „Vzhľadom na to, že“ |
| 17 | Anglický slovosled | Porušenie aktuálneho vetného členenia |
| 18 | Monotónny rytmus | Všetky vety približne rovnako dlhé |
| 19 | Privlastňovacie zámená | „Otvoril svoje oči a vzal svoj telefón“ |
| 20 | Anglické kalky | „Poďme sa ponoriť do“, „na dennej báze“ |
| 21 | Nadmerná nominalizácia | „Došlo k realizácii implementácie“ |
| 22 | Metakomentáre | „V tomto článku sa pozrieme na…“ |
| 23 | Falošná vyváženosť | „Na jednej strane… na druhej strane…“ |
| 24 | Ukazovacie zámená | „Tento problém… Táto situácia… Tieto faktory…“ |
| 25 | „Predstavovať“ namiesto „je“ | „Predstavuje kľúčový nástroj“ |
| 26 | Sendvičová štruktúra | Úvod, tri body, záver, vždy |
| 27 | Tautologické zdvojenia | „rôzne a rozmanité“, „efektívne a účinné“ |

Špecificky slovenské vzory (28 – 34 a 40 – 47), aby to bola správna slovenčina podľa PSP a KSSJ. Toto je hlavný rozdiel oproti českej a anglickej verzii:

| # | Vzor | Príklad |
|---|------|---------|
| 28 | Bohemizmy | „další“, „teď“, „protože“ → „ďalší“, „teraz“, „pretože“ |
| 29 | Rytmický zákon | „krásný“, „múdrý“ → „krásny“, „múdry“ (krátenie po dlhej slabike) |
| 30 | Vokalizácia predložiek | „v vode“, „s sestrou“ → „vo vode“, „so sestrou“ |
| 31 | Poradie príkloniek | „chcel som opýtať sa ho“ → „chcel som sa ho opýtať“ (by, som, sa, mi, ho) |
| 32 | Podmieňovací spôsob | „bych“, „abych“, „kdybych“ → „by som“, „aby som“, „keby som“ |
| 33 | Mäkčene a mäkké ľ | „ludia“, „učitel“ → „ľudia“, „učiteľ“ |
| 34 | Vybrané slová a sústava i/y | „mi sme“, „bidlisko“ → „my sme“, „bydlisko“ |
| 40 | Anglosaská interpunkcia pri úvodzovkách | rovné `" "` a bodka vždy dnu → „ “ podľa PSP |
| 41 | Zápis čísel, mien a dátumov | „40%“, „€12,500“, „2000 eúr“ → „40 %“, „12 500 €“, „2000 eur“ |
| 42 | Vetné chvosty | „, čo podčiarkuje…“, „, čím posilňuje…“ (v zhluku) |
| 43 | Formulka „Či už ide o X, alebo Y“ | šablónovitý úvod, čiarka pred „alebo“ |
| 44 | „Pre“ namiesto „na“ pri účele | „nástroj pre analýzu“ → „nástroj na analýzu“ |
| 45 | Frázové a spoločenské kalky | „adresovať problém“ → „zaoberať sa“; „to závisí“, „Maj pekný deň“ |
| 46 | Konzistentné vykanie/tykanie a veľké „Vy“ | jednotný tón, „Pošlite nám svoje údaje“ |
| 47 | Čiarky v súvetí (pravopisná kontrola) | pred „a preto“, „či – alebo“, vedľajšia veta s „ako/než“ |

Aktualizácia z novších verzií anglického [blader/humanizer](https://github.com/blader/humanizer) (35 – 39). Univerzálne vzory, ktoré nie sú viazané na konkrétny jazyk:

| # | Vzor | Príklad |
|---|------|---------|
| 35 | Negatívne paralelizmy | „nie je to len o…, je to…“, „nielen… ale aj…“ |
| 36 | Písanie ukotvené v zmene | opisuje zmenu namiesto veci samej |
| 37 | Vyrobené pointy, staccato dráma | séria krátkych fragmentov na umelú drámu |
| 38 | Aforizmové formulky | „X je jazykom Y“, „X sa stáva pascou“ |
| 39 | Konverzačné rečnícke otvárače | „Úprimne?“, „Pozri,“, „Ide o to, že“ |

## Čo to nerobí

Nie je to detektor. Nepovie ti, či text písala AI, a nezaručí, že ho detektory pustia. Slovenskú verziu som na detektoroch netestoval. Autor českej verzie uvádza, že jeho text po úprave prešiel cez Copyleaks, GPTZero aj Grammarly. Je to jeho test na češtine, nie môj, a nie je to štúdia.

Pri prepise si model môže vymyslieť aj konkrétne údaje. Ukážka v SKILL.md na to sama upozorňuje. Čísla a mená si po ňom skontroluj. A zmysel textu skill nemení. Zlý argument ostane zlým argumentom, len bez klišé.

## Inštalácia

### Claude Code (odporúčané)

```bash
# Naklonuj do priečinka skills
mkdir -p ~/.claude/skills
git clone https://github.com/ZoloZiak/humanizer-slovak.git ~/.claude/skills/humanizer-slovak
```

Potom v Claude Code použi `/humanizer-slovak` a za ním text na humanizáciu.

### Claude.ai (Projects)

1. Stiahni [SKILL.md](SKILL.md) (alebo celý ZIP cez zelené tlačidlo „Code“).
2. V claude.ai otvor Settings → Customize → Skills.
3. Nahraj SKILL.md ako nový skill.

### ChatGPT, Gemini, Copilot, Mistral a ďalšie LLM

1. Otvor [PROMPT.md](PROMPT.md).
2. Skopíruj celý obsah.
3. Vlož ho ako systémový prompt (system instructions) alebo na začiatok konverzácie.
4. Pošli text na humanizáciu.

## Poďakovanie

Je to slovenská adaptácia projektu [humanizer-czech](https://github.com/bejek/humanizer-czech) od [@bejek](https://github.com/bejek). Štruktúra a 27 vzorov sú jeho. Český projekt vychádza z projektu [humanizer](https://github.com/blader/humanizer) od [@blader](https://github.com/blader), pôvodnej anglickej verzie s viac ako 10 000 hviezdičkami.

Slovenská verzia pridáva 15 špecificky slovenských gramatických a typografických vzorov a 5 novších univerzálnych vzorov z anglického originálu. Vzory 17 – 27 podľa autora českej verzie vznikli porovnávaním výstupov z Claude, ChatGPT a Gemini. Projekt vychádza aj z článku [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing).

## Licencia

[MIT](LICENSE). Používaj ako chceš, komerčne aj nekomerčne.