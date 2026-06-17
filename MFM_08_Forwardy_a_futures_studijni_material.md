# Otázka 8 — Forwardy a futures

> **Zadání:** Stručná charakteristika derivátů. Podrobnější charakteristika forwardů a futures, jejich druhů a specifikace rozdílů mezi forwardy a futures. Odvození forwardové ceny. Způsob využití forwardů a futures při zajišťování.

**Mapa otázky na kapitoly:**
charakteristika derivátů → **kap. 1** · charakteristika forwardů a futures → **kap. 2** · druhy → **kap. 3** · rozdíly → **kap. 4** · odvození forwardové ceny → **kap. 5** · vztah forward/futures cen → **kap. 6** · zajišťování (hedging) → **kap. 7**.

---

## 1. Stručná charakteristika derivátů

**Derivát** (odvozený cenný papír) je finanční instrument, jehož hodnota je **odvozena od hodnoty podkladového aktiva** (*underlying*). Podkladovým aktivem může být akcie, akciový index, měna, úroková míra, komodita nebo dluhopis.

Společné rysy derivátů:

- hodnota se odvíjí od ceny podkladového aktiva,
- jde o **termínový obchod** — sjednání dnes, plnění v budoucnu,
- umožňují **finanční páku** (malý kapitál ovládá velkou nominální pozici),
- hlavní využití: **zajištění (hedging)**, **spekulace** a **arbitráž**.

### Klasifikace finančních derivátů

**Finanční deriváty** se dělí do tří skupin:

1. **Nepodmíněné termínované kontrakty** — obě strany mají *povinnost* plnit:
   - **Forwardy** — FRA, měnový, akciový, komoditní
   - **Futures** — úrokové, měnové, akciové, komoditní, na akciový index
2. **Opční kontrakty** — držitel má *právo* (ne povinnost) plnit:
   - **Opce** — na akcie, indexy, měnu, úroky, futures
   - **Jiné opční instrumenty** — opční listy, Cap, Floor, Collar
3. **Swapové kontrakty** — úrokové, měnové, komoditní, na cenné papíry

> **Klíčové odlišení:** u **opce** má držitel *právo* plnit (může, ale nemusí), u **forwardu / futures** má *povinnost* plnit. Forwardy a futures jsou tedy „nepodmíněné" — plnění nastane vždy.

---

## 2. Forwardy a futures — podrobná charakteristika

### 2.1 Forward

**Forward** je cenný papír, který ukládá držiteli **povinnost** (na rozdíl od opce, kde má právo) prodat nebo koupit podkladový instrument **v dohodnutém čase za dohodnutou cenu**.

- Dohodnutá **forwardová cena** je stanovena tak, aby **hodnota kontraktu byla v okamžiku uzavření nulová** — žádná ze stran neplatí druhé za vstup do kontraktu.
- Ve forwardu lze zaujmout dvě pozice:
  - **Krátká pozice (short)** = strana, která se zavazuje **prodat** podkladový instrument.
  - **Dlouhá pozice (long)** = strana, která se zavazuje **koupit** podkladový instrument.
- Forwardy jsou založeny na **opačném očekávání** obou stran (long sází na růst ceny, short na pokles).
- Obchodují se na **mimoburzovních trzích (OTC — over the counter)**.
- **Nejsou standardizovány** — objem, datum, kvalita i ostatní podmínky si lze libovolně dohodnout.

**Vstup do forwardu nic nestojí** (hodnota = 0). V čase expirace $T$ se long zavazuje koupit a short prodat za sjednanou cenu $K = FW(t,T)$.

Výplatní funkce (payoff) v čase $T$:

- **Long:** $\;S(T) - K$  (vydělá, když cena vzroste nad sjednanou)
- **Short:** $\;K - S(T)$  (vydělá, když cena klesne pod sjednanou)

### 2.2 Futures

**Futures = burzovní ekvivalent forwardu.** Liší se zejména:

- **Standardizací** — množství, kvalita, čas (expirace) jsou pevně dané burzou.
- **Denním zúčtováním zisků a ztrát (mark-to-market)** — zisky/ztráty se připisují, resp. odepisují každý den.
- **Standardizovanou splatností** — např. futures na indexy expirují vždy **třetí pátek měsíců březen, červen, září a prosinec**.
- K **vypořádání** kontraktu, který vypršel, dochází většinou v den následující po splatnosti.

