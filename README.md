# nConnect - webová aplikácia pre správu IT konferencie

## Popis projektu

**nConnect** je fullstack webová aplikácia vytvorená ako semestrálny projekt. Slúži na komplexnú správu a prezentáciu IT konferencie **nConnect**, ktorá spája študentov IT a popredné firmy z oblasti informačných technológií. Konferencia nadväzuje na tradíciu formátu „IT v praxi" Fakulty prírodných vied a informatiky UKF v Nitre.

Aplikácia poskytuje **verejnú časť** (webstránku konferencie) pre návštevníkov a **administračný panel** pre organizátorov, ktorý umožňuje spravovať celý obsah konferencie bez nutnosti zásahu do kódu.

---

## Hlavné funkcionality

### Verejná časť (pre návštevníkov)
- **Domovská stránka** — prehľad konferencie, informácie o podujatí, náhodný výber speakerov, program, referencie a sponzori
- **Stránka speakerov** — zoznam všetkých speakerov s podrobnými profilmi (fotografia, krátky a dlhý popis, sociálne siete, firma)
- **Program konferencie** — prehľad prednášok rozdelených podľa stage-ov a časových slotov
- **Registrácia študentov** — registračný formulár s výberom prednášok, e-mailové potvrdenie s tokenom
- **Správa registrácie** — aktivácia a zrušenie rezervácie cez unikátny token
- **Partneri/sponzori** — zobrazenie loga sponzorov s odkazmi
- **Kontakt** — kontaktné informácie
- **Vlastné stránky** — dynamicky vytvorené stránky cez WYSIWYG editor

### Administračný panel (pre organizátorov)
- **Dashboard** — prehľad modulov s rýchlym prístupom
- **Správa stage-ov** — CRUD operácie (vytvorenie, úprava, vymazanie) pre konferenčné sály/stage
- **Správa časových okien** — definovanie časových slotov pre prednášky
- **Správa prednášok** — priradenie prednášok k stage-om, rečníkom a časovým slotom
- **Správa speakerov** — CRUD operácie pre rečníkov vrátane fotografie a sociálnych sietí
- **Správa sponzorov** — CRUD operácie pre sponzorov/partnerov
- **Správa referencií (testimonials)** — CRUD operácie pre referencie
- **Správa vlastných stránok** — WYSIWYG editor pre vytváranie vlastných HTML stránok
- **Prehľad registrovaných študentov** — zoznam a správa registrácií

---

## Použité technológie

### Backend

| Technológia | Verzia
|---|---
| **PHP** | ^8.1
| **Laravel** | ^10.0 
| **Laravel Sanctum** | ^3.3 

### Frontend

| Technológia | Verzia 
|---|---
| **Vue.js** | ^3.4.23 | 
| **Vue Router** | ^4.3.2 
| **Pinia** | ^2.1.7 
| **Vuetify** | ^3.5.17 
| **Vue Quill** | ^1.2.0 
| **Axios** | ^1.6.
| **Vue Axios** | ^3.5.2 

---

## API Endpointy

### Autentifikácia

| Metóda | Endpoint | Popis |
|---|---|---|
| POST | `/api/register` | Registrácia nového admin účtu |
| POST | `/api/login` | Prihlásenie administrátora |
| POST | `/api/logout` | Odhlásenie |
| GET | `/api/authenticated` | Overenie, či je používateľ prihlásený |

### Sponzori

| Metóda | Endpoint | Popis |
|---|---|---|
| GET | `/api/sponsors` | Získanie zoznamu sponzorov |
| POST | `/api/sponsors` | Pridanie nového sponzora |
| PATCH | `/api/sponsors/{id}` | Úprava sponzora |
| DELETE | `/api/sponsors/{id}` | Vymazanie sponzora |

### Referencie (Testimonials)

| Metóda | Endpoint | Popis |
|---|---|---|
| GET | `/api/testimonials` | Získanie zoznamu referencií |
| POST | `/api/testimonials` | Pridanie novej referencie |
| PATCH | `/api/testimonials/{id}` | Úprava referencie |
| DELETE | `/api/testimonials/{id}` | Vymazanie referencie |

### Stage (Konferenčné sály)

