# Backend Setup für Berkshire Buddy

## Quick Start

Das Backend ist jetzt vollständig auf GitHub mit allen Archives included!

### Option 1: Von GitHub klonen (einfach)

```bash
git clone https://github.com/MarkusA1A/berkshire-buddy-backend.git
cd berkshire-buddy-backend
python3 app_simple.py
```

**Fertig!** Server läuft auf http://localhost:8000

### Option 2: Lokal starten (wenn du einen Fork hast)

```bash
cd ~/openclaw/workspace/berkshire-buddy-backend
./start.sh
# oder
python3 app_simple.py
```

## API Endpunkte

Wenn Backend läuft:

```bash
# Suche
curl "http://localhost:8000/search?q=value+investing&limit=3"

# Statistiken
curl http://localhost:8000/stats

# Health-Check
curl http://localhost:8000/health
```

## Frontend & Backend verbinden

Die Berkshire Buddy App versucht automatisch, sich mit dem Backend zu verbinden:
- **Mit Backend:** Live-Suche in allen 48 Jahren ✅
- **Ohne Backend:** Demo-Mode mit 5 vordefinierten Antworten ⚠️

Um das Frontend zu updaten, editiere in `index.html`:
```javascript
const API_BASE = 'http://localhost:8000'; // Dein Backend
```

## Production Deployment

Das Backend kann auf jedem Python-Host deployed werden:

### Vercel (einfach)
```bash
# Mit vercel CLI
vercel --prod
```

### Railway / Heroku
```bash
# Mit Railway
railway up

# Mit Heroku
heroku create berkshire-buddy-api
git push heroku main
```

### Docker
```dockerfile
FROM python:3.11-slim
WORKDIR /app
COPY . .
CMD ["python3", "app_simple.py"]
```

## Architektur

```
berkshire-buddy-backend/
  ├── app_simple.py          # HTTP Server (0 Dependencies)
  ├── data/
  │   ├── berkshire-letters-archive.json     (48 Jahre)
  │   └── berkshire-shareholder-meetings.txt
  ├── README.md
  ├── SETUP.md
  └── start.sh
```

## Performance

- Archive: ~3,3 MB JSON + 2,1 KB Meetings
- Laden beim Start: ~2-3 Sekunden
- Suche pro Query: <100ms
- RAM: ~50-100 MB

## Troubleshooting

**"Archives nicht gefunden"**
- Check: `data/` Folder existiert im Verzeichnis
- Check: Beide Dateien da: `berkshire-letters-archive.json` + `berkshire-shareholder-meetings.txt`

**"Port 8000 bereits in Benutzung"**
```bash
# Port finden & killen
lsof -i :8000
kill -9 <PID>
```

**"API startet nicht"**
- Python 3.8+ erforderlich: `python3 --version`
- Keine externen Dependencies nötig
- Schau Logs: `python3 app_simple.py` (im Terminal)

## Nächste Schritte

1. ✅ Backend lokal testen
2. ✅ Frontend anpassen (API_BASE)
3. ⏳ (Optional) Production deployen
4. ⏳ (Optional) Semantic Search hinzufügen

---

**Alle Dateien inklusive Archives sind jetzt auf GitHub!** 🎉