**Maržový systém:**

- Při uzavření kontraktu se skládá **maržový vklad (margin)**.
- **Initial (vstupní) margin** — kapitál nutný pro otevření pozice.
- **Maintenance (udržovací) margin** — minimální hodnota účtu; klesne-li vklad pod ni (z důvodu nepříznivého vývoje), přijde **margin call** (výzva k doplnění).
- Pokud investor nedoplní hotovost nebo jinak nezajistí pozici (standardně do jednoho dne), může mu být kontrakt uzavřen za aktuální cenu.
- Protože stačí složit pouze **část** nominální hodnoty, dochází k **efektu finanční páky**.

> **Poznámka (BCPP):** Na Burze cenných papírů Praha se v současnosti žádné futures neobchodují — obchodování skončilo v roce 2012 v souvislosti s přechodem na platformu Xetra®.

**Ilustrace finanční páky (E-mini NASDAQ-100).** Nominální hodnota kontraktu = 20× hodnota indexu; při pohybu indexu o 1 bod investor vydělá/ztratí 20 USD. Initial margin ≈ 3 245 USD, maintenance ≈ 2 950 USD (k 31. 1. 2014). Investor s vkladem 5 000 USD ovládá nominál ≈ 70 000 USD, tj. páka ≈ 14×. Proto změna indexu o 2 % vyvolá zisk/ztrátu řádově **~28 %** vloženého kapitálu (růst ≈ +27,8 %, pokles ≈ −28,2 % — asymetrie plyne z rozdílu nákupní a prodejní ceny).

---

## 3. Druhy forwardů (a futures)

Podle podkladového aktiva:

- **Akciové** — podkladem je akcie.
- **Komoditní** — podkladem je skladovatelná komodita (obilí, ropa, kovy…).
- **Měnové** — závazek směnit jednu měnu za druhou za forwardový kurz.
- **Úrokové (FRA — Forward Rate Agreement)** — závazek půjčit/vypůjčit částku za forwardovou úrokovou míru.

U **futures** se navíc běžně obchoduje varianta **na akciový index** (NASDAQ-100, S&P 500, dříve PX apod.).

---

## 4. Specifikace rozdílů mezi forwardy a futures

| Hledisko | **Forward** | **Futures** |
|---|---|---|
| Místo obchodování | mimoburzovní (OTC) | burzovní |
| Standardizace | ne — podmínky volně dohodnuté | ano — množství, kvalita, expirace |
| Protistrana | konkrétní druhá strana | clearingové centrum (burza) |
| Kreditní (úvěrové) riziko | vyšší — riziko selhání protistrany | minimální — garantuje clearingové centrum |
| Zúčtování | jednorázově při expiraci | denní (mark-to-market) |
| Marže | obvykle se neskládá | ano (initial + maintenance margin) |
| Likvidita | nižší | vyšší |
| Vypořádání | většinou fyzické dodání | často uzavření opačnou pozicí (peněžní) |
| Flexibilita | vysoká (šito na míru) | nízká (pevné parametry) |

> **Souhrn:** *Futures jsou standardizované, burzovní a denně zúčtované; forwardy jsou nestandardizované, OTC a zúčtované jednorázově.* Pro **krátkodobé kontrakty** jsou cenové odchylky velmi malé, proto **vztahy odvozené pro forwardy lze použít i pro futures** (viz kap. 6).

---

## 5. Odvození forwardové ceny

Jádro otázky. Společný princip všech vzorců je **arbitrážní argument typu cost-of-carry**: forwardová cena musí být taková, aby nebylo možné dosáhnout bezrizikového zisku (arbitráže).

**Označení:**

- $t$ = čas uzavření, $T$ = čas expirace, $T - t$ = doba do expirace,
- $S(t)$ = aktuální (spotová) cena podkladového aktiva,
- $r_f$ = intenzita úročení bezrizikových aktiv (spojité úročení; např. státní pokladniční poukázky),
- $FW(t,T)$ = forwardová cena zaručující **nulovou hodnotu kontraktu** v čase $t$.

