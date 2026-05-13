# Lexis — Synonym Finder 📖

A beautiful, fully functional synonym + meaning finder.  
**Docker image size: ~7MB** (nginx:alpine base)

## Features
- 🔍 Synonyms via **Datamuse API** (free, no API key)
- 📖 Meanings via **Free Dictionary API** (free, no API key)
- 🕘 Recent search history (localStorage)
- ⚡ Click any synonym chip to instantly look it up
- 📱 Fully responsive

## Quick Start

```bash
# Build
docker build -t lexis-app .

# Run
docker run -p 8080:80 lexis-app

# Visit
open http://localhost:8080
```

## Push to Registry

```bash
docker tag lexis-app yourusername/lexis-app:latest
docker push yourusername/lexis-app:latest
```

## Project Structure

```
synonymapp/
├── src/
│   └── index.html     ← entire app (HTML + CSS + JS)
├── nginx.conf         ← gzip + caching + SPA routing
├── Dockerfile         ← nginx:alpine, ~7MB
└── .dockerignore
```

## APIs Used (both free, no key needed)
- https://api.datamuse.com/words?rel_syn={word}
- https://api.dictionaryapi.dev/api/v2/entries/en/{word}
