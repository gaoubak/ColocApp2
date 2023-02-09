FROM node:11.13.0-alpine

RUN npm install -g nodemon
# create destination directory
WORKDIR /var/www/html/

# update and install dependency
RUN apk update && apk upgrade
RUN apk add git

ONBUILD RUN npm install
# expose 5000 on container
EXPOSE 5000

# set app serving to permissive / assigned
ENV NUXT_HOST=0.0.0.0
# set app port
ENV NUXT_PORT=5000

# start the app
CMD [ "npm", "start" ]