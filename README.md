# 🧑🏻‍🚀 NFCtron Frontend Case Study (Seating, 2024)

>Vítejte u našeho testovacího zadání pro kandidáty na pozici **React Frontend Developer** v NFCtron! Vaším úkolem bude
dokončit jednoduchou React aplikaci pro nákup vstupenek na konkrétní akci.

## 🎟 Úvod do Aplikace

Předpřipravili jsme pro vás základ aplikace s přednastavenými nástroji a layoutem. Zároveň aplikace disponuje připravenými [API endpointy](#api-endpointy), které budou potřebné pro získávání potřebných dat.

**➡️ Vaší úlohou bude aplikaci funkčně dokončit.**

![Base Layout](./base-layout.png)

## 🌱 Požadavky na Funkčnost

Aplikace by měla být schopna:

- [ ] Zobrazit onepage detail akce s relevantními údaji z API (obrázek, název, popis, datum, ...)
- [ ] Zobrazit seznam dostupných sedadel (řada, sedadlo) z API.
- [ ] Přidat/odebrat místo se vstupenkou do/z košíku.
- [ ] Spravovat obsah košíku s využitím promyšleného state managementu.
- [ ] Zobrazit aktuální počet vstupenek v košíku a jejich celkovou hodnotu (ve správné měně a formátu).
- [ ] Po kliknutí na "Koupit vstupenky" umožnit přihlášení nebo vyplnění potřebných údajů jako "host".
- [ ] Vytvořit objednávku skrze API a zobrazit výsledek (úspěch nebo chybu).

## 🎁 Bonusové Funkce
- Umožnit přidání akce do kalendáře.
- Multijazyčnost aplikace.
- Dalším vychytávkám se meze nekladou!

## Kritéria Hodnocení 📋

- Funkčnost a splnění funkčních požadavků.
- Vzhled aplikace a responzivitu na mobilních zařízeních.
- Práci s daty a state management.
- Kvalitu, strukturu a komentování kódu.
- Práci s Git.

## Jak začít 🏁

1. Naklonujte si tento repozitář.
2. Nastavte si své vývojové prostředí.
3. Vypracujte toto zadání.
4. Otestujte svou aplikaci.
5. Průběžně commitujte a pushujte své změny.
6. Po dokončení úkolu nám pošlete odkaz na Váš repozitář.

## API Endpointy

Potřebné API je dostupné na adrese `https://nfctron-frontend-seating-case-study-2024.vercel.app` a obsahuje následující
endpointy:

### Informace o akci
Endpoint: `GET:/event`

Odpověď:
```json
{
  "eventId": "uuid",
  "namePub": "string",
  "description": "string",
  "currencyIso": "string",
  "dateFrom": "datetime",
  "dateTo": "datetime",
  "headerImageUrl": "string",
  "place": "string"
}
```

### Vstupenky a místa k sezení na akci
Endpoint: `GET:/event-tickets?eventId=<uuid>`

Odpověď:
```json
{
  "ticketTypes": [
    {
      "id": "uuid",
      "name": "string",
      "price": 0
    }
  ],
  "seatRows": [
    {
      "seatRow": 1,
      "seats": [
        {
          "seatId": "uuid",
          "place": 1,
          "ticketTypeId": "uuid"
        }
      ]
    }
  ]
}
```

### Testovací login
Endpoint: `POST:/login`

> Použijte email: `frontend@nfctron.com` a heslo: `Nfctron2025`

Vstup:
```json
{
  "email": "string",
  "password": "string"
}
```

Odpověď:

```json
{
  "message": "string",
  "user": {
    "firstName": "string",
    "lastName": "string",
    "email": "string"
  }
}
```

### Vytvoření objednávky
Endpoint: `POST:/order`

Vstup:
```json
{
  "eventId": "uuid",
  "tickets": [
    {
      "ticketTypeId": "uuid",
      "seatId": "uuid"
    }
  ],
  "user": {
    "email": "string",
    "firstName": "string",
    "lastName": "string"
  }
}
```

Odpověď:

```json
{
  "message": "string",
  "orderId": "uuid",
  "tickets": [],
  "user": {
    "email": "string",
    "firstName": "string",
    "lastName": "string"
  },
  "totalAmount": 0
}
```

## Podpora 🆘

Máte-li jakékoli dotazy nebo potřebujete pomoci, neváhejte se na nás obrátit.

---

Přejeme vám hodně štěstí a těšíme se na vaše řešení! 🌟

_–– Tým NFCtron_
