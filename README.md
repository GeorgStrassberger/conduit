Frontend Angular
https://github.com/Developer-Akademie-GmbH/conduit-frontend.git

Backend Django
https://github.com/Developer-Akademie-GmbH/conduit-backend.git

---

## Projektstruktur (Beispiel)

```lua
Modul7/
├─ docker-compose.yml      <-- eine Ebene höher
├─ .env                    <-- auch hier
├─ conduit-backend/        <-- Django Backend
│  ├─ Dockerfile
│  ├─ start.sh
│  └─ ...
└─ conduit-frontend/       <-- Angular Frontend
   ├─ Dockerfile
   └─ ...
```

---

🔹 Starten

Compose Build
```bash
docker-compose build
```

Beide Services starten
```bash
docker-compose up
```

Zugriff
- Backend: http://localhost:7000
- Frontend: http://localhost:4200


---

