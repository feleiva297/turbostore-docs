# Buenas prácticas de desarrollo

## 📌 Índice

1. [🔤 Convenciones de nombramiento](https://www.notion.so/Buenas-pr-cticas-de-desarrollo-1ce0ec4380bd8061a323f55239f43bc3?pvs=21)
    
    Guía para nombrar variables, funciones, clases y archivos de forma consistente y clara en NestJS y React.
    
2. [📂 Estructura del código](https://www.notion.so/Buenas-pr-cticas-de-desarrollo-1ce0ec4380bd8061a323f55239f43bc3?pvs=21)
    
    Recomendaciones sobre cómo organizar carpetas y archivos para mantener un proyecto escalable y mantenible.
    
3. [🧠 Principios de desarrollo](https://www.notion.so/Buenas-pr-cticas-de-desarrollo-1ce0ec4380bd8061a323f55239f43bc3?pvs=21)
    
    Fundamentos como DRY, KISS, YAGNI y SOLID que ayudan a escribir código limpio, reutilizable y fácil de mantener.
    
4. [⚛️ Buenas prácticas en React](https://www.notion.so/Buenas-pr-cticas-de-desarrollo-1ce0ec4380bd8061a323f55239f43bc3?pvs=21)
    
    Reglas específicas para componentes, hooks, manejo de estado y estructura en proyectos con React.
    
5. [🦮 Buenas prácticas en NestJS](https://www.notion.so/Buenas-pr-cticas-de-desarrollo-1ce0ec4380bd8061a323f55239f43bc3?pvs=21)
    
    Estándares recomendados para servicios, controladores, DTOs y organización de módulos en NestJS.
    
6. [🌿 Control de versiones (Git)](https://www.notion.so/Buenas-pr-cticas-de-desarrollo-1ce0ec4380bd8061a323f55239f43bc3?pvs=21)
    
    Convenciones para mensajes de commits, uso de ramas y manejo colaborativo del repositorio con Git.
    
7. [🧩 Patrones comunes de diseño](https://www.notion.so/Buenas-pr-cticas-de-desarrollo-1ce0ec4380bd8061a323f55239f43bc3?pvs=21)
    
    Patrones de arquitectura y diseño recomendados para proyectos modernos, como repositorio, factory o singleton.
    
8. [📝 Documentación](https://www.notion.so/Buenas-pr-cticas-de-desarrollo-1ce0ec4380bd8061a323f55239f43bc3?pvs=21)
    
    Cómo y cuándo documentar funciones, endpoints y componentes, incluyendo herramientas útiles.
    
9. [🧪 Testing](https://www.notion.so/Buenas-pr-cticas-de-desarrollo-1ce0ec4380bd8061a323f55239f43bc3?pvs=21)
    
    Buenas prácticas para pruebas unitarias, de integración y end-to-end tanto en el backend como en el frontend.
    
10. [🔍 Revisión de código](https://www.notion.so/Buenas-pr-cticas-de-desarrollo-1ce0ec4380bd8061a323f55239f43bc3?pvs=21)
    
    Guía para realizar code reviews efectivos y constructivos, con foco en la calidad y consistencia del código.
    

---

### 🔤 Convenciones de nombramiento

Guía para nombrar elementos del código de forma clara y consistente:

| Elemento | NestJS | React |
| --- | --- | --- |
| Variables | `camelCase` | `camelCase` |
| Funciones | `camelCase` | `camelCase` |
| Clases | `PascalCase` | `PascalCase` |
| Interfaces | `PascalCase`, opcional `I` | `PascalCase`, opcional `I` |
| Archivos | `kebab-case` | `PascalCase.tsx` o `kebab-case.ts` |
| Constantes | `UPPER_SNAKE_CASE` | `UPPER_SNAKE_CASE` |

---

### 📂 Estructura del código

 **[🐱](https://emojipedia.org/cat-face) NestJS**

```
src/
├── modules/
│   ├── users/
│   │   ├── controllers/
│   │   ├── services/
│   │   ├── dtos/
│   │   ├── entities/
│   │   ├── users.module.ts
│   │   └── users.service.ts
│   └── auth/
│       ├── strategies/
│       ├── guards/
│       ├── dtos/
│       └── auth.module.ts
│
├── common/
│   ├── decorators/
│   ├── filters/
│   ├── interceptors/
│   ├── guards/
│   └── utils/
│
├── config/
│   └── configuration.ts
│
├── main.ts
└── app.module.ts
```

⚛️ **React**

```
src/
├── features/
│   ├── users/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── services/
│   │   ├── types/
│   │   └── index.ts
│
├── shared/
│   ├── components/    ← reutilizables en todo el proyecto
│   ├── utils/
│   ├── constants/
│   ├── hooks/
│   └── styles/
│
├── router/
│   └── AppRouter.tsx
│
├── App.tsx
└── main.tsx (o index.tsx)
```

---

### 🧠 Principios de desarrollo

- **DRY (Don't Repeat Yourself)**: Evitá repetir lógica innecesaria.
- **KISS (Keep It Simple, Stupid)**: Mantené el código simple y directo.
- **YAGNI (You Aren’t Gonna Need It)**: No desarrolles lo que no se necesita aún.
- **SOLID**:
    - **S**ingle Responsibility
    - **O**pen/Closed
    - **L**iskov Substitution
    - **I**nterface Segregation
    - **D**ependency Inversion

---

### ⚛️ Buenas prácticas en React

- Usar **componentes funcionales** con hooks.
- Separar lógica de presentación.
- Preferir `useEffect`, `useMemo`, `useCallback` bien definidos.
- Nombrar componentes con PascalCase.
- Evitar estados innecesarios, usar contextos o herramientas como Redux/TanStack Query donde sea necesario.
- Crear archivos por componente.

---

### 🦮 Buenas prácticas en NestJS

- Separar bien controladores, servicios y DTOs.
- Usar `@Injectable()` correctamente para servicios.
- Validar datos con `class-validator` y `class-transformer`.
- Modularizar por feature.
- Mantener DTOs simples y reutilizables.
- No acoplar controladores con lógica de negocio.

---

### 🌿 Control de versiones (Git)

- Convención de commits (ej. [Conventional Commits](https://www.conventionalcommits.org/)):
    
    ```
    feat: nueva funcionalidad
    fix: corrección de bug
    chore: cambios menores o mantenimiento
    refactor: cambios internos sin alterar comportamiento
    ```
    
- Usar ramas por feature: `feature/login`, `bugfix/user-avatar`, etc.
- Pull Requests con revisiones claras y mensajes explicativos.

---

### 🧩 Patrones comunes de diseño

- **Repository Pattern** (NestJS con TypeORM o Prisma)
- **Factory Pattern** (crear instancias con lógica específica)
- **Service Layer** (React o NestJS)
- **Singleton Pattern** (servicios compartidos)
- **Container / Presentational Components** (React)

---

### 📝 Documentación

- Usar `JSDoc` o comentarios descriptivos para funciones complejas.
- Documentar endpoints en Swagger (NestJS).
- Documentar props y componentes reutilizables en React.
- Mantené un README claro con instrucciones de instalación y ejecución.

---

### 🧪 Testing

**NestJS**

- Usar `@nestjs/testing` con Jest.
- Mockear dependencias en unit tests.
- Probar controladores, servicios y pipes.

**React**

- Usar `@testing-library/react` + Jest.
- Escribir tests por comportamiento, no por implementación.
- Testear casos edge y errores.

---

### 🔍 Revisión de código

- Verificar claridad del código.
- Evitar código duplicado.
- Buscar violaciones a DRY, KISS, SOLID.
- Sugerir mejoras, no solo señalar errores.
- Validar que se mantengan convenciones del equipo.