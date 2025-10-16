#Fase 1 : para construir los recuros /dependencias 
From node:20 as build

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

RUN  npm run  build

#Fase 2 : para construir la imagen

FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx","-g","daemon off;"]