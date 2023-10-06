# Nginx-Security-Headers
security headers in NGINX ingress in Kubernetes


Important HTTP headers:

Server - this is the first header which we must impose so the Server label should not be displayed in the browser

server: hide

X-Frame-Options - to avoid clickjacking attacks, by ensuring that their content is not embedded into other sites

X-Frame-Options: DENY or SAMEORIGIN

X-XSS-Protection - stops pages from loading when they detect reflected cross-site scripting (XSS) attacks.

X-XSS-Protection: 0 or 1

Content-Type - Indicate the original media type of the resource (prior to any content encoding applied for sending).

Content-Type: text/html; charset=UTF-8

X-Content-Type-Options - Avoid MIME type sniffing

X-Content-Type-Options: nosniff

Strict-Transport-Security (HSTS) - Enforce browsers that it should only be accessed using HTTPS, instead of using HTTP.

Strict-Transport-Security: max-age=< expire-time-in-sec>; includeSubDomains; preload

Strict-Transport-Security: max-age=31536000; includeSubDomains; preload

Content-Security-Policy (CSP) - mitigate Cross-Site Scripting (XSS) and data injection attacks

Content-Security-Policy: default-src 'self' http://example.com

Cross-Origin-Resource-Policy - tells the browser blocks no-cors cross-origin/cross-site requests to the given resource

Cross-Origin-Resource-Policy: same-site
