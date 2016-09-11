---
layout: post
title: Zlepšime si svoj život s Latexom
created: 1345553795
categories: []
---
Spolužiaci išli v preplnenej šaline, a jeden z nich plný entuziazmu zo svojho nového objavu zvolal na ostatných: "Včera som robil prvýkrát s Latexom, je to paráda, s tým sa dá spraviť úplne všetko." Nadšene rozvíjal svoje pocity ďalej a zhrozené pohľady ostatných cestujúcich svedčili o tom, že sa nenachádzajú na rovnakej vlnovej dĺžke. Jeden pán sa ale začal prefíkane usmievať.

Nemal na mysli ten "latex":/images/fakelatex.jpg, ale úžasný nástroj na tvorbu dokumentov. Už som dávno zabudol na Word a podobné nezmysly, odkedy používam Latex, je môj život omnoho kvalitnejší!

Jak na to
-------------
Ak si zvyknutý na tvorbu dokumentov alebo prezentácií vo Worde/OpenOffice, tak zo začiatku bude Latex kultúrny šok. Je to niečo úplne iné, viac sa to podobá písaniu webových stránok ako grafickým klikátkam. Keď mu ale prídeš na chuť, tak si ho zamiluješ.

Dokumenty sa v Latexu "programujú". Netreba sa zľaknúť toho slova, je to vlastne veľmi jednoduché. Napríklad keď chceš napísať niečo tučným písmom, tak by si v Latexu zadal `\textbf{text}`.
Každý príkaz začína spätným lomítkom `\`, takže to je klávesa, ktorú sa naučíš používať veľmi často. Potom nasleduje meno príkazu, to čo sa mu zadáva v zložených zátvorkách `{}` a niekedy sa používaju aj hranaté zátvorky `[]` keď je treba uviesť viac parametrov.

Najviac sa Latex používa na publikáciu vedeckých prác alebo dokumentov, ktoré obsahujú veľké množstvo matematických výrazov (napr. skriptá). No vďaka svojej krásnej štruktúrovanosti sa hodí aj na písanie obyčajných dokumentov, pretože len zopár riadkami kódu si môžeš nechať vygenerovať tabuľku obsahu aj s číslami strán, meniť hlavičku či pätu dokumentu a mnoho iného.

Na internete je veľa tutoriálov, z ktorých sa dá všetko zistiť. Zo začiatku je to ale hrozne neprehľadné, to čo som hlavne potreboval bola pekná šablóna, do ktorej by som mohol doplňovať svoje texty. Preto tu poskytujem dokument, ktorý obsahuje veľké množstvo užitočných príkazov, a dá sa z neho veľa pochopiť:

"Download":/upload/latex-ukol.zip

Je to domáca úloha z predmetu Automatické riadenie, ktorý sme mali na škole. Obsahuje vysádzané rovnice, matice, grafy s popiskami, výpis zdrojových kódov, zdroje literatúry. Každá strana je očíslovaná a má svoju hlavičku, ktorá sa neustále opakuje. V Ubuntu sa mi výborne pracuje s editorom "Texmaker":http://www.xm1math.net/texmaker/, ktorý je dostupný aj pod Windowsami.

Štruktúra dokumentu
------------------------------
Šablónu som zjednodušil tak, aby som sa sústredil na to hlavné - písanie, a nič iné ma nerušilo. Preto som hlavičky rozdelil do viacerých súborov, a v každom dokumente iba nastavím, čo sa má v v hlavičkách ukázať. Zdrojový kód je pomerne samovysvetľujúci.

Zopár základných príkazov:
- `\section{}` Nadpis, sekcia, s použitím hviezdičky sa nebude automaticky číslovať `\section*{}`
- `$x^2 = y$` Zápis matematický výrazov. Na podrobný popis odporúčam iné zdroje.
- `\begin{...} ... \end{...}` Vymedzenie bloku, na ktorý sa bude uplatňovať daný výraz.

Enjoy! Veľa sa dá toho nájsť na "Latex wiki":http://en.wikibooks.org/wiki/LaTeX alebo som čerpal v začiatkoch tiež z tutoriálu na "root.cz":http://www.root.cz/clanky/jak-na-latex-uvod/
