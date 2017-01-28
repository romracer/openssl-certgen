openssl
=======

[![](https://badge.imagelayers.io/spifftastic/openssl-certgen.svg)](https://imagelayers.io/?images=spifftastic/openssl-certgen:latest 'Get your own badge on imagelayers.io')

Alpine-based image with OpenSSL for SSL certificate generation. Forked from the
[centurylink/openssl](https://github.com/CenturyLinkLabs/openssl) image.

Usage
-----
```sh
docker run --rm \
	-e LIFETIME=3652 \
	-e COUNTRY_NAME=<Country Name> \
	-e COMMON_NAME=<Common Name> \
	-e KEY_NAME=<Cert File Names Prefix> \
	-v /var/certs:/certs \
	spifftastic/openssl-certgen
```

Environment Variables
---------------------
- `LIFETIME` - The number of days the cert is valid.  Defaults to 365 days.
- `COUNTRY_NAME` - The country name. Defaults to nothing.
- `COMMON_NAME` - The common name.
- `KEY_NAME` - The name to use for the CSR, certificate, and key. By default,
  the files are `KEY_NAME.csr`, `KEY_NAME.crt`, and `KEY_NAME.key`,
  respectively.
- `KEY_FILE` - An explicit key file to use instead of `KEY_NAME.key`. If
  `KEY_NAME` is not set, you must also set `CRT_FILE`.
- `CRT_FILE` - An explicit certificate file name to use instead of
  `KEY_NAME.crt`. If `KEY_NAME` is not set, you must also set `KEY_FILE`.
