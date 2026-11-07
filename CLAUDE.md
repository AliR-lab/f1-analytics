# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Estado del proyecto

Esqueleto inicial (creado con `uv init --package`). El único código es un `main()` de ejemplo en `src/f1_analytics/__init__.py`. Todavía no hay tests, linter ni formateador configurados: no des por hecho que existen pytest o ruff; si hacen falta, añádelos antes como dependencias de desarrollo.

## Herramientas

Gestionado con **uv** (backend de build `uv_build`). Python está fijado en 3.13 mediante `.python-version` y `requires-python = ">=3.13"`, así que se puede usar sintaxis moderna (`match`, uniones de tipos `X | Y`, genéricos nativos como `list[int]`, etc.).

```bash
uv sync                      # instala dependencias + grupo dev en .venv
uv run f1-analytics          # ejecuta el punto de entrada (f1_analytics:main)
uv add <paquete>             # añade una dependencia de ejecución
uv add --dev <paquete>       # añade al grupo de dependencias de desarrollo
uv run jupyter lab           # JupyterLab está en el grupo dev para análisis exploratorio
```

Tras cambiar la versión de Python, ejecuta `uv sync` para recrear `.venv` y actualizar `uv.lock`.

## Stack y estructura

- Librerías principales: **DuckDB** (motor de análisis SQL), **pandas** y **matplotlib**.
- Estructura src: el código del paquete vive en `src/f1_analytics/`; el comando `f1-analytics` apunta a `f1_analytics:main`.
- `data/` está en `.gitignore`: los datos en bruto o procesados van ahí y nunca se suben al repositorio. `.env` también está ignorado, para secretos y claves de API.

## Cómo quiero que me ayudes
- Estoy aprendiendo data analytics desde cero
- No quiero que me escribas el código salvo que te lo pida
- Quiero que me revises y expliques el código
- Quiero que me corrijas y expliques las correcciones y los errores
- Quiero que me sugieras próximos pasos
- Quiero que me expliques los comandos antes de ejecutarlos
- Usa siempre uv (nunca pip) 
- Ejecuta Python con uv run 
- Responde en español. 