# IIT Energía & UPS — CLAUDE.md

**v1.2** — actualizado 2026-07-01

## Propósito

Sitio web independiente (multipágina) de servicios de energía de Infraestructura-IT:
estudios de calidad de energía, mantenimiento preventivo/correctivo de UPS, plantas
eléctricas, tecnología (diagrama de bloques UPS online doble conversión + PFC), zona
de clientes, monitoreo/mejora de infraestructura y contacto.

No forma parte del sitio corporativo `infraestructura-it.github.io` — es un repo propio.

## Estructura

```
index.html            → hero, preview de servicios, teaser de tecnología
servicios.html         → 6 servicios completos
proceso.html            → 5 pasos del flujo de trabajo, detallado
tecnologia.html        → diagrama de bloques UPS true online doble conversión + PFC
zona-clientes.html     → landing informativa: inventario por marca, calibración, fallas
                          comunes — enlaza al portal real (sistema de órdenes de servicio,
                          iit-ordenes-servicio-v2), URL pendiente de reemplazar (ver issues)
monitoreo.html          → software de monitoreo propio + dispositivos IoT a la medida,
                          proceso de implementación, comparación vs. monitoreo genérico
normativa.html          → tabla de rangos + IEEE-519 / RETIE / NTC 5001
contacto.html            → canales de contacto
assets/styles.css       → sistema visual compartido (todas las páginas)
assets/site.js           → menú móvil (hamburguesa)
```

## Stack

Vanilla HTML/CSS/JS, sin frameworks. Fuentes vía Google Fonts CDN: Syne (display),
Space Mono (mono/labels), DM Mono (datos/captions).

## Paleta

Base cyberpunk IIT: `#080b10` fondo, `#00D4FF` cyan, `#10B981` verde, `#7C3AED` morado.
Acento propio de este sitio: **ámbar `#FFB020`** (energía / UPS / advertencia eléctrica),
diferenciado de los acentos ya usados en Datacenter/Redes/IA del sitio corporativo.

## Relación con otros repos

- **zona-clientes.html** es solo la landing informativa. El panel real (inventario,
  calibración, fallas) vive en el repo del sistema de órdenes de servicio
  (`iit-ordenes-servicio-v2`, Supabase). El botón "Ingresar a mi Zona de Cliente" tiene
  un `href="#"` placeholder hasta que se defina la URL pública de ese sistema — ver
  issue de seguimiento abajo.

## Despliegue

GitHub Pages, rama `main`, raíz `/`. Repo: `infraestructura-it/iit-energia-ups`.
URL: `https://infraestructura-it.github.io/iit-energia-ups/`

## Trazabilidad (issue → fix → commit → CLAUDE.md)

Mismo patrón que `iit-ordenes-servicio-v2`: cada pendiente vive como issue individual,
no como checklist duplicado aquí. El commit que lo resuelve debe incluir `closes #N`.

- Backlog activo: `gh issue list --repo infraestructura-it/iit-energia-ups --label "mejora-continua"`
- Todo el historial: `gh issue list --repo infraestructura-it/iit-energia-ups --state all`

Issues de mejora continua abiertos al momento de este corte (confirmar números reales
con `gh issue list`, pueden variar según el orden en que se crearon):

| # | Pendiente |
|---|-----------|
| #3 | Reemplazar URL placeholder de Zona de Clientes |
| #4 | Agregar WhatsApp/teléfono real en contacto.html |
| #5 | Reemplazar logo SVG simplificado por IIT-CORE definitivo |
| #6 | Definir dominio final del sitio |
| #7 | Ampliar tabla de normativa.html con equipos/marcas reales |
| #8 | Confirmar nombres reales de dispositivos IoT/plataforma en monitoreo.html |

Issue #1 (checklist original) y #2 (bug de despliegue Zona de Clientes/Monitoreo) — cerrados.

## Bugs resueltos (referencia rápida)

- **#2** — Zona de Clientes y Monitoreo no aparecían en producción. Causa raíz: el
  credential helper de git seguía usando el token cacheado de `automatizacion-it`
  después de `gh auth switch`. Fix: `gh auth setup-git` para resincronizar git con la
  cuenta activa de gh.


