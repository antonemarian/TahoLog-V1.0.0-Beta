# 🚛 TahoLog - Asistent Digital Profesional pentru Șoferi de Camion

**TahoLog** este o aplicație Android de ultimă generație concepută special pentru șoferii de camion din transportul internațional și național de marfă. Aplicația ajută la monitorizarea exactă a timpilor de conducere, muncă, disponibilitate și repaus, în conformitate cu **Regulamentul (CE) Nr. 561/2006** și **Pachetul de Mobilitate UE**.

---

## 🌟 Funcționalități Principale

### ⏱️ 1. Monitorizare & Calcul Timpi în Timp Real
* **Calcule automate conform CE 561/2006**:
  * Program zilnic de conducere (9h / 10h extins).
  * Timp continuu de conducere (4h30m cu atenționare pauză 45m).
  * Repaus zilnic (11h normal / 9h redus) și amplitudine zilnică (13h / 15h).
  * Repaus săptămânal (45h normal / 24h redus) cu evidențierea și calculul datoriilor de compensare.
* **Muncă de noapte**: Detectare automată conform legislației specifice fiecărei țări (ex. intervalul 00:00 - 04:00).
* **Verificare conformitate săptămânală**: Indicatoare vizuale (buline de reducere 9h) care se migrează și resetează automat la începerea unei noi săptămâni.

### 🚗 2. Moduri de Lucru Adaptabile
* **Mod SMART / ASISTENT**: Detectare automată a mișcării prin GPS și senzorul G-Sensor / accelerometru, trecând automat între *DRIVING*, *WORK* și *REST*.
* **Mod TAHO / HIBRID**: Integrează telemetria Bluetooth în timp real de pe tahograf.
* **Mod MANUAL**: Control manual total pentru introducerea și editarea activităților.

### 🏖️ 3. Modul Concediu de Odihnă (`isVacation`) & Diurnă
* **Detectare Concediu**: La o pauză neîntreruptă de peste 45 ore, aplicația oferă opțiunea de activare a Modului Concediu.
* **Economisire Energie & Date**: În modul concediu, senzorii sunt opriți, iar starea de concediu se transmite automat către flotă o dată la 24 ore.
* **Calculator Diurnă**: Calcul automat al diurnei externe și interne în funcție de țara de rezidență și perioadele de tranzit.

### 🌐 4. Sincronizare Cloud & Management Flotă (VIP)
* **Sincronizare în timp real cu dispeceratul (Firebase Firestore)**:
  * Trimitere locație GPS, stare activă zi (`isDayActive`), repaus săptămânal (`isWeeklyRest`) și viteza camionului.
  * Sistem de rezervă în 3 trepte pentru GPS (GPS Live $\rightarrow$ AppState $\rightarrow$ Ultimul Log salvat) pentru raportare garantată chiar și în zone fără semnal satelit.
* **Backup & Restaurare**: Restaurare completă a istoricului din Cloud cu un singur click în caz de schimbare a telefonului.

### 🔋 5. Ghid Inteligent de Baterie OEM
* **Suport nativ pentru producători mari (Samsung, Xiaomi, Huawei, Oppo, Vivo)**:
  * Detectare automată a marcii telefonului.
  * Navigare directă către meniurile speciale (*Aplicații niciodată inactive*, *Pornire automată / Autostart*) cu animație de evidențiere pe buton.
  * Funcționare neîntreruptă ca *Foreground Service* în fundal.

---

## 🛠️ Arhitectură Tehnică & Tehnologii Utilizate

* **Limbaj & UI**: Kotlin, Jetpack Compose (Modern Material 3 UI).
* **Arhitectură**: MVVM (Model-View-ViewModel), Coroutines, Kotlin Flow, StateFlow.
* **Bază de date Locală**: Room Database v49 (cu migrare automată și suport complet offline).
* **Servicii de Fundal**: Foreground Service cu protecție WakeLock și canale de notificare dedicate.
* **Cloud & Auth**: Firebase Auth (Google Sign-In), Cloud Firestore, Firebase Crashlytics & Analytics.
* **Geo & Locație**: Google Play Services Location API, Geocoder local/rețea.
