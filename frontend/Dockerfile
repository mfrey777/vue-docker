FROM mcr.microsoft.com/vscode/devcontainers/javascript-node:18

RUN npm install -g http-server @vue/cli @vue/cli-service-global
WORKDIR /myapp/app

EXPOSE 5173

CMD [ "npm", "run", "dev", "--","--host", "0.0.0.0" ]