FROM node:14-alpine
# Set the working directory in the container
WORKDIR /app
# Copy package.json and package-lock.json to the working directory
COPY package*.json ./
# Install dependencies
RUN npm install
# Copy the rest of the application code
COPY . .
# Build the React app
RUN npm run build
# Serve the React app using a lightweight HTTP server (nginx)
RUN npm install -g serve
# Expose port 80 to the outside world
EXPOSE 80
# Serve the built React app
CMD ["serve", "-s", "build", "-l", "80"]
