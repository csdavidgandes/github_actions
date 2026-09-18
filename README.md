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
pip install -r requirements.txt
```

## Ejecutar pruebas

Con `unittest` (notación de módulo, con puntos):

```bash
python -m unittest -v tests.test_persona
```

### Cobertura de pruebas

```bash
coverage run -m unittest tests.test_persona
coverage report -m
```

## Integración continua

El workflow [`pruebas.yml`](.github/workflows/pruebas.yml) se ejecuta en cada `push` y
`pull_request` hacia la rama `main`, y realiza:

1. **Pruebas** (`job1`): instala las dependencias de `requirements.txt`, corre las pruebas
   unitarias con `unittest` y calcula la cobertura con `coverage`.
2. **Automerge** (`automerge`): si las pruebas pasan, intenta hacer merge automático del
   pull request usando [`pascalgn/automerge-action`](https://github.com/pascalgn/automerge-action).

## Dependencias

Definidas en [`requirements.txt`](requirements.txt):

- `coverage` — cálculo de cobertura de pruebas.
- `numpy`, `numpydoc` — utilizadas para pruebas exploratorias del proyecto.
