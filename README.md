# Humanizer Slovak

!\[Version](https://img.shields.io/badge/version-1.0.0-blue)
!\[License](https://img.shields.io/badge/license-MIT-green)

## Prepíš slovenský text tak, ako by ho napísal človek.

Starostlivo zostavený humanizer skill zameraný špecificky na slovenský jazyk. Detekuje 27 vzorov typických pre AI-generovanú slovenčinu a prepíše text tak, aby znel prirodzene a čo najviac ľudsky. 🧑‍🏫



## 4 štýly výstupu

* **Akademický** - odborný, presný, pre výskum, odborné a akademické práce
* **Formálny** - profesionálny, pre firemnú komunikáciu a produktové texty
* **Priateľský** - teplý tón, pre blogy, newslettery, sociálne siete
* **Konverzačný** - neformálny, prirodzený, ako keby si písal kamošovi



## Čo to robí

* **Zakazuje em dash (—)** - nahrádza ho bežnou pomlčkou (-)
* **Identifikuje slovenské AI klišé** ("V dnešnej dobe", "Je dôležité zdôrazniť", "Na záver možno konštatovať"...)
* **Detekuje anglický slovosled**, kalky, nominalizáciu a ďalšie slovensko-špecifické vzorce
* **Odstraňuje nafúknutý jazyk**, trpný rod, vágne atribúcie
* **Pridáva osobnosť** a autentický hlas
* **Dual-pass systém**: prepíše → skontroluje → opraví znovu
* **4 štýly výstupu:** akademický, formálny, priateľský, konverzačný



## Smrť em dashi! 🥳

Poznáte ten dlhý pomlčkový znak **—** čo je doslova v každom AI texte? Ten, čo žiadny "normálny" Slovák NIKDY v živote nenapíše, lebo na klávesnici jednoducho stlačí pomlčku "-"? Tak ten už vo svojom texte neuvidíte.<br>
Je to na prvý pohľad najviditeľnejší znak AI-generovaného textu a je úplne všade. Toto je prvý slovenský humanizer, ktorý ho rieši natvrdo ako globálne pravidlo.



## Príklad

**Vstup (typický AI text):**

> V dnešnom rýchlo sa meniacom digitálnom svete je čoraz dôležitejšie venovať pozornosť oblasti umelej inteligencie. Je dôležité zdôrazniť, že AI predstavuje revolučnú technológiu, ktorá zásadným spôsobom mení krajinu moderného podnikania.

**Výstup (štýl: priateľský):**

> AI v podnikaní riešia firmy teraz, nie o päť rokov. Gartner hovorí, že ju testuje 65 % stredných firiem v Európe, ale úprimne - väčšina z nich len skúša, čo to vlastne vie.



## 27 detekovaných vzorov

|#|Vzor|Príklad|
|-|-|-|
|1|Nafúknuté otváracie frázy|"V dnešnej dobe..."|
|2|Prehnané zdôrazňovanie|"Je dôležité zdôrazniť..."|
|3|Formulaické závery|"Na záver možno konštatovať..."|
|4|Nadužívanie spojok|"Avšak", "Okrem toho", "V neposlednom rade"|
|5|Prehnane formálny jazyk|"Bolo dosiahnuté", "Je potrebné"|
|6|Pravidlo troch|Trojice prídavných mien/príkladov|
|7|Propagačný jazyk|"Revolučný", "Inovatívny", "Komplexné riešenie"|
|8|Vágna atribúcia|"Odborníci sa zhodujú", "Štúdie ukazujú"|
|9|Nadužívanie pomlčiek|Prehnané em dash (—)|
|10|Prehnané formátovanie|Tučné nadpisy v zoznamoch|
|11|Emoji dekorácie|Emoji v nadpisoch|
|12|Chatbot artefakty|"Skvelá otázka!", "Rád pomôžem"|
|13|Synonymické koliesko|Spoločnosť/firma/podnik/korporácia|
|14|Falošné rozsahy|"Od startupov po korporácie"|
|15|Generické závery|"Budúcnosť vyzerá sľubne"|
|16|Výplňové frázy|"Za účelom dosiahnutia", "Vzhľadom na to, že"|
|17|Anglický slovosled|Porušenie aktuálneho členenia vetného|
|18|Monotónny rytmus|Všetky vety podobnej dĺžky (nízka burstiness)|
|19|Privlastňovacie zámená|"Otvoril svoje oči a vzal svoj telefón"|
|20|Anglické kalky|"Poďme sa ponoriť do", "na dennej báze"|
|21|Nadmerná nominalizácia|"Došlo k realizácii implementácie"|
|22|Meta-komentáre|"V tomto článku sa pozrieme na..."|
|23|Falošná vyváženosť|"Na jednej strane... na druhej strane..."|
|24|Ukazovacie zámená|"Tento problém... Táto situácia... Tieto faktory..."|
|25|Copula avoidance|"Predstavuje kľúčový nástroj" namiesto "je"|
|26|Sendvičová štruktúra|Úvod - 3 body - záver vždy|
|27|Tautologické zdvojenia|"rôzne a rozmanité", "efektívne a účinné"|



> \[!NOTE]
> \*\*Výsledky detektorov:\*\* Vzali sme extra ťažko AI-generovaný text, pri ktorom všetky detektory hlásili 100 % AI. Prohnali sme ho týmto slovenským humanizerom a nechali otestovať top detektory. Výsledok?<br>
> Copyleaks: 0% AI. ✅<br>
> GPTZero: "entirely human". ✅<br>
> Grammarly: 0% AI. ✅



\---

## 🔧 Inštalácia

### Claude Code (odporúčané)

```bash
# Naklonuj do priečinka skills
mkdir -p \~/.claude/skills
git clone https://github.com/\[repo]/humanizer-slovak.git \~/.claude/skills/humanizer-slovak
```

Potom v Claude Code použi `/humanizer-slovak` nasledovaný textom na humanizáciu.

### Claude.ai (Projects)

1. Stiahni [SKILL.md](SKILL.md) (alebo celý ZIP cez zelené tlačidlo "Code")
2. V claude.ai otvor Settings → Customize → Skills
3. Nahraj SKILL.md ako nový skill

### ChatGPT, Gemini, Copilot, Mistral a ďalšie LLM

1. Otvor [PROMPT.md](PROMPT.md)
2. Skopíruj celý obsah
3. Vlož ako systémový prompt (system instructions) alebo na začiatok konverzácie
4. Pošli text na humanizáciu

\---

## Poďakovanie

Tento projekt je slovenskou adaptáciou [**Humanizer Czech**](https://github.com/bejek/humanizer-czech) — výborne spracovaného českého humanizera, ktorý si zaslúži všetku zásluhu za pôvodnú myšlienku, štruktúru a 27 detekovaných vzorov. Slovenská verzia preberá celý framework, lokalizuje ho pre slovenský jazyk a pridáva slovensko-špecifické jazykové nuansy (iný slovosled rémy, slovenské kalky, miestny kontext).

Inšpirované projektom [humanizer](https://github.com/blader/humanizer) od [@blader](https://github.com/blader) - pôvodná anglická verzia s 10k+ stars, ktorá to všetko odštartovala.

Vychádza tiež z [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing).

Vzorce 17-27 identifikované cross-referenciou výstupov z Claude, ChatGPT a Gemini.

\---

## Licencia

[MIT](LICENSE) - používaj ako chceš, komerčne aj nekomerčne.

\---
