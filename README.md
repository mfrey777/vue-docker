=====================
Create new environment
=====================
in wsl:
cd ~/projects/
cp -a vue-docker new-app-name
cd new-app-name
sudo chown -R marcel .

=====================
Initial Setup vue.js
=====================
docker compose run --rm frontend /bin/bash
cd..
npm init vue@latest
app name needs to be "app"
...
cd app
npm install
exit
sudo chown -R marcel .
nano frontend/.devcontainer/devcontainer.json
update "name"
Ctrl+O / Ctrl+X
cd frontend
code . (then select "Reopen in container")

==========================
VSCode - remove Vue hints
==========================
Ctrl + Shift + P
User Settings (JSON)
add to file:
"volar.inlayHints.eventArgumentInInlineHandlers": false,

==================
Rebuld containers
==================
Force rebuild on an app image (frontend in this example):
docker-compose build --no-cache frontend

Rebuild container(frontend in this example):
docker-compose up --build --force-recreate --no-deps -d frontend