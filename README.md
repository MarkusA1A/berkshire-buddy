# 🤖 Berkshire Buddy – Investment Coach

Dein persönlicher Investment-Coach powered by Warren Buffett & Charlie Munger.

**Live:** https://markusa1a.github.io/berkshire-buddy/

## Was ist das?

Berkshire Buddy ist eine interaktive App, die auf den echten Erkenntnissen und Zitaten von Warren Buffett und Charlie Munger basiert. Stelle eine Frage zu Investitionen, und der Coach antwortet mit bewährter Wisdom aus Jahrzehnten.

### Die Datenquellen

- **Berkshire Hathaway Shareholder Letters** (1977–2024, 48 Jahre)
- **Berkshire Hathaway Shareholder Meetings** (Q&A, wörtliche Zitate)
- **Klassische Investment-Konzepte** (Graham, Dodd, Value Investing)

### Für wen?

- Investment-Anfänger, die verstehen möchten, wie man richtig investiert
- Erfahrene Investoren, die sich durch bewährte Prinzipien leiten lassen
- Alle, die Buffetts und Mungers Philosophie kennenlernen möchten

## Features

✅ Interaktive Fragen & Antworten  
✅ Direkte Zitate aus offiziellen Quellen  
✅ Einfache, verständliche Erklärungen  
✅ Mobile-responsive Design  
✅ Zero Dependencies – pure HTML/CSS/JS  

## Technisch

- **Frontend:** HTML5, Vanilla JavaScript, CSS3
- **Hosting:** GitHub Pages
- **Design:** Minimalistisch, inspiriert von "Aktienmarkt-Downturns" Theme

### Lokal starten

```bash
# Einfach index.html im Browser öffnen
open index.html

# Oder mit Python HTTP Server
python3 -m http.server 8000
# → http://localhost:8000
```

### Entwicklung

Die Fragen sind aktuell hardcoded in `index.html` (im `responses` Objekt). 

**Zukünftige Erweiterung:** Integration mit echtem Backend, das die vollständigen Archives (`berkshire-letters-archive.json`, `berkshire-shareholder-meetings.txt`) durchsucht.

## Lizenz

MIT License – siehe LICENSE für Details

## Autor

© Markus O. Thalhamer  
mthalhamer@thalhamer.com

---

**Disclaimer:** Privates Projekt. Keine Gewährleistung für die Korrektheit oder Vollständigkeit der Ergebnisse. Dies ist keine Finanzberatung.
