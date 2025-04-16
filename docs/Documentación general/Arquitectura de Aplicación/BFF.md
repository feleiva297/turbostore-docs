# BFF

---

## 🧱 TurboStore – Arquitectura del BFF (Backend For Frontend)

El **BFF** es una capa intermedia que sirve como punto de entrada para los frontends. Su objetivo es adaptar los datos del backend a las necesidades específicas del **Creator** y del **Template**, reducir la cantidad de llamadas, centralizar la lógica de frontend que sería innecesaria repetir y mejorar la performance.

---

### 📁 Estructura del Proyecto

```

/bff
│
├── src/
│   ├── modules/          # Agrupación por dominio (auth, stores, products, etc.)
│   ├── common/           # Utilidades y configuraciones compartidas
│   ├── middlewares/      # Middlewares personalizados (auth, logger, etc.)
│   ├── services/         # Clientes HTTP hacia los microservicios o APIs externas
│   ├── adapters/         # Transformadores de datos entre backend y frontend
│   ├── routes/           # Definición de endpoints del BFF
│   ├── guards/           # Validaciones y permisos
│   ├── interceptors/     # Lógica de interceptación HTTP
│   └── main.ts           # Entry point
│
├── .env                  # Variables de entorno
├── tsconfig.json
├── package.json
└── README.md

```

---

### ⚙️ Tecnologías Utilizadas

- **NestJS** – framework principal
- **Axios** – para consumo de microservicios
- **Redis** – opcional para cacheo de peticiones
- **JWT** – validación de tokens
- **Prisma Client** – si necesita persistencia propia
- **Swagger** – documentación de API (solo uso interno)
- **Zod o class-validator** – validaciones de entrada

---

### 🧠 Módulos del BFF

### Auth

- Login / Registro / Logout
- Renovación de Token
- Validación de usuario activo

### Stores

- Obtener información de la tienda
- Activación / desactivación
- Selección de template y tema

### Products

- ABM de productos
- Filtro por categoría

### Categories

- ABM de categorías
- Relación con productos

### Templates

- Listado de templates disponibles
- Carga de vista previa

### Payments

- Configuración de métodos de pago
- Validación de integración (por ejemplo: Stripe, MercadoPago)

### Shipping

- Métodos de envío disponibles
- Configuraciones por país/ciudad

### Config

- Obtener configuración de tema
- Obtener componentes habilitados por el creador

### Orders

- Historial de compras
- Facturación

---

### 📦 Adaptadores

Cada microservicio o fuente de datos tiene su adaptador para:

- Adaptar estructuras al frontend
- Normalizar errores
- Componer múltiples respuestas (por ej. productos + categorías)

---

### 🔐 Seguridad

- Middleware de validación de token JWT
- Protección por roles (admin, store_owner, customer)
- Throttling por IP (opcional)
- CORS sólo para dominios de frontends oficiales

---

### 📥 Resumen de endpoints posibles

| Método | Endpoint | Descripción |
| --- | --- | --- |
| GET | `/store/:id` | Obtener tienda con configuración |
| POST | `/auth/login` | Iniciar sesión |
| POST | `/auth/register` | Crear cuenta |
| POST | `/auth/refresh-token` | Renovar JWT |
| GET | `/store/:id/products` | Obtener productos con formato adaptado |
| POST | `/store/:id/products` | Crear producto |
| GET | `/templates` | Listar templates disponibles |
| GET | `/theme/:storeId` | Obtener tema configurado |
| GET | `/orders/:userId` | Historial de compras |
| ... |  | Y así con cada dominio |

---

### 🧰 Buenas prácticas implementadas

- Validación estricta de entradas con DTOs
- Arquitectura modular y escalable
- Centralización de errores
- Tipado estricto con TypeScript
- Adaptadores para desacoplar del backend real