### 5.1 Forward na akcii (bez dividendy)

$$FW(t,T) = S(t)\,e^{\,r_f(T-t)}$$

**Odvození arbitráží.** Ukážeme, že jakákoli odchylka od této rovnosti umožní bezrizikový zisk — proto musí platit rovnost.

**Případ A:** $\;FW(t,T) > S(t)\,e^{r_f(T-t)}\;$ (forward je *nadhodnocen*)

*V čase $t$:*

- vstoupíme do **short** pozice ve forwardu (zavážeme se prodat za $FW(t,T)$),
- **půjčíme si** $S(t)$ za sazbu $r_f$ a **koupíme akcii** za $S(t)$,
- čistý peněžní tok v čase $t$ je **0**.

*V čase $T$:*

- dodáme akcii a inkasujeme $FW(t,T)$,
- splatíme úvěr ve výši $S(t)\,e^{r_f(T-t)}$,
- **zisk** $= FW(t,T) - S(t)\,e^{r_f(T-t)} > 0$ — a to **bezrizikově**.

**Případ B:** $\;FW(t,T) < S(t)\,e^{r_f(T-t)}\;$ (forward je *podhodnocen*)

*V čase $t$:*

- vstoupíme do **long** pozice ve forwardu (zavážeme se koupit za $FW(t,T)$),
- **prodáme akcii nakrátko** (short sell) a získáme $S(t)$,
- získané $S(t)$ **uložíme** za bezrizikovou sazbu $r_f$,
- čistý peněžní tok v čase $t$ je **0**.

*V čase $T$:*

- vybereme uložené peníze $S(t)\,e^{r_f(T-t)}$,
- koupíme akcii přes forward za $FW(t,T)$ a **vrátíme** ji (uzavřeme short pozici),
- **zisk** $= S(t)\,e^{r_f(T-t)} - FW(t,T) > 0$ — opět **bezrizikově**.

Obě odchylky vedou k arbitráži, proto jediná bezarbitrážní cena je
$$FW(t,T) = S(t)\,e^{\,r_f(T-t)}. \qquad \blacksquare$$

### 5.2 Forward na akcii vyplácející dividendu

Vyplatí-li akcie během života forwardu dividendu, snižuje to výhodu z držby akcie o současnou hodnotu dividend $D(t,T)$:

$$FW(t,T) = \big[\,S(t) - D(t,T)\,\big]\,e^{\,r_f(T-t)}$$

**Intuice:** Držitel akcie (na rozdíl od držitele forwardu) inkasuje dividendu. „Efektivní" cena akcie pro účely forwardu je proto snížena o současnou hodnotu dividend.

### 5.3 Forward na skladovatelnou komoditu

Oproti akcii vznikají navíc **skladovací náklady a pojištění**, jejichž současnou hodnotu označíme $I(t,T)$. Ty zvyšují náklady na držení komodity:

$$FW(t,T) = \big[\,S(t) + I(t,T)\,\big]\,e^{\,r_f(T-t)}$$

**Intuice:** Skladování stojí peníze (přesný opak dividendy), proto se k ceně **připočítává**.

### 5.4 Měnový forward

Zavazuje držitele dodat (koupit) měnu jednoho státu za měnu druhého v daném čase za **forwardový kurz**. Platí (tzv. **krytá úroková parita**):

$$FW(t,T) = S(t)\,e^{\,(r_d - r_f)(T-t)}$$

kde $S(t)$ = současný měnový kurz (domácí měna za jednotku zahraniční, např. Kč/USD), $r_d$ = domácí bezriziková sazba, $r_f$ = zahraniční bezriziková sazba.

**Odvození.** Mějme 1 jednotku zahraniční měny (1 USD). Existují dvě cesty, jak z ní mít v čase $T$ domácí měnu (Kč), a obě musí dát stejný výsledek (jinak arbitráž):

- **Cesta 1:** směníme 1 USD hned za spotový kurz na $S(t)$ Kč a uložíme za domácí sazbu $r_d$ → v čase $T$ máme $\;S(t)\,e^{r_d(T-t)}\;$ Kč.
- **Cesta 2:** uložíme 1 USD za zahraniční sazbu $r_f$ → v čase $T$ máme $e^{r_f(T-t)}$ USD, které směníme za **předem sjednaný** forwardový kurz $FW(t,T)$ → máme $\;FW(t,T)\,e^{r_f(T-t)}\;$ Kč.

