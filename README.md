# 📦 Inventory Management System v2.0

Sistem za upravljanje inventarom — statički frontend sa Supabase bazom podataka, hostujen na Vercel.

## Funkcionalnosti

- **Kontrolna tabla** — Statistike, upozorenja za niske zalihe, poslednje promene
- **Proizvodi** — CRUD operacije, pretraga, filtriranje po kategoriji i stanju
- **Kategorije** — Dodavanje i brisanje kategorija
- **Excel Import** — Uvoz proizvoda iz .xlsx/.csv sa automatskim mapiranjem kolona
- **Izveštaji** — Vrednost po kategorijama, profit, top artikli, promet za 30 dana
- **Praćenje zaliha** — Ulaz, izlaz, korekcija sa istorijom

## Tech Stack

- **Frontend**: Vanilla HTML/CSS/JS (Single Page App)
- **Baza**: Supabase (PostgreSQL)
- **Hosting**: Vercel (statički sajt)
- **Excel**: SheetJS (XLSX) — klijentsko parsiranje

## Deploy na Vercel

### 1. Push na GitHub

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/TVOJ-USERNAME/inventory-management.git
git branch -M main
git push -u origin main
```

### 2. Poveži sa Vercel

1. Idi na [vercel.com](https://vercel.com)
2. Klikni **"Add New Project"**
3. Importuj GitHub repo `inventory-management`
4. Framework Preset: **Other**
5. Klikni **Deploy**

To je to! Vercel će automatski deployovati sajt i dati ti URL.

### 3. Automatski deploy

Svaki `git push` na `main` branch automatski triggeruje novi deploy na Vercel.

## Supabase tabele

Tabele su prefixovane sa `inv_` da se razdvoje od ostalih projekata:

- `inv_categories` — kategorije proizvoda
- `inv_products` — proizvodi sa cenama, zalihama, lokacijom
- `inv_stock_movements` — istorija promena stanja (ulaz/izlaz/korekcija)

## Excel Import format

Fajl treba da ima header red. Podržani formati: `.xlsx`, `.xls`, `.csv`

Minimalni kolone:
- **Naziv** (name, naziv, proizvod, artikal...)
- **SKU** (sku, šifra, kod, barcode...)

Opcione kolone: kategorija, cena, nabavna, količina, lokacija, dobavljač, opis

Sistem automatski prepoznaje nazive kolona na srpskom i engleskom.
