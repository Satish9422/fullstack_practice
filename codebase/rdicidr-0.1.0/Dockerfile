FROM node:15 as builder

WORKDIR /app

COPY package*.json ./

RUN npm install --only=production

COPY . .  

RUN npm run build

FROM nginx:alpine AS production

# WORKDIR

COPY --from=builder /app/build /usr/share/nginx/html

EXPOSE 80
CMD ["nginx","-g","daemon off;"]
# RUN 

# ENTRYPOINT 