Aby nevznikla arbitráž, musí se obě částky rovnat:

$$S(t)\,e^{r_d(T-t)} = FW(t,T)\,e^{r_f(T-t)}$$
$$\Rightarrow\quad FW(t,T) = S(t)\,e^{\,(r_d - r_f)(T-t)}. \qquad \blacksquare$$

### 5.5 Úrokový forward (forwardová úroková míra, FRA)

Úrokový forward ukládá povinnost půjčit/vypůjčit částku v daném čase za **forwardovou úrokovou míru**.

V čase 0 známe spotové intenzity úročení $r_{t_1}$ a $r_{t_2}$ na doby $t_1$ a $t_2$ (přičemž $t_2 > t_1$). **Forwardová intenzita úročení** $r_{t_1,t_2}$ (sazba sjednaná v čase 0 pro období od $t_1$ do $t_2$, tedy na délku $t_2 - t_1$) je dána:

$$r_{t_1,t_2} = \frac{t_2\,r_{t_2} - t_1\,r_{t_1}}{t_2 - t_1}$$

**Odvození (spojité úročení).** Bezarbitrážní podmínka: uložit peníze na dobu $t_2$ přímo musí dát stejný výsledek jako uložit na $t_1$ a poté „přerolovat" zbývající dobu $t_2 - t_1$ za forwardovou sazbu:

$$e^{\,r_{t_2}\,t_2} = e^{\,r_{t_1}\,t_1}\cdot e^{\,r_{t_1,t_2}\,(t_2 - t_1)}$$

Zlogaritmováním:

$$r_{t_2}\,t_2 = r_{t_1}\,t_1 + r_{t_1,t_2}\,(t_2 - t_1)
\quad\Rightarrow\quad
r_{t_1,t_2} = \frac{t_2\,r_{t_2} - t_1\,r_{t_1}}{t_2 - t_1}. \qquad \blacksquare$$

Jako referenční sazba slouží např. **LIBOR, EURIBOR, PRIBOR**.

#### FRA (Forward Rate Agreement)

Nejznámější úrokový forward. **Nepůjčuje se žádná částka** — v době expirace dojde pouze k **vyrovnání rozdílu** úroků. Využívá se především pro **hedging úrokového rizika**.

**Značení FRA „a×b":** v čase $a$ (měsíců) započne úročení vkladu, který skončí v čase $b$. Např.:

- **FRA 6×9** = sjednaná sazba na **tříměsíční** vklad, úročení započne **za 6 měsíců**.
- **FRA 9×12** = tříměsíční sazba začínající **za 9 měsíců**.

**Odvození FRA sazby (jednoduché úročení).** Stejný princip jako u spojité varianty, jen s jednoduchým úročením a sazbami $i$:

$$(1 + i_1 t_1)\,\big(1 + i_{FRA}(t_2 - t_1)\big) = 1 + i_2 t_2$$
$$1 + i_{FRA}(t_2 - t_1) = \frac{1 + i_2 t_2}{1 + i_1 t_1}$$
$$i_{FRA}(t_2 - t_1) = \frac{i_2 t_2 - i_1 t_1}{1 + i_1 t_1}$$
$$\boxed{\;i_{FRA} = \frac{i_2 t_2 - i_1 t_1}{(t_2 - t_1)\,(1 + i_1 t_1)}\;}$$

**Vyrovnání FRA v čase $t_1$.** Úroky by se normálně platily na konci období ($t_2$), ale FRA se vyrovnává **na začátku** úrokového období ($t_1$) — proto se rozdíl **diskontuje** referenční sazbou. Pro nominál $N$, dobu $\tau = t_2 - t_1$ a referenční sazbu při fixaci $i_{ref}$ platí (z pohledu **kupujícího** FRA, který si fixuje sazbu $i_{FRA}$):

$$\text{Vyrovnání}(t_1) = \frac{N\,(i_{FRA} - i_{ref})\,\tau}{1 + i_{ref}\,\tau}$$

