# GitHub Poradnik — Heuristica

Statyczna strona edukacyjna z poradnikiem pracy na GitHub dla początkujących. Zbudowana jako pojedynczy plik HTML, bez frameworków i zależności.

## Co zawiera

- **10 porad** z opisem i infografikami SVG — od inicjalizacji repo po SSH keys
- **Ściągawka komend** — 9 kategorii (Git + PowerShell), kliknięcie kopiuje komendę do schowka
- **Widget czatu** — floating button połączony z agentem n8n przez webhook

## Stack

- Vanilla HTML/CSS/JS — zero zależności frontendowych
- Fonty: Fraunces + DM Mono + Instrument Sans (Google Fonts)
- Infografiki: inline SVG
- Backend czatu: n8n webhook (`n8n.heuristica.pl`)

## Uruchomienie

Otwórz `github-guide.html` bezpośrednio w przeglądarce — nie wymaga serwera.

Dla lokalnego serwera (opcjonalnie):

```bash
npx serve .
# lub
python -m http.server 8080
```

## Webhook czatu

Adres webhooka n8n w pliku HTML (sekcja `CHAT WIDGET`):

```
https://n8n.heuristica.pl/webhook/64df11bf-222e-4673-9be9-8d8dec78d05a/chat
```

Payload wysyłany do n8n:
```json
{ "chatInput": "wiadomość użytkownika", "sessionId": "unikalny-id-sesji" }
```

Oczekiwana odpowiedź: `{ "output": "..." }` lub `{ "text": "..." }`.

## Struktura

```
.
├── github-guide.html   # cały projekt w jednym pliku
└── README.md
```

## Autor

[Heuristica](https://heuristica.pl) — AI consulting & education
