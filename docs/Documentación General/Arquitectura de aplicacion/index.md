# Arquitectura de Aplicación

### 🛠️ 1. Creator

**🎯 Propósito:**

Es el panel de gestión desde donde los usuarios crean y configuran su tienda. Actúa como una interfaz amigable para construir una tienda sin conocimientos técnicos.

**🧩 Funcionalidades:**

- Registro / inicio / cierre de sesión
- Creación y personalización de tienda (colores, templates, logo, etc.)
- Gestión de productos y categorías
- Configuración de métodos de pago y envío
- Activación / desactivación de tienda
- Vista previa de la tienda basada en templates

**📎 Acceso:**

→ *[Ir a la página del Creator]*

---

### 🎨 2. Template

**🎯 Propósito:**

Representa la tienda visible para los compradores. Es una app frontend completamente dinámica y configurable, que consume la configuración establecida en el Creator.

**🧩 Funcionalidades:**

- Renderizado de tienda según configuración del Creator
- Diseño modular con componentes reutilizables
- Sistema de temas (tipografía, colores, estilos)
- Ruteo, Redux, servicios HTTP, manejo de estados y carga
- Páginas predefinidas: Home, Producto, Categoría, Contacto, etc.
- Componentes reutilizables: Navbar, Cards, Botones, Loaders (Skeletons), etc.

**📎 Acceso:**

→ *[Ir a la página del Template]*

---

### 🧠 3. Infraestructura Backend

**🎯 Propósito:**

Proporciona los servicios y la base de datos para toda la plataforma. Es el motor que gestiona la lógica, persistencia y autenticación de TurboStore.

**🧩 Tecnologías:**

- NestJS como framework base
- Prisma ORM
- PostgreSQL como base de datos
- Redis para cacheo de datos y sesiones
- JWT para autenticación y renovación de sesión

**🧩 Avances:**

- Investigación y testing de stack
- Modelo entidad-relación (DER)
- Desarrollo de endpoints de autenticación
- APIs para tienda, productos, configuración, etc.

**📎 Acceso:**

→ *[Ir a la página del Backend]*

[BFF](https://www.notion.so/BFF-1d60ec4380bd80f28beaeac4903e79f8?pvs=21)

[Creator](https://www.notion.so/Creator-1d60ec4380bd8012a39df9ddf6c6f9e4?pvs=21)

[Template](https://www.notion.so/Template-1d60ec4380bd809fb46fc01e7d93e908?pvs=21)