- výsledek **kladný** ($i_{ref} < i_{FRA}$) → kupující (klient) **platí** bance,
- výsledek **záporný** ($i_{ref} > i_{FRA}$) → banka **platí** klientovi.

> **Konvexita vyrovnání:** Při stejné absolutní diferenci sazeb je výše plnění **vždy v neprospěch kupujícího FRA** (klienta), protože se vždy diskontuje referenční sazbou (asymetrie).

**Příklad (FRA 9×12, $N$ = 20 mil. Kč, sjednaná sazba 0,49 %, $\tau = 91/360$):**

- PRIBOR = 0,19 % → klient **zaplatí** bance ≈ **15 159,39 Kč**,
- PRIBOR = 0,79 % → banka **zaplatí** klientovi ≈ **15 136,44 Kč**.

Všimněte si konvexity: stejná diference 0,30 %, ale $|{-}15\,159| > |{-}15\,136|$ — klient je vždy v mírné nevýhodě.

---

## 6. Vztah forwardové a futures ceny

- Pokud **známe budoucí vývoj úrokové míry**, je forwardová a futures cena **stejná**.
- V realitě vývoj sazeb neznáme ⇒ ceny se mohou lišit. Empiricky byly odpozorovány vztahy:
  - **Krátkodobé kontrakty (méně než 9 měsíců):** rozdíly velmi malé.
  - **Slabá korelace podkladu s úrokovou mírou:** rozdíl opět nepodstatný.
  - **Dlouhodobé kontrakty s podkladem citlivým na úrokovou míru** (např. dluhopisy): rozdíly významné. Při **kladné korelaci** futures ceny s úrokovou mírou je **futures cena vyšší** než forwardová (a naopak).

**Proč (intuice):** U futures se zisky/ztráty zúčtovávají denně (mark-to-market). Při kladné korelaci s úrokovou mírou přicházejí zisky (a tedy reinvestice) v době vyšších sazeb a ztráty (které je nutno financovat) v době nižších sazeb → výhoda pro držitele long futures → mírně vyšší futures cena oproti forwardu.

---

## 7. Způsob využití forwardů a futures při zajišťování (hedging)

**Hedging = ochrana proti riziku** (proti nepříznivému pohybu ceny). Pro futures **platí všechny vztahy odvozené pro forwardy**.

### 7.1 Báze a její význam

**Báze** = rozdíl mezi spotovou a futures cenou:

$$B(t) = S(t) - F(t,T)$$

- **Volatilita báze je v praxi řádově nižší** než volatilita spotové či futures ceny → zajištění převádí (velké) **cenové riziko** na (mnohem menší) **bázové riziko**.
- **Contango:** báze je **záporná** ($S < F$, futures nad spotem).
- **Backwardation:** báze je **kladná** ($S > F$, futures pod spotem).

### 7.2 Krátký hedging (short hedge)

Zajištění pro případ **budoucího prodeje** — např. farmář si chce v čase 0 zajistit cenu při prodeji pšenice.

- Prodej plánuje za 1 měsíc (čas $t$), ale nejbližší futures kontrakt expiruje za 3 měsíce (čas $T$).
- V čase 0 vstoupí do **krátké (short)** pozice futures (zavazuje se k prodeji v $T$).
- Za měsíc futures uzavře (vstupem do opačné pozice se stejnou expirací) a prodá pšenici na spotovém trhu.

Příjem:

$$G(t) = S(t) + \big[F(0,T) - F(t,T)\big] = F(0,T) + B(t)$$

Cena $F(0,T)$ je **známá**, proto je výsledné riziko **pouze bázové**.

### 7.3 Dlouhý hedging (long hedge)

Zajištění pro případ **budoucího nákupu** — např. potravinářská firma si chce v čase 0 zajistit cenu na nákup pšenice.

- Nákup plánuje za 1 měsíc (čas $t$), nejbližší futures expiruje za 3 měsíce (čas $T$).
- V čase 0 vstoupí do **dlouhé (long)** pozice futures (zavazuje se ke koupi v $T$).
- Za měsíc futures uzavře a koupí pšenici za spotovou cenu.

Výdaje:

$$V(t) = S(t) + \big[F(0,T) - F(t,T)\big] = F(0,T) + B(t)$$

