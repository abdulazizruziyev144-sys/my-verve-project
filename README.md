# ⚡ Verve — Mahalliy Restoran & WebApp Ekotizimi

> *O‘zbekona ta’m, tez va mazali.* — Zamonaviy raqamli buyurtma tizimi hamda real vaqtda buyurtmalarni sinxronlashtirishga mo'ljallangan yuqori unumdorlikka ega veb-menyu va Telegram bot ekotizimi.

---

## 🌟 Umumiy Ma'lumot (Overview)

**Verve** mahalliy restoran dinamikasini Telegram WebApp imkoniyatlari bilan birlashtiradi. Foydalanuvchilarga qulay va tezkor xizmat ko'rsatish uchun interaktiv veb-interfeys (`telegramm.html`) va asinxron Python backend-serveri (`script2.py`) mukammal bog'langan.

Platforma buyurtmalarni to'liq boshqaradi: boy menyu ko'rinishi va neon bannerlardan tortib, real vaqt rejimidagi savatcha (cart) ma'lumotlari hamda buyurtmalar tarixini saqlashgacha.

---

## 🔥 Asosiy Imkoniyatlar (Features)

### 🎨 Frontend Veb-Ilovasi (`telegramm.html`)
* **Mahalliy Brending**: Mahalliy mijozlarga moslashtirilgan milliy chaqiriq (*"O‘zbekona ta’m, tez va mazali."*).
* **Interaktiv Menyu**: Neon uslubidagi promo-qatorlar va ichimliklar uchun qulay tanlov kartalari.
* **Telegram WebApp SDK B интеграatsiyasi**: Mijozlar Telegram ilovasidan chiqmagan holda bevosita menyuni ochishi va buyurtma berishi mumkin.
* **Dinamik Ma'lumot Yuborish**: Mijoz tanlagan taomlar, maxsus istaklar va yetkazib berish ma'lumotlarini tuzilmali JSON shaklida to'playdi.

### ⚡ Backend Bot Dvigateli (`script2.py`)
* **Asinxron Hodisalarni Boshqarish**: Python asinxron sikllari (`aiogram` / `python-telegram-bot`) yordamida ko'p sonli foydalanuvchilar buyurtmalarini ushlanib qolishlarsiz qabul qiladi.
* **Buyurtma Qabul Qiluvchi (Payload Receiver)**: WebApp'dan keladigan buyurtma ma'lumotlarini qabul qiladi, tekshiradi va tasdiqlaydi.
* **Buyurtmalar Tarixini Sinxronlash**: Real vaqtdagi buyurtma holatlarini (*Kutilmoqda*, *Tayyorlanmoqda*, *Yo'lda*, *Yakunlandi*) ma'lumotlar bazasi bilan moslashtiradi.
* **Oshpaz va Admin Bildirishnomalari**: Yangi buyurtma tushganda restoran xodimlari guruhiga zudlik bilan xabar yuboradi.

---

## 🏗️ Tizim Arxitekturasi
