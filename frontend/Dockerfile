# Build environment
FROM node as builder

RUN mkdir /usr/src/app
WORKDIR /usr/src/app
ENV PATH /usr/src/app/node_modules/.bin:$PATH
COPY package.json /usr/src/app/package.json

RUN npm install --verbose

COPY . /usr/src/app

RUN npm run-script build

# Production environment
FROM caddy:2.0.0

RUN mkdir -p /usr/share/caddy/html/build
RUN mkdir -p /usr/share/caddy/html/css
RUN mkdir -p /usr/share/caddy/html/js
RUN mkdir -p /usr/share/caddy/html/img

COPY --from=builder /usr/src/app/build /usr/share/caddy/html

# Prod
COPY --from=builder /usr/src/app/Caddyfile /etc/caddy/Caddyfile

EXPOSE 80
EXPOSE 443

