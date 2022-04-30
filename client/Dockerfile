FROM node:alpine
WORKDIR /purchify
COPY package.json ./
COPY package-lock.json ./
COPY ./ ./
RUN npm i
EXPOSE 3000
CMD ["npm", "run", "start"]

# Command to build the container - make sure you are in the client folder. 
# docker build -f DockerFile -t client .

# Command to run the container on port 4001 - make sure you are in the client folder.
# docker run -it -p 4001:3000 client    
