FROM node:24-alpine
# RUN addgroup app && adduser -S -G app app
# USER app
WORKDIR /app
COPY package*.json ./
# USER root
# RUN chown -R app:app .
# USER app
RUN npm install
RUN npm install vite
COPY . .
EXPOSE 5173
CMD ["npx", "vite", "--host"]

