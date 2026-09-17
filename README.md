# github_actions

Proyecto de ejemplo (Módulo 7 - Agile) para practicar CI con GitHub Actions.

## Estructura

```
src/mi_proyecto/           Código fuente (clase Persona)
tests/                     Pruebas unitarias (unittest)
.github/workflows/         Workflows de CI
```

## Instalación

```bash
python3 -m venv venv
source venv/bin/activate
pip install -e .
```

## Ejecutar pruebas

Con `unittest` (notación de módulo, con puntos):

```bash
python -m unittest -v tests.test_persona
```

## Integración continua

El workflow [`pruebas.yml`](.github/workflows/pruebas.yml) corre las pruebas unitarias
automáticamente en cada `push` a la rama `master`.
