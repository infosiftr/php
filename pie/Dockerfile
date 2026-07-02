#
# NOTE: THIS DOCKERFILE IS GENERATED VIA "apply-templates.sh"
#
# PLEASE DO NOT EDIT IT DIRECTLY.
#

FROM alpine:3.24 as build
RUN set -eux; \
	apk add --no-cache curl; \
	curl -fsSL -o /usr/local/bin/pie 'https://github.com/php/pie/releases/download/1.4.7/pie.phar'; \
	echo 'e8d27c100e85720f374a55f79d63fa8d686dedabc9ccbc6567085e0baf646d55 */usr/local/bin/pie' | sha256sum -c; \
	chmod +x /usr/local/bin/pie

FROM scratch
COPY --from=build /usr/local/bin/pie /pie
