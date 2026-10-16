# 🤖 Discord AI Server Builder & Manager Bot

Zaawansowany bot w **Node.js (discord.js v14)** zintegrowany z **OpenAI API (GPT-4o / GPT-4o-mini)**, który automatycznie tworzy kompletne, w pełni skonfigurowane serwery Discord na podstawie jednego opisu, a także zarządza nimi (powitania, tickety, moderacja AI, szablony).

---

## ✨ Kluczowe Funkcje i Ulepszenia

1. **🚀 AI Server Builder (`/buildserver`)**:
   - Generuje pełną strukturę kategorii, kanałów tekstowych, kanałów głosowych i ról z kolorami HEX.
   - **Uprawnienia i Bezpieczeństwo**: Automatycznie blokuje dostęp zwykłym użytkownikom do kategorii administracyjnych.
   - **Rate Limiting & Safety**: Zabezpieczony przed przekroczeniem limitów API Discorda (opóźnienia między zapytaniami).
   - **Logowanie zdarzeń**: Automatycznie tworzy dedykowany kanał `#logs-bot` do raportowania akcji.

2. **📋 Szablony Serwerów (`/template`)**:
   - Szybkie budowanie bez zużywania API OpenAI z gotowych szablonów JSON (`Gaming`, `Community`, `Coding`).

3. **🎫 System Ticketów (Wsparcie)**:
   - Interaktywne przyciski Discorda.
   - Tworzenie prywatnych kanałów pomocy technicznej z pełnymi uprawnieniami dla zgłaszającego.
   - Przycisk **Zamknij Ticket** (`🔒 Zamknij`) do automatycznego usuwania obsłużonego zgłoszenia.

4. **👋 System Powitań & Autorola**:
   - Wysyłanie spersonalizowanych wiadomości powitalnych.
   - Automatyczne przyznawanie podstawowej roli nowym członkom.

5. **🛡️ Moderacja AI w Czasie Rzeczywistym**:
   - Wykorzystuje bezpłatny i szybki model **OpenAI Moderation API**.
   - Wykrywa hejt, groźby, wulgaryzmy i auto-usuwa niebezpieczne wiadomości z ostrzeżeniem dla użytkownika.

---

## 🛠️ Instrukcja Krok po Kroku

### Krok 1: Wymagania
- Node.js w wersji **v18+** lub **v20+**.

### Krok 2: Instalacja zależności
Wypakuj archiwum ZIP, otwórz terminal w folderze projektu i uruchom:
```bash
npm install
```

### Krok 3: Konfiguracja `.env`
Utwórz plik `.env` w głównym folderze (możesz skopiować `.env.example`) i uzupełnij klucze:
```env
DISCORD_TOKEN=twój_token_bot
CLIENT_ID=id_aplikacji_discord
OPENAI_API_KEY=sk-proj-...
```

> ⚠️ **NIGDY nie udostępniaj pliku `.env` ani nie commituj go do Git!**

### Krok 4: Uruchomienie bota
```bash
npm start
```

---

## 🌐 Hosting 24/7 (PM2 / VPS / Cloud)

### Uruchomienie przez PM2 na VPS:
```bash
npm install -g pm2
pm2 start src/index.js --name "discord-ai-bot"
pm2 save
pm2 startup
```

### Uruchomienie na Render.com / Railway / Fly.io:
1. Wgraj projekt do prywatnego repozytorium GitHub (upewnij się, że `.env` jest w `.gitignore`).
2. Dodaj nowe środowisko w panelu hostingu i ustaw zmienne środowiskowe (`DISCORD_TOKEN`, `CLIENT_ID`, `OPENAI_API_KEY`).
3. Ustaw komendę startową: `npm start`.
