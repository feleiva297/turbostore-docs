# Template

---

## 🧱 TurboStore – Arquitectura del Template

El Template de TurboStore representa la tienda online visible para los usuarios finales. Es una app completamente dinámica y modular, cuyo contenido y diseño se adaptan a la configuración establecida desde el **Creator**.

---

### 📁 Estructura General del Proyecto

```

/template
│
├── components/        # Componentes reutilizables
├── layouts/           # Estructura de layout por sección
├── pages/             # Páginas principales de la tienda
├── redux/             # Store global y slices de estado
├── routes/            # Definición de rutas y navegación
├── services/          # Integración con APIs
├── themes/            # Configuración de estilos y temas
└── utils/             # Funciones utilitarias
```

---

### 🧩 1. Componentes

Componentes reutilizables y configurables que forman la interfaz visual del template.

- **ProductCard**
- **CategoryCard**
- **Navbar**
- **Footer**
- **Button**
- **Input**
- **QuantitySelector**
- **ImageGallery**
- **SkeletonLoader**
- **PriceTag**
- **TagList**
- **StarsRating**
- **Modal**
- **Alert**
- **Badge**
- **ToggleTheme**
- **SearchBar**
- **CartPreview**

---

### 📐 2. Layouts

Contenedores estructurales de cada tipo de vista.

- **MainLayout** – layout base para toda la tienda (header/footer/contexto)
- **ProductLayout** – layout específico para página de producto
- **CategoryLayout** – layout para listado de productos de una categoría
- **ContactLayout** – layout para la página de contacto
- **NotFoundLayout** – para la página 404
- **AuthLayout** – para páginas de login/register si se agregan
- **CheckoutLayout** – para proceso de compra

---

### 📄 3. Pages

Páginas principales que el cliente puede navegar.

- `/` – **HomePage**
- `/product/:id` – **ProductPage**
- `/category/:slug` – **CategoryPage**
- `/checkout` – **CheckoutPage**
- `/contact` – **ContactPage**
- `/*`– **NotFoundPage**

---

### 🧠 4. Redux

Manejo de estado global con slices.

- **store.ts** – configuración global
- **configSlice** – para manejar la configuración y theme del Creator
- **cartSlice** – carrito de compras
- **productsSlice** – productos
- **categoriesSlice** – categorías
- **uiSlice** – UI y modales

---

### 🔀 5. Routes

Sistema de navegación con React Router DOM.

- `routes.ts` – definición de rutas
- `AppRouter.tsx` – renderiza las rutas con layouts correspondientes
- `ProtectedRoute.tsx` – (opcional) protección de rutas privadas

---

### 🌐 6. Services

Módulo de servicios HTTP para consumir la API.

- `api.ts` – instancia de axios con interceptores
- `productService.ts`
- `categoryService.ts`
- `configService.ts`
- `checkoutService.ts`

---

### 🎨 7. Themes

Sistema de tematización dinámico.

- `theme.ts` – definición del tema base
- `tailwind.config.js` – configuración dinámica si se usa Tailwind
- `useThemeConfig.ts` – hook para aplicar la configuración del Creator

---

### 🧰 8. Utils

Funciones de utilidad y helpers globales.

- `formatPrice.ts`
- `slugify.ts`
- `truncate.ts`
- `capitalize.ts`
- `mergeConfig.ts`
- `handleApiError.ts`

---

### 🧩 Extras

- **Internacionalización (i18n)** *(si aplica)*
- **Dark Mode toggle** desde el Creator
- **Responsive** adaptable a móviles
- **Accesibilidad** (foco, contraste, etiquetas alt)