Opět je riziko **pouze bázové**.

> **Pozn.:** Vzorce pro $G(t)$ i $V(t)$ jsou stejné — efektivní cena = známá futures cena $F(0,T)$ upravená o bázi $B(t)$.

**Příklad (kukuřice).** Spot 347,6 c/bušl, futures (Jul/09) 364,0 c/bušl; předpokládá se zachování poměru futures/spot.

- (a) Spot klesne na 320 → efektivní cena ≈ **348,90 c/bušl**,
- (b) Spot vzroste na 400 → efektivní cena ≈ **345,13 c/bušl**.

V obou scénářích je díky zajištění cena „uzamčena" blízko 364 c/bušl ± malá báze — i přes velký pohyb spotu. Výsledek je shodný pro farmáře (short) i odběratele (long), protože hedgingové vzorce jsou symetrické.

### 7.4 Rolovací hedging

Pro zajištění na **delší období, než pokrývají dostupné futures**, se pozice opakovaně otevírá a zavírá (roluje) po celou dobu zajištění.

- Používat **likvidní futures s kratší expirací** (do 6 měsíců).
- Pozici uzavírat **alespoň jeden měsíc před expirací** (v posledním měsíci bývá obchodování futures často velmi volatilní).

### 7.5 Pojištění portfolia

Investor uzavře na své portfolio forward a zajistí si tím prodejní cenu. Pro ocenění forwardu na portfolio v hodnotě $S(t)$ platí:

$$FW(t,T) = S(t)\,e^{\,r_f(T-t)}$$

- Cena forwardu při uzavření je nulová, ovšem **výnos portfolia se touto operací sníží na bezrizikovou úrokovou míru** (jinak by existovala arbitráž).
- Problém: nalezení vhodné protistrany → lze obejít využitím **futures** (vzniká ale problém standardizace).
- Lze využít **futures na index** (má-li stejné složení jako pojišťované portfolio) nebo **futures na jednotlivá aktiva**.
- Není-li dostupný futures přímo na portfolio, použije se futures s korelací k portfoliu blízkou −1 (dle Málka 2003), ale pak **není eliminováno celé riziko** (zůstává reziduální riziko).

---

## Shrnutí klíčových vzorců

| Instrument / veličina | Vztah |
|---|---|
| Akcie (bez dividendy) | $FW(t,T) = S(t)\,e^{r_f(T-t)}$ |
| Akcie s dividendou | $FW(t,T) = [S(t)-D(t,T)]\,e^{r_f(T-t)}$ |
| Komodita (skladovací náklady) | $FW(t,T) = [S(t)+I(t,T)]\,e^{r_f(T-t)}$ |
| Měnový forward | $FW(t,T) = S(t)\,e^{(r_d-r_f)(T-t)}$ |
| Forwardová úr. míra (spojitě) | $r_{t_1,t_2} = \dfrac{t_2 r_{t_2}-t_1 r_{t_1}}{t_2-t_1}$ |
| FRA sazba (jednoduše) | $i_{FRA} = \dfrac{i_2 t_2 - i_1 t_1}{(t_2-t_1)(1+i_1 t_1)}$ |
| FRA vyrovnání v $t_1$ | $\dfrac{N(i_{FRA}-i_{ref})\tau}{1+i_{ref}\tau}$ |
| Báze | $B(t) = S(t) - F(t,T)$ |
| Krátký / dlouhý hedging | $G(t)=V(t)=F(0,T)+B(t)$ |

---

## Pojmy na rychlé zopakování

- **Long / short** — povinnost koupit / prodat.
- **OTC** — mimoburzovní trh (forwardy).
- **Mark-to-market** — denní zúčtování (futures).
- **Initial / maintenance margin, margin call** — maržový systém futures.
- **Cost-of-carry** — princip odvození forwardové ceny (úrok ± náklady na držbu).
- **Krytá úroková parita** — odvození měnového forwardu.
- **FRA a×b** — forwardová úroková dohoda, vyrovnání v $t_1$, konvexita.
- **Báze, contango, backwardation** — klíčové pro hedging futures.
- **Bázové riziko** — zbytkové riziko po zajištění futures.
