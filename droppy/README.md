# Droppy (plugin para Claude Desktop y Claude Code)

Droppy ayuda a un dropshipper de Shopify en la UE a analizar productos, competencia, rentabilidad, anuncios, stock, precios, páginas de producto y KPIs, y a proponer mejoras y contenidos. Las acciones sensibles requieren aprobación individual; su servidor MCP protegido aplica licencia, plan, límites y auditoría. Droppy no ejecuta automáticamente ni sustituye asesoramiento legal o fiscal.

Droppy MCP es el conector protegido que aporta el contexto de licencia, plan, límites y auditoría. La clave se gestiona según el cliente; el paquete conserva solo el placeholder de configuración y no contiene credenciales.

## Qué hace Droppy

Analiza la información disponible de tu catálogo, competencia, rentabilidad, anuncios, stock, precios, páginas de producto y KPIs de Shopify en la UE. A partir de ese análisis propone mejoras, contenidos y acciones con sus supuestos; no promete automatización ni resultados comerciales.

## Flujo de aprobación

Las acciones sensibles siguen análisis y recomendación → droppy_propose_action pendiente → droppy_request_approval/confirmación autorizada por el servidor → ejecución externa → droppy_report_execution. No hay autoaprobación. soft_execution indica que el servidor registra y audita lo que pasa por él, pero no ejecuta Shopify ni controla conectores externos. Droppy no sustituye asesoramiento legal o fiscal.

## Incluye

- Agente: Droppy (la clave técnica del plugin y el servidor sigue siendo droppy).
- Conector humano-documental: Droppy MCP; en .mcp.json la clave soportada es mcpServers.droppy.
- Diez skills operativas de nivel 1; el contenido protegido lo sirve el servidor autorizado.
- Conector MCP HTTPS en https://mcp.hydromix.io/mcp, sin secretos literales.

Skills disponibles:
- /droppy:analisis-competencia-ecommerce
- /droppy:analizar-rendimiento-anuncios-meta
- /droppy:auditar-pagina-producto-shopify
- /droppy:auditar-stock-precios-proveedor
- /droppy:calcular-rentabilidad-producto
- /droppy:crear-creativos-meta
- /droppy:crear-producto-shopify
- /droppy:generar-imagenes-variantes-shopify
- /droppy:informe-kpis-tienda
- /droppy:traducir-contenido-shopify

## Instalación y prueba en chat

- Claude Desktop: si tu versión/interfaz admite importar plugins, puedes intentar cargar Droppy.zip; la carga, la UI, userConfig y la autenticación del conector no se han verificado. Si el cliente lo solicita, configura la licencia/conector según sus indicaciones y abre un chat. Puedes probar con «Analiza este producto para venderlo en Shopify UE; primero dime qué datos necesitas y qué propones».
- Claude Code: carga claude --plugin-dir <carpeta-del-plugin> y prueba el mismo mensaje; usa /<nombre-del-plugin>:<skill> para una skill. La variante con hooks solo se distribuye si se pide explícitamente.

La distribución Desktop no incluye hooks. Si la versión/interfaz de Claude Desktop admite cargar plugins, puedes intentar importar este ZIP; esa carga, la UI, userConfig y el conector no se han verificado. Si necesitas la variante Claude Code con el hook, solicítala explícitamente al generador con --harness claude-code --hooks; no se incluye en este ZIP Desktop.

Instalar el ZIP no autoriza la licencia, no conecta Shopify y no concede permisos automáticamente. La UI de Desktop, OAuth, elicitation y el endpoint fixture no se han verificado.

## Instalación

Requiere una licencia activa de Droppy adquirida en https://droppify.agency. Instalar el plugin es gratis; sin una clave de licencia válida el conector Droppy MCP no responde.

Claude Code (una línea):

```
/plugin install droppy --marketplace hydromix-io/droppify-marketplace
```

Claude Desktop / Claude web (Teams):

1. Customize > Plugins > Add > Add marketplace, y añade el repositorio `hydromix-io/droppify-marketplace`.
2. Instala **droppy** desde el Directorio.
3. Pega tu clave de licencia (`csk_live_...`) en el campo "Clave de licencia" del plugin.

Privacidad: el plugin se conecta al servicio Droppy MCP en https://mcp.hydromix.io. Consulta la política de privacidad en https://droppify.agency/legal/privacidad.
