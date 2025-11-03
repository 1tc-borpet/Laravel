# Laravel telepítése – Lépésről lépésre útmutató

## 1. Előfeltételek

A Laravel telepítéséhez az alábbi programokra lesz szükség:

- PHP 8.1 vagy újabb
- Composer (PHP csomagkezelő)
- Webszerver (pl. Apache vagy Nginx)
- Adatbázis (pl. MySQL, MariaDB, PostgreSQL)
- Git (ajánlott)

Ellenőrizd a verziókat a következő parancsokkal:
```bash
php -v
composer -V
git --version
```

---

## 2. PHP telepítése

### Windows
Töltsd le a PHP-t a hivatalos oldalról:  
[https://windows.php.net/download/](https://windows.php.net/download/)

### Linux / macOS
Telepítés terminálból:
```bash
sudo apt install php php-cli php-mbstring unzip curl
```
vagy macOS esetén:
```bash
brew install php
```

Telepítés ellenőrzése:
```bash
php -v
```

---

## 3. Composer telepítése

A Composer a Laravel függőségeinek kezelésére szolgál.

### Windows
Látogasd meg: [https://getcomposer.org/download/](https://getcomposer.org/download/)  
Töltsd le és futtasd a Composer-Setup.exe fájlt.


Ellenőrzés:
```bash
composer -V
```

---

## 4. Laravel letöltése és telepítése

A Laravel projekt legegyszerűbben Composer segítségével hozható létre.

```bash
composer create-project laravel/laravel projekt_neve
```

Ez letölti és telepíti a Laravel teljes forráskódját és függőségeit a megadott mappába.

---

## 5. Fejlesztői szerver indítása

Lépj be a projekt mappájába:
```bash
cd projekt_neve
```

Indítsd el a Laravel beépített fejlesztői szerverét:
```bash
php artisan serve
```

Ha minden rendben működik, a terminálban ezt látod:
```
Starting Laravel development server: http://127.0.0.1:8000
```

A böngészőben megnyitva elérhető a projekt:  
[http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## 6. Környezeti beállítások (.env fájl)

A Laravel beállításai az `.env` fájlban találhatók.

Példa konfiguráció:
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

Ha az APP_KEY üres, generáld újra:
```bash
php artisan key:generate
```

---

## 7. Adatbázis migrációk futtatása

A Laravel tartalmaz alapértelmezett adatbázis migrációkat.  
Futtatásukhoz használd az alábbi parancsot:
```bash
php artisan migrate
```

Ha az adatbázis még nem létezik, hozd létre manuálisan (például phpMyAdmin segítségével), majd futtasd újra a parancsot.

---

## 8. Laravel Installer használata (opcionális)

Ha gyakran hozol létre új Laravel projekteket, érdemes telepíteni a Laravel Installer-t:

```bash
composer global require laravel/installer
```

Ezután új projektet így hozhatsz létre:
```bash
laravel new projekt_neve
```

---

## 9. Gyakori hibák és megoldások

**Hiba:** Class "PDO" not found  
Megoldás: Telepítsd a PHP PDO bővítményt.

**Hiba:** APP_KEY is missing  
Megoldás: Futtasd a `php artisan key:generate` parancsot.

**Hiba:** Adatbázis kapcsolat hiba  
Megoldás: Ellenőrizd az `.env` fájlban lévő adatbázis beállításokat.

---
