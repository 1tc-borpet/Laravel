# Laravel telepítése – Lépésről lépésre útmutató

## Előfeltételek

Mielőtt elkezdenéd a telepítést, győződj meg róla, hogy az alábbi programok telepítve vannak:

- **PHP 8.1 vagy újabb**
- **Composer** (PHP csomagkezelő)
- **Webszerver** (pl. Apache vagy Nginx)
- **Adatbázis** (pl. MySQL, MariaDB, PostgreSQL)
- **Git** (ajánlott)

Ellenőrizd a verziókat:
```bash
php -v
composer -V
git --version
```

---

## 🪄 1. Laravel projekt létrehozása

A legegyszerűbb módja a telepítésnek a Composer használata.

```bash
composer create-project laravel/laravel projekt_neve
```

Ez létrehoz egy új mappát a megadott névvel, és telepíti a Laravel összes függőségét.

Alternatív megoldásként, ha már van globálisan telepített Laravel parancssorod:
```bash
laravel new projekt_neve
```

---

## ⚙️ 2. Fejlesztői szerver indítása

Lépj be a projekt mappájába:
```bash
cd projekt_neve
```

Indítsd el a beépített fejlesztői szervert:
```bash
php artisan serve
```

Ha minden rendben, a konzolban ilyet látsz:
```
Starting Laravel development server: http://127.0.0.1:8000
```

Ezután a böngészőben nyisd meg:  
[http://127.0.0.1:8000](http://127.0.0.1:8000)

---

##  3. Környezeti beállítások

A Laravel környezeti változóit az `.env` fájl tartalmazza.

Példa beállítások:
```env
APP_NAME=Laravel
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://127.0.0.1:8000

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=adatbazis_neve
DB_USERNAME=root
DB_PASSWORD=
```

Ha az `APP_KEY` üres, generáld le:
```bash
php artisan key:generate
```

---

##  4. Adatbázis migrációk futtatása

A Laravel alapértelmezett migrációkkal érkezik.  
Ezek futtatásához:
```bash
php artisan migrate
```

Ha az adatbázis nincs létrehozva, hozd létre manuálisan (pl. phpMyAdmin-ban), majd futtasd újra a parancsot.

---

##  5. Hasznos Artisan parancsok

| Parancs | Funkció |
|----------|----------|
| `php artisan serve` | Fejlesztői szerver indítása |
| `php artisan migrate` | Migrációk futtatása |
| `php artisan make:model` | Új modell létrehozása |
| `php artisan make:controller` | Új vezérlő létrehozása |
| `php artisan route:list` | Elérhető útvonalak listázása |

---

##  6. Gyakori hibák és megoldások

**Hiba:** `Class "PDO" not found`  
 Telepítsd a PHP PDO bővítményt.

**Hiba:** `APP_KEY is missing`  
 Futtasd: `php artisan key:generate`

**Hiba:** Adatbázis kapcsolat hiba  
 Ellenőrizd az `.env` fájl DB_* beállításait.

---

