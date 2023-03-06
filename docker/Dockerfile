ARG CADDY_VERSION
FROM caddy:${NGINX_VERSION}-builder-alpine AS app_caddy_builder

RUN xcaddy build \
	--with github.com/caddy-dns/cloudflare


FROM caddy:${NGINX_VERSION}-alpine

WORKDIR /app

COPY --from=app_caddy_builder --link /usr/bin/caddy /usr/bin/caddy
