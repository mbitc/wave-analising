# 🌊 Bangos analizė — erdvėlaikio lauko vizualizacija

Interaktyvi 1D kompleksinio bangos lauko vizualizacija, rodanti, kaip sistema evoliucionuoja erdvėje ir laike veikiama nelinijinių bei disipatyvių procesų.

🔗 Demo: https://mbitc.github.io/wave-analising/

---

## 🧠 Modelio esmė

Modelis paremtas apibendrinta nelinijine Schrödinger tipo lygtimi su energijos įvedimu ir prisotinimu:

[
i \partial_t \psi = -\alpha \partial_x^2 \psi - g |\psi|^2 \psi + V(x)\psi + i(\gamma - \beta |\psi|^2)\psi
]

### Kintamieji

* **ψ(x,t)** — kompleksinis bangos laukas
* **α** — dispersijos koeficientas
* **g** — nelinijiškumas
* **V(x)** — išorinis potencialas
* **γ** — energijos įvedimas (gain)
* **β** — prisotinantis slopinimas (loss)

📌 Sistema nėra konservatyvi:

* energija gali augti
* gali stabilizuotis
* gali formuoti struktūras arba chaotiškai elgtis

---

## 📊 Kas vizualizuojama

Rodomi trys laukai erdvėlaikio (spacetime) reprezentacijoje:

### 1. Amplitudė

[
|\psi(x,t)|
]
Rodo bangos intensyvumą / energijos tankį.

---

### 2. Realioji dalis

[
\text{Re}[\psi(x,t)]
]
Parodo bangos struktūrą (⚠️ tai nėra fazė).

---

### 3. Srautas

[
j(x,t) = 2\alpha \cdot \text{Im}(\psi^* \partial_x \psi)
]

Rodo bangos „judėjimo kryptį“ ir intensyvumą.

---

## 🕒 Erdvelaikio vaizdavimas

* **Horizontaliai (X):** laikas

  * dešinė → dabartis
  * kairė → praeitis

* **Vertikaliai (Y):** erdvė (x)

Kiekvienas naujas žingsnis įrašomas kaip nauja kolona → susidaro istorija.

---

## ⚙️ Skaitinis metodas

* Baigtinių skirtumų metodas (erdvei)
* **RK4 (Runge–Kutta 4 eilės metodas)** laikui
* Periodinės ribinės sąlygos
* Tinklelis: `N = 512`

### Stabilumo pastabos

* Didelis **g** → stiprūs nelinijiniai efektai
* Didelis **γ** → eksponentinis augimas
* **β > 0** → stabilizuoja sistemą

---

## 🎛 Valdymas

### Pradinės sąlygos

* **Gaussas** — lokalizuotas paketas
* **Du paketai** — sąveikaujančios bangos
* **Triukšmas** — atsitiktinė būsena
* **Tuščia + gain** — nestabilumo augimas iš triukšmo

---

### Fizikiniai parametrai

| Parametras | Reikšmė                  |
| ---------- | ------------------------ |
| g          | nelinijiškumo stiprumas  |
| α          | dispersija               |
| γ          | energijos įvedimas       |
| β          | prisotinantis slopinimas |
| V₀         | potencialo stiprumas     |

---

### Vizualizacija

* Spalvų žemėlapiai:

  * plasma
  * viridis
  * inferno
  * diverging (pasirašytiems laukams)
* Reguliuojamas istorijos ilgis

---

## 📈 Stebimi dydžiai

* **Norma**
  [
  \int |\psi|^2 dx
  ]

* **Maksimali amplitudė**

* **Bendras srautas**
  [
  \int |j(x)| dx
  ]

* **Laikas t**

---

## 🔍 Interpretacija

Galimi reiškiniai:

### Nelinijiniai efektai

* savikoncentracija
* lokalizuotos struktūros (solitonų tipo)
* kolapsas

### Gain / Loss dinamika

* augimas (γ > 0)
* stabilizacija per β

### Transportas

* kryptinis judėjimas (j)
* interferencijos

---

## ⚠️ Apribojimai

* 1D modelis
* Nenaudojamas FFT (dispersija aproksimuota)
* Fiksuotas laiko žingsnis
* Dinaminė spalvų normalizacija gali iškraipyti amplitudės suvokimą
* Fazė nėra tiesiogiai rodoma

---

## 🚧 Tolimesnė plėtra

* Fazės (arg ψ) vizualizacija
* Spektrinė analizė (FFT)
* Energijos funkcionalas
* 2D modelis
* Eksportas / įrašymas

---

## 🧩 Kontekstas

Modelis artimas:

* nelinijinei Schrödinger lygčiai (NLS)
* Ginzburg–Landau tipo sistemoms
* disipatyvioms bangoms

Naudingas tyrinėti:

* struktūrų formavimąsi
* nestabilumus
* emergentinį elgesį

---

## 📦 Technologijos

* Vanilla JavaScript
* HTML5 Canvas
* Be išorinių bibliotekų

---

## 🧠 Esmė

Tai ne tik vizualizacija.

Tai įrankis stebėti, kaip iš paprastos lygties atsiranda sudėtingas elgesys:

> struktūra kyla iš dispersijos, nelinijiškumo ir energijos srauto sąveikos
