# API Endpointy

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
