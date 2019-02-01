FROM node:11.5-alpine

RUN mkdir -p /usr/src/admin

WORKDIR /usr/src/admin

RUN apk add --no-cache --virtual .gyp \
        python \
        make \
        g++

# Prevent the reinstallation of node modules at every changes in the source code
COPY . ./
RUN yarn install \
	&& apk del .gyp

CMD yarn start