| Metóda | Endpoint | Popis |
|---|---|---|
| GET | `/api/stages` | Získanie zoznamu stage-ov |
| POST | `/api/stages` | Vytvorenie nového stage |
| PATCH | `/api/stages/{id}` | Úprava stage |
| DELETE | `/api/stages/{id}` | Vymazanie stage |

### Program prednášok

| Metóda | Endpoint | Popis |
|---|---|---|
| GET | `/api/programs` | Získanie zoznamu prednášok |
| POST | `/api/programs` | Pridanie novej prednášky |
| PATCH | `/api/programs/{id}` | Úprava prednášky |
| DELETE | `/api/programs/{id}` | Vymazanie prednášky |

### Rečníci

| Metóda | Endpoint | Popis |
|---|---|---|
| GET | `/api/speakers` | Získanie zoznamu rečníkov |
| POST | `/api/speakers` | Pridanie nového rečníka |
| PATCH | `/api/speakers/{id}` | Úprava rečníka |
| DELETE | `/api/speakers/{id}` | Vymazanie rečníka |

### Časové sloty

| Metóda | Endpoint | Popis |
|---|---|---|
| GET | `/api/sloty` | Získanie zoznamu časových slotov |
| POST | `/api/sloty` | Pridanie nového slotu |
| PATCH | `/api/sloty/{id}` | Úprava slotu |
| DELETE | `/api/sloty/{id}` | Vymazanie slotu |

### Registrácia študentov

| Metóda | Endpoint | Popis |
|---|---|---|
| POST | `/api/ulozit-registraciu` | Odoslanie registračného formulára + e-mail |
| GET | `/api/student-data/{token}` | Aktivácia registrácie cez token |
| POST | `/api/student-data/{token}` | Zrušenie rezervácie |
| GET | `/api/students` | Získanie zoznamu registrovaných študentov |

### Vlastné stránky

| Metóda | Endpoint | Popis |
|---|---|---|
| GET | `/api/stranky` | Získanie zoznamu vlastných stránok |
| POST | `/api/stranky` | Vytvorenie novej stránky |
| PATCH | `/api/stranky/{id}` | Úprava stránky |
| DELETE | `/api/stranky/{id}` | Vymazanie stránky |

---

## Inštalácia a spustenie

### Požiadavky
- PHP >= 8.1
- Composer
- Node.js a npm
- MySQL databáza

### Kroky inštalácie

1. **Klonovanie repozitára**
   ```bash
   git clone https://github.com/PeterOpal/BT_semestralny_projekt.git
   cd BT_semestralny_projekt
   ```

2. **Inštalácia PHP závislostí**
   ```bash
   composer install
   ```

3. **Inštalácia JavaScript závislostí**
   ```bash
   npm install
   ```

4. **Konfigurácia prostredia**
   ```bash
   cp .env.example .env
   php artisan key:generate
   ```
   Upravte súbor `.env` 
   ```env
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=nazov_vasej_databazy
   DB_USERNAME=vas_pouzivatel
   DB_PASSWORD=vase_heslo
   ```

5. **Spustenie migrácií**
   ```bash
   php artisan migrate
   ```

6. **Spustenie vývojového servera**
   ```bash
   # V jednom termináli:
   php artisan serve

   # V druhom termináli:
   npm run dev
   ```

7. **Zostavenie pre produkciu**
   ```bash
   npm run build
   ```

---

## Architektúra aplikácie

Aplikácia je postavená na architektúre **SPA (Single Page Application)**:

- **Backend (Laravel)** slúži ako REST API server, ktorý spracúva všetky dátové operácie a autentifikáciu
- **Frontend (Vue.js)** beží ako SPA — všetky routy sú obsluhované cez jediný Blade template (`app.blade.php`), pričom Vue Router riadi navigáciu na strane klienta
- **Autentifikácia** je zabezpečená cez **Laravel Sanctum** (cookie-based SPA autentifikácia)
- **Stavový manažment** na frontende je riešený cez **Pinia** store moduly
- **UI komponenty** využívajú knižnicu **Vuetify 3** (Material Design)
- Komunikácia medzi frontendom a backendom prebieha cez **REST API** s použitím **Axios**

---

## Licencia

Tento projekt je postavený na frameworku Laravel, ktorý je licencovaný pod [MIT licenciou](https://opensource.org/licenses/MIT).
