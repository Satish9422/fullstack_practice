FROM node:15 as builder

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .  

RUN npm run build

FROM nginx:alpine AS production

# WORKDIR

COPY --from=builder /app/build /usr/share/nginx/html
CMD ["nginx","-g","daemon 0ff;"]
# RUN 

# ENTRYPOINT 