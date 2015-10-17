# NVM

A base docker image with a node version manager and a pg client installed.


## How to use it

```
FROM livingdocs/nvm

# app specific npm & node version
ADD ./.nvmrc /app/.nvmrc
RUN bash -c '. /usr/share/nvm/nvm.sh && cd /app && nvm install && nvm alias default'

# app installation
WORKDIR /app
ADD ./ /app
RUN npm install

ENV PORT 8080
EXPOSE 8080
CMD ["node index.js"]
```
