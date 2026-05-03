# Banga erdvėje — vizualinis nelinijinės bangos modelis

## Aprašymas

Šis projektas yra interaktyvi vizualizacija, skirta analizuoti vienmačių kompleksinių bangų dinamiką erdvėje ir laike. Modelis remiasi nelinijine Schrödinger tipo lygtimi su papildomais energijos įvedimo (gain) ir slopinimo (loss) nariais.

Sistema leidžia realiu laiku stebėti, kaip bangos forma evoliucionuoja priklausomai nuo fizinių parametrų ir pradinių sąlygų.

---

## Matematinis modelis

Naudojama lygtis:

i∂ₜψ = −α∂²ₓψ − g|ψ|²ψ + V(x)ψ + i(γ − β|ψ|²)ψ

Kur:

* ψ(x,t) — kompleksinis bangos laukas
* α — dispersijos koeficientas
* g — nelinijiškumas
* V(x) — išorinis potencialas
* γ — energijos įvedimas (gain)
* β — prisotinantis slopinimas (saturating loss)

---

## Vizualizacijos struktūra

Vizualizacija suskirstyta į tris pagrindinius laukus (spacetime reprezentacija):

1. **|ψ(x,t)|**

   * Bangos amplitudė
   * Parodo struktūrų formavimąsi ir lokalizaciją

2. **Re[ψ(x,t)]**

   * Realioji dalis
   * Naudinga fazinių struktūrų stebėjimui (bet nėra pati fazė)

3. **j(x,t)**

   * Srautas: j = 2α·Im(ψ*∂ₓψ)
   * Rodo „judėjimo kryptį“ ir intensyvumą

Laikas vaizduojamas horizontalia kryptimi:

* Dešinė — dabartis
* Kairė — praeitis

---

## Funkcionalumas

### Pradinės sąlygos

* **Gaussas** — lokalizuotas bangos paketas
* **Du paketai** — priešpriešinės bangos
* **Triukšmas** — atsitiktinė būsena
* **Tuščia + gain** — silpnas triukšmas su galimu augimu

---

### Fizikiniai parametrai

* **g (nelinijiškumas)**
  Kontroliuoja savitarpio sąveiką tarp bangos komponentų

* **α (dispersija)**
  Atsakinga už bangos išsisklaidymą

* **γ (gain)**
  Energijos įvedimas į sistemą

* **β (loss)**
  Stabilizuoja augimą per prisotinimą

* **V₀ (potencialas)**
  Sukuria lokalizuotą lauką erdvėje

---

### Vizualiniai nustatymai

* Keli spalvų žemėlapiai (plasma, viridis, inferno, diverging, ice)
* Istorijos gylis (trail length)
* Real-time atnaujinimas

---

## Skaitinis metodas

Naudojamas:

* **RK4 (Runge–Kutta 4-os eilės metodas)** laiko integracijai
* **Baigtinių skirtumų metodas** erdviniams išvestiniams
* **Periodinės ribinės sąlygos**

---

## Interpretacijos pastabos

Svarbu suprasti:

* Sistema yra **ne konservatyvi** (dėl γ ir β)
* Energija gali:

  * atsirasti (gain)
  * išnykti (loss)

Todėl:

* srautas j(x,t) nėra tiesiogiai konservacijos rodiklis
* normos ∫|ψ|²dx dinamika gali keistis

---

## Galimi reiškiniai

Su tinkamais parametrais galima stebėti:

* Solitonų formavimąsi
* Disipacinius darinius
* Bangų interferenciją
* Chaotišką dinamiką
* Nestabilumų augimą iš triukšmo

---

## Apribojimai

* Modelis yra 1D
* Vizualizacija naudoja dinaminę normalizaciją (gali iškraipyti amplitudės suvokimą)
* Fazė nėra tiesiogiai atvaizduojama

---

## Tolimesnės plėtros kryptys

Galimi patobulinimai:

* Fazės (arg ψ) vizualizacija
* Fourier analizė (spektro stebėjimas)
* Energijos / Hamiltoniano skaičiavimas
* 2D versija
* Stabilumo analizės įrankiai

---

## Tikslas

Šis projektas nėra tik vizualizacija — tai eksperimentinė platforma:

* intuicijai apie nelinijines sistemas lavinti
* dinamikos tyrimui
* hipotezių testavimui prieš rimtesnį modeliavimą

---

## Pastaba

Modelio interpretacija priklauso nuo parametrų.
Vizualiai panašūs rezultatai gali turėti skirtingą fizinę prasmę.
