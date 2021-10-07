FROM node:14-alpine as build-step
WORKDIR /usr/src/app
COPY ["package.json", "package-lock.json*", "npm-shrinkwrap.json*", "./"]
RUN npm install
COPY . .
RUN ["npm", "run", "build"]


FROM nginx:1.20.1-alpine
EXPOSE 4200
COPY --from=build-step /usr/src/app/dist/AngularApp /usr/share/nginx/html



# FROM node:14-alpine as build-step
# WORKDIR /usr/src/app
# COPY ["package.json", "package-lock.json*", "npm-shrinkwrap.json*", "./"]
# RUN npm install
# COPY . .
# RUN ["npm", "run", "build"]

# RUN ["ls"]
# FROM nginx:1.20.1-alpine
# COPY --from=build-step /usr/src/app/dist/AngularApp /usr/share/nginx/html
