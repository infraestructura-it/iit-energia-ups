# IIT Energía & UPS — CLAUDE.md

**v1.0** — creado 2026-07-01

## Propósito

Sitio web independiente (multipágina) de servicios de energía de Infraestructura-IT:
estudios de calidad de energía, mantenimiento preventivo/correctivo de UPS, plantas
eléctricas, tecnología (diagrama de bloques UPS online doble conversión + PFC) y contacto.

No forma parte del sitio corporativo `infraestructura-it.github.io` — es un repo propio.

## Estructura

```
index.html         → hero, preview de servicios, teaser de tecnología
servicios.html      → 6 servicios completos
proceso.html         → 5 pasos del flujo de trabajo, detallado
normativa.html      → tabla de rangos + IEEE-519 / RETIE / NTC 5001
tecnologia.html     → diagrama de bloques UPS true online doble conversión + PFC
contacto.html        → canales de contacto
assets/styles.css   → sistema visual compartido (todas las páginas)
assets/site.js       → menú móvil (hamburguesa)
```

## Stack

Vanilla HTML/CSS/JS, sin frameworks. Fuentes vía Google Fonts CDN: Syne (display),
Space Mono (mono/labels), DM Mono (datos/captions).

## Paleta

Base cyberpunk IIT: `#080b10` fondo, `#00D4FF` cyan, `#10B981` verde, `#7C3AED` morado.
Acento propio de este sitio: **ámbar `#FFB020`** (energía / UPS / advertencia eléctrica),
diferenciado de los acentos ya usados en Datacenter/Redes/IA del sitio corporativo.

## Despliegue

GitHub Pages, rama `main`, raíz `/`. Repo objetivo: `infraestructura-it/iit-energia-ups`.
URL esperada: `https://infraestructura-it.github.io/iit-energia-ups/`

## Pendientes

- [ ] Agregar WhatsApp/teléfono real en `contacto.html` (aviso visible dejado en el archivo)
- [ ] Reemplazar el chip SVG simplificado por el logo IIT-CORE definitivo
- [ ] Definir dominio final (subdominio propio vs. GitHub Pages por defecto)
- [ ] Confirmar datos reales de equipos/marcas si se quiere ampliar la tabla de normativa.html
