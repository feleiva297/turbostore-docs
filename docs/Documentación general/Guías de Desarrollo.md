# Guías de Desarrollo

# Setup del proyecto

## Requisitos del Sistema

Para comenzar con el desarrollo del proyecto MultiTienda, necesitarás tener instalado lo siguiente:

- Node.js (v18 o superior)
- npm o yarn como gestor de paquetes
- Git para control de versiones
- Docker y Docker Compose
- Editor de código (VS Code recomendado)

## Instalación del Entorno

Sigue estos pasos para configurar tu entorno de desarrollo:

1. Clonar el repositorio:
    
    ```bash
    git clone https://github.com/multitienda/proyecto
    cd proyecto
    ```
    
2. Instalar dependencias:
    
    ```bash
    npm install
    ```
    
3. Construir contenedores Docker:
    
    ```bash
    docker-compose build
    docker-compose up -d
    ```
    

## Configuración Inicial

Una vez instalado el entorno, deberás realizar las siguientes configuraciones:

- Crear base de datos local siguiendo el script en /docs/db/init.sql
- Configurar el archivo de configuración principal en /config/default.json
- Ejecutar migraciones iniciales: `npm run migrate`
- Cargar datos de prueba: `npm run seed`

## Variables de Entorno

El proyecto requiere las siguientes variables de entorno:

```bash
# Servidor
PORT=3000
NODE_ENV=development

# Base de datos
DB_HOST=localhost
DB_PORT=5432
DB_NAME=multitienda
DB_USER=admin
DB_PASSWORD=password

# JWT
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=24h

# APIs externas
PAYMENT_API_KEY=your-api-key
SHIPPING_API_KEY=your-api-key
```

# Estándares de Código

## Guía de Estilo

Seguimos las siguientes convenciones de código:

- Usar ES6+ para JavaScript/TypeScript
- Indentación de 2 espacios
- Punto y coma al final de cada declaración
- Comillas simples para strings
- Usar const y let, evitar var

## Convenciones de Nombrado

Seguimos estas convenciones para nombrar elementos:

- PascalCase para nombres de clases y componentes
- camelCase para variables y funciones
- UPPER_SNAKE_CASE para constantes
- kebab-case para nombres de archivos

## Procesos de Revisión

El código debe pasar por el siguiente proceso antes de ser integrado:

1. Análisis estático con ESLint
2. Formateo automático con Prettier
3. Code review por al menos un desarrollador
4. Pruebas automáticas pasadas exitosamente

## Testing

Implementamos los siguientes tipos de pruebas:

- Pruebas unitarias con Jest
- Pruebas de integración con Supertest
- Pruebas E2E con Cypress
- Coverage mínimo requerido: 80%

```bash
# Ejecutar pruebas
npm run test           # Pruebas unitarias
npm run test:e2e      # Pruebas E2E
npm run test:coverage # Reporte de coverage
```