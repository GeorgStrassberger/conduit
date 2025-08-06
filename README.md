Frontend Angular
https://github.com/Developer-Akademie-GmbH/conduit-frontend.git

Backend Django
https://github.com/Developer-Akademie-GmbH/conduit-backend.git

---

## Projektstruktur (Beispiel)

```text
Modul7/						
├─ docker-compose.yml      	
├─ conduit-backend/       	
│  ├─ .env           	     
│  ├─ Dockerfile			
│  ├─ start.sh				
│  └─ ...					
└─ conduit-frontend/      	
   ├─ Dockerfile			
   └─ ...					
```							

---

## Projekt Starten

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
- Frontend: http://localhost:8082

---

## Author

```text

  ██████╗   ███████╗   ███████╗  █████████╗
 ██╔════╝   ██╔════╝  ██╔═════╝  ╚══██╔═══╝
 ██║  ███╗  █████╗    ╚█████╗       ██║
 ██║   ██║  ██╔══╝     ╚═══██╗      ██║
 ██║   ██║  ██║             ██╗     ██║
 ╚██████╔╝  ███████╗   ███████║     ██║
  ╚═════╝   ╚══════╝   ╚══════╝     ╚═╝
```

