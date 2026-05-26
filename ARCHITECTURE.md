# Arquitectura de Zynara

## Diagrama general

Internet → Cloudflare → Nginx (SSL) → Node.js → Gemini 2.5 Flash
                                     ↓
                              Stripe / NOWPayments

## Componentes
- **Gateway:** Cloudflare maneja DDoS, DNSSEC y headers de seguridad
- **Proxy:** Nginx con SSL A+, HSTS y CSP estricto
- **Backend:** Node.js con webhook handler y auth bcrypt
- **IA:** Gemini 2.5 Flash via API
- **Pagos:** Stripe (fiat) + NOWPayments (crypto LTC)
- **Infra:** Self-hosted en Debian, contenedorizado con Docker

## Por qué self-hosted
Control total sobre datos, costos predecibles y
experiencia real de DevOps.
