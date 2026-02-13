# Tutorial Interactivo de GitHub Actions

Este repositorio está preparado para que puedas explicar cómo funciona CI/CD con GitHub Actions.

## Estructura del Proyecto

El proyecto simula una pequeña aplicación Node.js.

- `src/index.js`: El código fuente (muy simple).
- `package.json`: Define los scripts `npm test` y `npm run lint` que usaremos en la CI.
- `.github/workflows/`: ¡Aquí está la magia!

## Guía de Explicación

Sigue este orden para explicar el contenido:

### 1. El Concepto (Intro)

Abre el archivo [src/index.js](./src/index.js) y explica que tenemos código. Luego abre [package.json](./package.json) para mostrar que hay "tareas" que queremos automatizar (test, lint).

### 2. El Primer Workflow (CI Básico)

Abre **[.github/workflows/01-ci-basico.yml](.github/workflows/01-ci-basico.yml)**.

- Explica las **3 Partes Clave**:
  1.  **Events (`on`)**: ¿Cuándo corre? (Push a main).
  2.  **Jobs**: ¿Qué hace? (Verificar código).
  3.  **Steps**: Los pasos individuales.
- Destaca la diferencia entre `uses` (usar algo hecho) y `run` (ejecutar comando).
- Menciona que sin `actions/checkout`, la máquina estaría vacía.

### 3. Workflow Avanzado (Docker & Secretos)

Abre **[.github/workflows/02-deploy-avanzado.yml](.github/workflows/02-deploy-avanzado.yml)**.

- Explica las **Variables de Entorno (`env`)**.
- Explica los **Secretos (`secrets`)**:
  - Muestra cómo usamos `${{ secrets.GITHUB_TOKEN }}` para no poner contraseñas en el código.
- Explica los **Permisos**:
  - Necesarios para escribir paquetes o hacer cosas "peligrosas".

## Peculiaridades Comunes (Para recordar)

1.  **Indentación YAML**: Siempre 2 espacios, NUNCA tabs.
2.  **Rutas**: Los workflows SIEMPRE deben estar en `.github/workflows/`.
3.  **Logs**: Si algo falla, mira la pestaña "Actions" en GitHub para ver el log del error.
