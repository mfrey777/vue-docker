# Create new environment

cd ~/projects/  

in wsl:
cp -a vue-docker new-app-name  
cd new-app-name  
sudo chown -R marcel .  

or add to existing environment:  
cp -a vue-docker/frontend existing-repo/frontend  
Manually add frontend service in existsing docker-compose file

# Initial Setup vue.js

in docker-compose.yml:  
comment out line (add a "#" in front):  - node_modules:/myapp/app/node_modules  

docker compose run --rm frontend /bin/bash  
cd..  
npm init vue@latest  
app name needs to be "app"  
...  
exit

in docker-compose.yml:  
activate line(remove a "#" in front):  - node_modules:/myapp/app/node_modul

docker compose run --rm frontend /bin/bash  

npm install  
exit  
sudo chown -R marcel .  
nano frontend/.devcontainer/devcontainer.json  
update "name"  
Ctrl+O / Ctrl+X  
cd frontend  
code . (then select "Reopen in container")


# VSCode - remove Vue hints
Ctrl + Shift + P  
User Settings (JSON)  
add to file:  
"volar.inlayHints.eventArgumentInInlineHandlers": false,

# Rebuld containers

Force rebuild on an app image (frontend in this example):  
docker-compose build --no-cache frontend  

Rebuild container(frontend in this example):  
docker-compose up --build --force-recreate --no-deps -d frontend