# BOE-MCP. Integración vía MCP con la API del BOE

[![en](https://img.shields.io/badge/lang-en-red.svg)](README.md)
[![es](https://img.shields.io/badge/lang-es-yellow.svg)](README_es.md)

## DESCRIPCIÓN

**BOE es el Boletín Oficial del Estado de España.**

**Boe-mcp** permite consultar legislación consolidada, sumarios del BOE/BORME y datos auxiliares jurídicos directamente desde Claude AI y otros clientes MCP compatibles, utilizando el protocolo **Model Context Protocol (MCP)**.

Boe-mcp es un servidor MCP que expone herramientas para que los LLM puedan acceder a:

- Legislación consolidada del ordenamiento jurídico español
- Sumarios diarios del BOE y BORME
- Tablas auxiliares de materias, ámbitos y departamentos

## CARACTERÍSTICAS PRINCIPALES

- Búsqueda avanzada de legislación consolidada con filtros por fecha, ámbito y vigencia
- Recuperación de textos legales completos en formato XML/JSON
- Consulta de sumarios históricos del BOE y BORME
- Acceso a tablas auxiliares de referencia legal (materias, departamentos, relaciones)
- Soporte para navegación por bloques de texto legal
- Validación automática de consolidación normativa

## INSTALACIÓN

### Instalar con uv

### Prerrequisitos

- Python 3.10 o superior.
- [uv](https://docs.astral.sh/uv/getting-started/installation/) package manager.

### Instalación de uv

Lo primero que hay que hacer es instalar `uv`, que es un gestor de paquetes para Python.
**Se instala desde la consola**.

En MAC y Linux:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

En Windows:

```bash
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

También se puede instalar con pip:

```bash
pip install uv
```

Para más información sobre la instalación de **uv**, consulta la [documentación oficial](https://docs.astral.sh/uv/getting-started/installation/).

## INTEGRACIÓN CON CLIENTES COMO CLAUDE PARA ESCRITORIO

1. Ve a **Claude > Settings > Developer > Edit Config > `claude_desktop_config.json`**.
2. Agrega el siguiente bloque de código dentro de `"mcpServers"`:

```json
"boe_mcp": {
    "command": "uvx",
    "args": [
        "boe_mcp"
    ]
}
```

3. Si ya tienes otro servidor MCP configurado, separa cada servidor con una coma `,`.

## EJEMPLOS DE USO

Una vez configurado, podrás realizar consultas como:

- "Lista las leyes estatales vigentes sobre protección de datos"
- "Muestra el sumario del BOE del 14/06/2024"
- "Muestra la tabla de materias jurídicas del BOE"
