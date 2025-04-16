# Creator

---

## 🧱 TurboStore – Arquitectura del Creator

El **Creator** es la aplicación donde los usuarios crean, personalizan y administran su tienda online. Permite definir productos, categorías, metodos de pago, configuración de diseño, templates, etc. Todos los datos generados acá son consumidos por el **Template**.

---

### 📁 Estructura General del Proyecto

```

/creator
│
├── components/        # Componentes reutilizables del sistema
├── layouts/           # Layouts estructurales (dashboard, auth, etc.)
├── pages/             # Páginas accesibles desde el panel del usuario
├── redux/             # Store y slices de estado
├── routes/            # Sistema de navegación
├── services/          # Comunicación con APIs del backend
├── themes/            # Estilos, variables de diseño, etc.
└── utils/             # Funciones auxiliares

```

---

### 🧩 1. Componentes

Componentes reutilizables del panel administrador.

- **Sidebar**
- **Topbar**
- **StoreCard**
- **FormInput**
- **FormSelect**
- **FormSwitch**
- **Modal**
- **ConfirmDialog**
- **ProductCard**
- **CategoryCard**
- **TemplatePreview**
- **ThemeSelector**
- **ColorPicker**
- **Toast**
- **SkeletonLoader**

---

### 📐 2. Layouts

Estructuras generales para distintas secciones.

- **AuthLayout** – login y registro
- **DashboardLayout** – vista principal para tiendas
- **StoreLayout** – configuración y personalización de una tienda
- **SettingsLayout** – configuración general
- **ProductLayout** – secciones internas de productos
- **CategoryLayout** – secciones internas de categorías

---

### 📄 3. Pages

Rutas principales del Creator.

- `/login` – **LoginPage**
- `/register` – **RegisterPage**
- `/dashboard` – **DashboardPage**
- `/store/:id` – **StorePage**
- `/store/:id/products` – **ProductsPage**
- `/store/:id/categories` – **CategoriesPage**
- `/store/:id/templates` – **TemplatesPage**
- `/store/:id/theme` – **ThemePage**
- `/store/:id/payments` – **PaymentsPage**
- `/store/:id/shipping` – **ShippingPage**
- `/store/:id/contact` – **ContactPage**
- `/store/:id/status` – **StatusPage**

---

### 🧠 4. Redux

Gestión de estado global para toda la app.

- **store.ts** – store principal
- **authSlice** – autenticación
- **userSlice** – información del usuario
- **storeSlice** – datos de la tienda actual
- **productSlice** – productos
- **categorySlice** – categorías
- **themeSlice** – configuración de diseño
- **paymentSlice** – métodos de pago
- **shippingSlice** – métodos de envío
- **uiSlice** – estado de UI (modales, loaders)

---

### 🔀 5. Routes

Sistema de navegación con rutas protegidas.

- `routes.ts` – definición de rutas
- `AppRouter.tsx` – enrutador principal
- `PrivateRoute.tsx` – protección de rutas autenticadas

---

### 🌐 6. Services

Servicios de conexión con backend para CRUDs.

- `api.ts` – axios con auth + interceptores
- `authService.ts`
- `userService.ts`
- `storeService.ts`
- `productService.ts`
- `categoryService.ts`
- `templateService.ts`
- `themeService.ts`
- `paymentService.ts`
- `shippingService.ts`

---

### 🎨 7. Themes

Sistema visual para la configuración del diseño.

- `themeOptions.ts` – opciones disponibles
- `useThemeForm.ts` – hook de formulario
- `PreviewContext.tsx` – contexto de vista previa de la tienda
- `tailwind.config.js` – (si usa Tailwind, para personalización)

---

### 🧰 8. Utils

Funciones auxiliares para tareas comunes.

- `formatDate.ts`
- `slugify.ts`
- `capitalize.ts`
- `generateId.ts`
- `validateEmail.ts`
- `handleApiError.ts`
- `parseThemeConfig.ts`

---

### 🧩 Extras

- Vista previa del Template en tiempo no real (simulación de los cambios)
- Guardado automático de formularios
- Drag & drop (si aplica para ordenamiento de productos o secciones)
- Toasts y feedback al usuario
- Acceso multi-tienda para un mismo usuario