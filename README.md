# ⚡ Verve — Localized Restaurant & WebApp Ecosystem

> *O‘zbekona ta’m, tez va mazali.* — A modern, high-performance web menu and automated Telegram bot ecosystem engineered for seamless digital dining and real-time order synchronization.

---

## 🌟 Overview

**Verve** bridges local restaurant dynamics with the Telegram WebApp framework. Built to deliver a smooth user experience, it pairs a localized, neon-styled interactive web interface (`telegramm.html`) with an asynchronous Python backend (`script2.py`).

The platform manages the complete ordering lifecycle: from rich menu interaction and dynamic beverage rows to real-time cart payloads and persistent order history logging.

---

## 🔥 Key Features

### 🎨 Frontend Web Application (`telegramm.html`)
* **Localized Cultural Branding**: Native Uzbek messaging (*"O‘zbekona ta’m, tez va mazali."*) designed to connect with regional dining preferences.
* **Interactive Menu Display**: Smooth visual displays featuring custom neon promotion lines and interactive beverage selection rows.
* **Telegram WebApp SDK Integration**: Native web container integration allowing clients to launch, select, and order directly inside Telegram without leaving their chat session.
* **Dynamic Payload Generation**: Automatically compiles customer cart choices, special instructions, and delivery preferences into a structured JSON payload.

### ⚡ Backend Engine & Telegram Bot (`script2.py`)
* **Asynchronous Event Handling**: Powered by Python asynchronous loops (`aiogram` / `python-telegram-bot`) to execute multi-user order queues with zero blocking delays.
* **Order Payload Receiver**: Webhook and polling endpoints that intercept incoming WebApp payloads, validate items, and confirm transaction integrity.
* **Order History Synchronization**: Real-time order state mapping (*Pending*, *Preparing*, *Out for Delivery*, *Completed*) synchronized with an active database backend.
* **Admin & Kitchen Alerts**: Instant notification triggers sent to restaurant staff channels upon new order placement.

---

## 🏗️ System Architecture

┌────────────────────────────────┐         ┌────────────────────────────────┐
│   Telegram Client (WebApp)     │         │   Python Backend (script2.py)  │
│                                │         │                                │
│   [ telegramm.html ]           │  JSON   │   • Async Event Loop           │
│   ├── Menu & Neon Banners      ├────────>│   • Order Validation          │
│   ├── Beverage Showcase Rows   │ Payload │   • Telegram Admin Alerts     │
│   └── WebApp JS SDK Action     │         │   • Order History Database     │
└────────────────────────────────┘         └────────────────────────────────┘


---

## 🛠️ Technology Stack

| Component | Technology | Description |
| :--- | :--- | :--- |
| **Frontend** | HTML5, CSS3, JavaScript | Modern, mobile-first responsive web view |
| **SDK** | Telegram WebApp JS SDK | Native container bridge for Telegram context |
| **Backend** | Python 3.x | Asynchronous core engine |
| **Bot Framework** | `aiogram` / `python-telegram-bot` | Telegram Bot API wrapper |
| **Database** | SQLite / Async Engine | Order history persistence and state tracking |
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# ⚡ Verve — Mahalliy Restoran & WebApp Ekotizimi

> *O‘zbekona ta’m, tez va mazali.* — Raqamli buyurtmalarni uzluksiz amalga oshirish va real vaqt rejimida buyurtmalarni sinxronlashtirish uchun mo'ljallangan zamonaviy, yuqori unumdorlikdagi veb-menyu va avtomatlashtirilgan Telegram bot ekotizimi.

---

## 🌟 Umumiy Ma'lumot

**Verve** mahalliy restoran dinamikasini Telegram WebApp ramkasi (framework) bilan bog'laydi. Foydalanuvchilarga qulay tajriba taqdim etish uchun u mahalliy, neon uslubidagi interaktiv veb-interfeysni (`telegramm.html`) asinxron Python backend'i (`script2.py`) bilan birlashtiradi.

