# Defer Number Facts

Live Number Facts are paused until we choose an HTTPS-capable trivia source. Numbers API is HTTP-only (broken TLS on HTTPS), so browser calls fail and mixed content would block HTTP from the Cloudflare site. Proxying and a static dataset were rejected for now; the countdown ships without facts.
