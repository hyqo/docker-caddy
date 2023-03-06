ARG CADDY_VERSION
FROM caddy:${CADDY_VERSION}-builder-alpine AS app_caddy_builder

RUN xcaddy build \
	--with github.com/caddy-dns/cloudflare


FROM caddy:${CADDY_VERSION}-alpine

WORKDIR /app

COPY --from=app_caddy_builder --link /usr/bin/caddy /usr/bin/caddy
