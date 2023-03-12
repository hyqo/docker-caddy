ARG CADDY_VERSION
FROM caddy:${CADDY_VERSION}-builder-alpine AS app_caddy_builder

RUN xcaddy build \
	--with github.com/caddy-dns/cloudflare \
    --with github.com/dunglas/mercure \
	--with github.com/dunglas/mercure/caddy

FROM caddy:${CADDY_VERSION}-alpine

WORKDIR /app

COPY --from=app_caddy_builder --link /usr/bin/caddy /usr/bin/caddy
