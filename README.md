# Conduit Project (Dockerized Fullstack App)

A fullstack Conduit application:
- **Frontend**: Angular – [conduit-frontend](https://github.com/Developer-Akademie-GmbH/conduit-frontend.git)
- **Backend**: Django – [conduit-backend](https://github.com/Developer-Akademie-GmbH/conduit-backend.git)

---

## Table of Contents

- [Conduit Project (Dockerized Fullstack App)](#conduit-project-dockerized-fullstack-app)
  - [Table of Contents](#table-of-contents)
  - [Project Structure](#project-structure)
  - [Quickstart](#quickstart)
  - [Start the App](#start-the-app)
  - [Usage](#usage)
  - [Author](#author)


## Project Structure

```text
conduit/						
├─ docker-compose.yml     
├─ Conduit_Container_Checkliste.pdf  
├─ .dockerignore 
├─ .gitignore 
├─ .gitmodules
├─ conduit-backend/       	
│  ├─ .env           	     
│  ├─ Dockerfile			
│  ├─ start.sh				
│  └─ ...					
└─ conduit-frontend/      	
   ├─ Dockerfile		
   ├─ src/   
   │  ├─ environments/   
   │  │  └─ environment.development.ts
   │  └─ ...
   └─ ...					

```

## Quickstart

1. Clone the fullstack project with submodules:

```bash
git clone --recurse-submodules https://github.com/GeorgStrassberger/conduit.git
cd conduit
```

2. Update frontend submodule:
```bash
cd conduit-frontend
git checkout docker
git pull origin docker
```

3. Update backend submodule:
```bash
cd ../conduit-backend
git checkout docker
git pull origin docker
```

4. Backend .env Setup

    Inside `conduit-backend/`:

    ```bash
    cp .env.example .env
    nano .env
    ```

    Edit your environment variables:

    ```text
    # DJANGO SUPERUSER
    DJANGO_SUPERUSER_EMAIL=admin@example.com    # <- change
    DJANGO_SUPERUSER_NAME=admin                 # <- change
    DJANGO_SUPERUSER_PASSWORD=adminpass         # <- change

    # SECURITY
    SECRET_KEY=your-django-secret-key           # <- change
    DEBUG=True
    ALLOWED_HOSTS=localhost,127.0.0.1           # <- change

    # CORS
    ALLOWED_ORIGIN=http://127.0.0.1:8082        # <- change
    ```
    Save & Exit: `CTRL + O`, then `CTRL + X`

5. Frontend Environment Setup

    Inside `conduit-frontend/src/environments/`:

    ```bash
    cp environment.development.ts environment.ts
    nano environment.ts
    ```

    Edit as needed:

    ```text
    export const environment = {
      production: true,                          // set to TRUE
      apiUrl: "http://localhost:7000/api",       // your host-ipv4
    };
    ```
    Save & Exit: `CTRL + O`, then `CTRL + X`

## Start the App

Go back to root directory `conduit`:
```bash
cd ../../..
```

Build containers:
```bash
docker compose build
```

Run services:
```bash
docker compose up -d
```

Verify that containers are running:
```bash
docker ps
```

You should see output like this:
```bash
CONTAINER ID   IMAGE                  COMMAND                  STATUS         PORTS
abcd1234       conduit-backend        "gunicorn ..."           Up 10 seconds  0.0.0.0:7000->7000/tcp
efgh5678       conduit-frontend       "nginx -g ..."           Up 10 seconds  0.0.0.0:8082->80/tcp
```

## Usage
- Backend: http://localhost:7000/admin
- Frontend: http://localhost:8082

Replace `localhost` with your local IP if needed.


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