Platforma buyurtma berish jarayonini boshidan oxirigacha boshqaradi: boy menyu ta'siridan tortib dinamik ichimliklar qatorigacha, real vaqtdagi savatcha ma'lumotlari va buyurtmalar tarixini doimiy saqlashni ta'minlaydi.

---

## 🔥 Asosiy Xususiyatlar

### 🎨 Frontend Veb-Ilovasi (`telegramm.html`)
- **Mahalliy Madaniy Brending**: Mintaqaviy taomlanish afzalliklariga moslashtirilgan milliy xabarlar (*"O‘zbekona ta’m, tez va mazali."*).
- **Interaktiv Menyu Ko'rinishi**: Maxsus neon aksiyalar qatorlari va interaktiv ichimliklar tanlash qatorlari bilan jihozlangan silliq vizual dizayn.
- **Telegram WebApp SDK Integratsiyasi**: Mijozlarga chat sessiyasidan chiqmagan holda to'g'ridan-to'g'ri Telegram ichida ishga tushirish, tanlash va buyurtma berish imkonini beruvchi veb-konteyner integratsiyasi.
- **Dinamik Ma'lumotlarni Yaratish**: Mijozning savatchadagi tanlovlarini, maxsus ko'rsatmalarini va yetkazib berish afzalliklarini tuzilmali JSON ma'lumotiga avtomatik ravishda yig'adi.

### ⚡ Backend Dvigateli & Telegram Bot (`script2.py`)
- **Asinxron Hodisalarni Boshqarish**: Hech qanday to'xtalishlarsiz ko'p foydalanuvchili buyurtma navbatlarini bajarish uchun Python asinxron sikllari (`aiogram` / `python-telegram-bot`) asosida ishlaydi.
- **Buyurtma Qabul Qiluvchi**: Kelayotgan WebApp ma'lumotlarini ushlab qoladigan, elementlarni tasdiqlaydigan va tranzaksiya yaxlitligini ta'minlaydigan vebhook va polling nuqtalari.
- **Buyurtmalar Tarixini Sinxronizatsiya Qilish**: Faol ma'lumotlar bazasi backend'i bilan sinxronlashtirilgan real vaqtdagi buyurtma holati xaritasi (*Kutilmoqda*, *Tayyorlanmoqda*, *Yetkazib berish uchun yo'lga chiqdi*, *Yakunlandi*).
- **Admin va Oshxona Ogohlantirishlari**: Yangi buyurtma berilganda restoran xodimlari kanallariga yuboriladigan zudlik bilan xabar berish mexanizmlari.

---

## 🏗️ Tizim Arxitekturasi

┌────────────────────────────────┐         ┌────────────────────────────────┐
│   Telegram Client (WebApp)     │         │   Python Backend (script2.py)  │
│                                │         │                                │
│   [ telegramm.html ]           │  JSON   │   • Async Event Loop           │
│   ├── Menu & Neon Banners      ├────────>│   • Order Validation          │
│   ├── Beverage Showcase Rows   │ Payload │   • Telegram Admin Alerts     │
│   └── WebApp JS SDK Action     │         │   • Order History Database     │
└────────────────────────────────┘         └────────────────────────────────┘

---

## 🛠️ Texnologiyalar Steki

| Komponent | Texnologiya | Tavsif |
| :--- | :--- | :--- |
| **Frontend** | HTML5, CSS3, JavaScript | Zamonaviy, mobil qurilmalarga moslashuvchan veb-ko'rinish |
| **SDK** | Telegram WebApp JS SDK | Telegram muhiti uchun mahalliy konteyner ko'prigi |
| **Backend** | Python 3.x | Asinxron asosiy dvigatel |
| **Bot Framework** | `aiogram` / `python-telegram-bot` | Telegram Bot API o'rash kutubxonasi |
| **Ma'lumotlar Bazasi** | SQLite / Async Engine | Buyurtmalar tarixini saqlash va holatni kuzatish |
