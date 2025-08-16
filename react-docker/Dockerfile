FROM node:24-alpine

# Create app user
RUN addgroup app && adduser -S -G app app

# Set working directory
WORKDIR /app

# Copy package files first
COPY package*.json ./

# Switch to root for permissions
USER root

# Set correct ownership
RUN chown -R app:app .

# Switch back to app user
USER app

# Install dependencies
RUN npm install
# Install vite locally instead of globally
RUN npm install vite

# Copy application files
COPY . .

EXPOSE 5173

# Use npx to run vite
CMD ["npx", "vite", "--host"]


# run the docker container with the following command in cmd prompt
#docker run -it -p 5173:5173 -v "%cd%:/app" -v /app/node_modules -e CHOKIDAR_USEPOLLING=true --name react-container react-docker