# 🏥 MediSearch-TDS

> **Sistema integral de búsqueda y gestión de productos farmacéuticos** desarrollado como Proyecto Final de la materia "Tecnología de Desarrollo de Software" (TDS) en el Instituto Tecnológico de Las Américas (ITLA).

[![Sitio en vivo](https://img.shields.io/badge/🌐%20Ver%20en%20vivo-medisearch--tds.netlify.app-blue)](https://medisearch-tds.netlify.app/)
![Estado](https://img.shields.io/badge/Estado-Activo-brightgreen)
![Licencia](https://img.shields.io/badge/Licencia-MIT-blue)
![Frontend](https://img.shields.io/badge/Frontend-React%2018%20%2B%20Vite-61DAFB?logo=react)
![Backend](https://img.shields.io/badge/Backend-.NET%206%20%2B%20Clean%20Architecture-512BD4?logo=dotnet)
![Database](https://img.shields.io/badge/Database-PostgreSQL-336791?logo=postgresql)

---

## 📖 Descripción

**MediSearch** es una plataforma en línea que ofrece a sus usuarios mayor accesibilidad a medicamentos y productos farmacéuticos, conectando eficientemente a:

- 💊 **Clientes** que buscan medicamentos y productos farmacéuticos.
- 🏪 **Farmacias** que distribuyen productos al público.
- 🔬 **Laboratorios** que fabrican y comercializan medicamentos.

### ✨ Características Principales

- 🔍 **Búsqueda avanzada** de medicamentos y productos farmacéuticos por empresa y categoría.
- 📊 **Panel de administración** con visualización de datos y estadísticas en tiempo real.
- 👥 **Sistema de roles** (Cliente, Farmacia, Laboratorio, Administrador, Empleado).
- 💬 **Comentarios y respuestas** en productos con sistema de calificaciones.
- ❤️ **Favoritos** de productos y empresas para usuarios registrados.
- 🏪 **Gestión de catálogos** de empresas y sus productos.
- 💬 **Salas de chat** para comunicación entre usuarios y empresas.
- 📱 **Interfaz responsive** adaptada a dispositivos móviles y desktop.
- 🛡️ **Autenticación JWT** con access y refresh tokens.
- 📧 **Notificaciones y confirmaciones** por correo electrónico.
- 📈 **Gráficas interactivas** en el panel de administración con ApexCharts.

---

## 🛠️ Stack Tecnológico

### Frontend

| Tecnología | Versión | Uso |
|---|---|---|
| [React](https://reactjs.org/) | 18.2.0 | Librería principal de UI |
| [Vite](https://vitejs.dev/) | 4.3.9 | Build tool y servidor de desarrollo |
| [Material-UI (MUI)](https://mui.com/) | 5.13.3 | Sistema de componentes y diseño |
| [React Router](https://reactrouter.com/) | 6.11.2 | Enrutamiento del lado del cliente |
| [Axios](https://axios-http.com/) | 1.4.0 | Cliente HTTP para consumo de API |
| [Formik](https://formik.org/) | 2.4.1 | Gestión de formularios |
| [Yup](https://github.com/jquense/yup) | 1.2.0 | Validación de esquemas |
| [ApexCharts](https://apexcharts.com/) | 3.41.1 | Visualización de datos y gráficas |
| [React Toastify](https://fkhadra.github.io/react-toastify/) | 9.1.3 | Notificaciones en pantalla |
| [MUI X Data Grid](https://mui.com/x/react-data-grid/) | 6.9.0 | Tablas de datos avanzadas |
| [React Image Gallery](https://github.com/xiaolin/react-image-gallery) | 1.3.0 | Galería de imágenes de productos |

### Backend

| Tecnología | Versión | Uso |
|---|---|---|
| [ASP.NET Core](https://dotnet.microsoft.com/) | 6.0 | Framework web principal |
| Clean Architecture | — | Patrón de arquitectura del proyecto |
| [Entity Framework Core](https://learn.microsoft.com/en-us/ef/core/) | 6.0.16 | ORM para acceso a datos |
| [ASP.NET Identity](https://learn.microsoft.com/en-us/aspnet/core/security/authentication/identity) | 6.0.16 | Gestión de usuarios y roles |
| [JWT Bearer Auth](https://jwt.io/) | — | Autenticación con access/refresh tokens |
| [MediatR](https://github.com/jbogard/MediatR) | 12.0.1 | Patrón CQRS (Commands & Queries) |
| [AutoMapper](https://automapper.org/) | 12.0.1 | Mapeo entre entidades y DTOs |
| [Npgsql / PostgreSQL](https://www.npgsql.org/) | 6.0.8 | Proveedor de base de datos PostgreSQL |
| [Swagger / OpenAPI](https://swagger.io/) | 6.5.0 | Documentación interactiva de la API |
| [MailKit](https://github.com/jstedfast/MailKit) | 3.3.0 | Envío de correos electrónicos vía SMTP |
| [DotNetEnv](https://github.com/tonerdo/dotnet-env) | 2.5.0 | Carga de variables de entorno |

---

## 📁 Estructura del Proyecto

```
MediSearch-TDS/
│
├── Frontend/
│   └── medi-search/                    # Aplicación React con Vite
│       ├── public/                     # Archivos estáticos (Logo, etc.)
│       ├── src/
│       │   ├── APIs/                   # Instancias de Axios configuradas
│       │   ├── assets/                 # Imágenes y recursos estáticos
│       │   ├── components/
│       │   │   ├── contexts/           # React Context (Auth, etc.)
│       │   │   ├── custom/             # Componentes personalizados reutilizables
│       │   │   ├── interceptors/       # Interceptores Axios (JWT refresh)
│       │   │   ├── layouts/            # Layouts de página
│       │   │   ├── pages/              # Páginas principales de la app
│       │   │   ├── persistence/        # Persistencia de estado
│       │   │   ├── routeGuards/        # Guardias de rutas (protección)
│       │   │   ├── routes/             # Definición de rutas
│       │   │   └── scenes/             # Escenas/secciones visuales
│       │   ├── hooks/                  # Custom React hooks
│       │   ├── services/               # Servicios de llamadas a la API
│       │   ├── styles/                 # Estilos CSS globales
│       │   ├── utils/                  # Utilidades y helpers
│       │   ├── App.jsx                 # Componente raíz
│       │   └── main.jsx                # Punto de entrada
│       ├── index.html
│       ├── package.json
│       └── vite.config.js
│
├── Backend/
│   └── src/
│       ├── MediSearch.WebApi/              # 🌐 Proyecto principal (ASP.NET Core)
│       │   ├── Controllers/
│       │   │   ├── AccountController.cs   # Autenticación y registro
│       │   │   ├── v1/AdminController.cs  # Gestión de administración
│       │   │   ├── v1/HomeController.cs   # Funcionalidades para clientes
│       │   │   ├── v1/ProductController.cs # CRUD de productos
│       │   │   └── v1/ChatController.cs   # Sistema de chat
│       │   ├── Extensions/                # Extensiones de servicios
│       │   ├── Middlewares/               # Middlewares personalizados
│       │   ├── Program.cs
│       │   ├── Startup.cs
│       │   └── appsettings.json
│       │
│       ├── MediSearch.Core.Application/   # 🧠 Lógica de negocio (CQRS)
│       │   ├── Features/                  # Commands y Queries (MediatR)
│       │   │   ├── Account/
│       │   │   ├── Admin/
│       │   │   ├── Chat/
│       │   │   ├── Home/
│       │   │   └── Product/
│       │   ├── Dtos/                      # Objetos de transferencia de datos
│       │   ├── Interfaces/                # Contratos / Interfaces
│       │   ├── Mappings/                  # Perfiles de AutoMapper
│       │   └── Seeds/                     # Datos iniciales
│       │
│       ├── MediSearch.Core.Domain/        # 📋 Entidades y lógica de dominio
│       │   ├── Entities/                  # Entidades del negocio
│       │   ├── Common/                    # Clase base auditable
│       │   └── Settings/                  # Configuraciones (JWT, Mail)
│       │
│       ├── MediSearch.Infrastructure.Persistence/  # 💾 Acceso a datos
│       │   ├── Contexts/                  # DbContext de EF Core
│       │   └── Repositories/              # Implementación de repositorios
│       │
│       ├── MediSearch.Infrastructure.Identity/    # 🔐 Autenticación
│       │   ├── Entities/                  # ApplicationUser
│       │   ├── Migrations/                # Migraciones de Identity
│       │   └── Services/                  # AccountService (JWT)
│       │
│       ├── MediSearch.Infrastructure.Shared/      # 🔧 Servicios compartidos
│       │   └── Services/                  # EmailService (MailKit)
│       │
│       └── MediSearch.sln                 # Solución de Visual Studio
│
└── README.md
```

---

## 🚀 Guía de Instalación

### 📋 Requisitos Previos

**Para el Frontend:**
- [Node.js](https://nodejs.org/) 16 o superior
- npm 7+ (incluido con Node.js) o [yarn](https://yarnpkg.com/)

**Para el Backend:**
- [.NET SDK 6.0](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) o superior
- [PostgreSQL](https://www.postgresql.org/) o acceso a una instancia de CockroachDB
- [Visual Studio 2022](https://visualstudio.microsoft.com/) (recomendado) o [VS Code](https://code.visualstudio.com/) con extensión C#

---

### ⚙️ Setup — Frontend

**1. Navega a la carpeta del Frontend:**
```bash
cd Frontend/medi-search
```

**2. Instala las dependencias:**
```bash
npm install
```

**3. Configura las variables de entorno:**

Crea un archivo `.env` en la raíz de `Frontend/medi-search/`:
```env
VITE_API_URL=https://localhost:5001/api/v1
```

**4. Inicia el servidor de desarrollo:**
```bash
npm run dev
```
La aplicación estará disponible en `http://localhost:5173`

**5. Build para producción:**
```bash
npm run build
```

---

### ⚙️ Setup — Backend

**1. Navega a la carpeta del Backend:**
```bash
cd Backend/src
```

**2. Configura las variables de entorno:**

El proyecto usa `DotNetEnv`. Crea un archivo `.env` en la carpeta `Backend/src/MediSearch.WebApi/`:
```env
HOST=tu-host-de-postgresql
PASSWORD=tu-contraseña-de-base-de-datos
```

O actualiza directamente el `appsettings.json` (ver sección de [Configuración](#-configuración--backend)).

**3. Restaura las dependencias NuGet:**
```bash
dotnet restore
```

**4. Aplica las migraciones de base de datos:**
```bash
# Migraciones de la base de datos de la aplicación
dotnet ef database update --project MediSearch.Infrastructure.Persistence --startup-project MediSearch.WebApi

# Migraciones de Identity (usuarios y roles)
dotnet ef database update --project MediSearch.Infrastructure.Identity --startup-project MediSearch.WebApi
```

**5. Ejecuta el servidor de desarrollo:**
```bash
dotnet run --project MediSearch.WebApi
```
La API estará disponible en `https://localhost:5001`  
Swagger UI disponible en: `https://localhost:5001/swagger`

**Alternativa con Visual Studio 2022:**
- Abre `Backend/src/MediSearch.sln`
- Establece `MediSearch.WebApi` como proyecto de inicio
- Presiona **F5** para ejecutar

---

## 📝 Scripts y Comandos Disponibles

### Frontend (`Frontend/medi-search/`)

| Comando | Descripción |
|---|---|
| `npm run dev` | Inicia el servidor de desarrollo con Vite (puerto 5173) |
| `npm run build` | Compila la aplicación para producción en `dist/` |
| `npm run lint` | Ejecuta ESLint para verificar la calidad del código |
| `npm run preview` | Previsualiza la build de producción localmente |

### Backend (`Backend/src/`)

| Comando | Descripción |
|---|---|
| `dotnet restore` | Restaura los paquetes NuGet del proyecto |
| `dotnet build` | Compila toda la solución |
| `dotnet run --project MediSearch.WebApi` | Ejecuta el servidor de la API |
| `dotnet ef migrations add <Nombre> --project MediSearch.Infrastructure.Persistence --startup-project MediSearch.WebApi` | Crea una nueva migración de EF Core |
| `dotnet ef database update --project MediSearch.Infrastructure.Persistence --startup-project MediSearch.WebApi` | Aplica las migraciones pendientes |
| `dotnet test` | Ejecuta las pruebas unitarias |

---

## 🔐 Configuración — Backend

### `appsettings.json`

Archivo de configuración principal ubicado en `Backend/src/MediSearch.WebApi/appsettings.json`:

```json
{
  "UseInMemoryDatabase": false,
  "ConnectionStrings": {
    "PostgreSQL": "Host=TU_HOST;Port=5432;Database=MediSearchDB;User ID=TU_USUARIO;Password=TU_CONTRASEÑA;sslmode=Require;Trust Server Certificate=true"
  },
  "JWTSettings": {
    "Key": "tu-clave-secreta-larga-aqui",
    "Issuer": "CodeIdentity",
    "Audience": "MediSearchApi",
    "DurationInMinutes": 15
  },
  "RefreshJWTSettings": {
    "Key": "tu-clave-refresh-larga-aqui",
    "Issuer": "CodeIdentity",
    "Audience": "MediSearchApi",
    "DurationInDays": 5
  },
  "MailSettings": {
    "EmailFrom": "tu-correo@gmail.com",
    "SmtpHost": "smtp.gmail.com",
    "SmtpPort": 587,
    "SmtpUser": "tu-correo@gmail.com",
    "SmtpPass": "tu-contraseña-de-aplicacion-gmail",
    "DisplayName": "MediSearch"
  },
  "AllowedHosts": "*"
}
```

> ⚠️ **Importante:** No subas el `appsettings.json` con credenciales reales al repositorio. Usa variables de entorno o el archivo `.env` para manejar datos sensibles en producción.

---

## 📚 Endpoints Principales de la API

Base URL: `https://localhost:5001/api/v1`

### 🔑 Autenticación (`/Account`)

| Método | Endpoint | Descripción | Auth |
|---|---|---|---|
| POST | `/Account/login` | Iniciar sesión y obtener tokens | No |
| POST | `/Account/register-client` | Registrar nuevo cliente | No |
| POST | `/Account/register-company` | Registrar nueva empresa (Farmacia/Laboratorio) | No |
| GET | `/Account/refresh-access-token` | Renovar el access token | No |
| GET | `/Account/validate-refresh-token` | Validar el refresh token | No |
| GET | `/Account/confirm-email` | Confirmar correo electrónico | No |
| POST | `/Account/reset-password` | Solicitar restablecimiento de contraseña | No |
| POST | `/Account/confirm-code` | Confirmar código de verificación | No |
| POST | `/Account/change-password` | Cambiar contraseña del usuario | Sí |
| GET | `/Account/logout` | Cerrar sesión | Sí |

### 🏠 Inicio / Clientes (`/Home`)

| Método | Endpoint | Descripción | Auth |
|---|---|---|---|
| GET | `/Home/get-products-farmacy` | Obtener productos de farmacias | Sí |
| GET | `/Home/get-products-laboratory` | Obtener productos de laboratorios | Sí |
| GET | `/Home/get-product/{id}` | Obtener detalle de un producto | Sí |
| GET | `/Home/get-all-farmacy` | Listar todas las farmacias | Sí |
| GET | `/Home/get-all-laboratory` | Listar todos los laboratorios | Sí |
| GET | `/Home/get-all-companies` | Listar todas las empresas | Sí |
| GET | `/Home/get-company/{id}` | Obtener detalle de una empresa | Sí |
| GET | `/Home/get-all-favorite-company` | Listar empresas favoritas del usuario | Sí |
| GET | `/Home/get-all-favorite-product` | Listar productos favoritos del usuario | Sí |
| GET | `/Home/get-data-client` | Obtener datos del cliente autenticado | Sí |
| POST | `/Home/add-favorite-company` | Agregar empresa a favoritos | Sí |
| POST | `/Home/add-favorite-product` | Agregar producto a favoritos | Sí |
| DELETE | `/Home/delete-favorite-company/{companyId}` | Eliminar empresa de favoritos | Sí |
| DELETE | `/Home/delete-favorite-product/{productId}` | Eliminar producto de favoritos | Sí |

### 📦 Productos (`/Product`)

| Método | Endpoint | Descripción | Auth |
|---|---|---|---|
| GET | `/Product/get-all` | Listar todos los productos de la empresa | Sí |
| GET | `/Product/get/{id}` | Obtener detalle de un producto | Sí |
| POST | `/Product/create` | Crear nuevo producto | Sí |
| PUT | `/Product/update` | Actualizar producto existente | Sí |
| DELETE | `/Product/delete/{id}` | Eliminar producto | Sí |
| POST | `/Product/add-comment` | Agregar comentario a un producto | Sí |
| POST | `/Product/add-reply` | Agregar respuesta a un comentario | Sí |

### 👤 Administración (`/Admin`)

| Método | Endpoint | Descripción | Auth |
|---|---|---|---|
| GET | `/Admin/get-all-employees` | Listar empleados de la empresa | Sí |
| GET | `/Admin/get-profile` | Obtener perfil del usuario | Sí |
| GET | `/Admin/get-profile-company` | Obtener perfil de la empresa | Sí |
| GET | `/Admin/get-data-dashboard` | Obtener datos del panel de control | Sí |
| POST | `/Admin/register-employee` | Registrar nuevo empleado | Sí |
| DELETE | `/Admin/delete-employee/{id}` | Eliminar empleado | Sí |
| PUT | `/Admin/edit-profile` | Editar perfil del usuario | Sí |
| PUT | `/Admin/edit-profile-company` | Editar perfil de la empresa | Sí |

### 💬 Chat (`/Chat`)

| Método | Endpoint | Descripción | Auth |
|---|---|---|---|
| GET | `/Chat/get-all-chats` | Obtener todas las salas de chat | Sí |
| GET | `/Chat/get-chat/{id}` | Obtener mensajes de una sala | Sí |
| POST | `/Chat/send-message` | Enviar un mensaje | Sí |

> 📖 Documentación completa e interactiva disponible en Swagger UI: `https://localhost:5001/swagger`

---

## 🌐 Deployment

### Frontend — Netlify

El Frontend está desplegado en Netlify con integración continua desde la rama `main`.

```bash
# Build para producción
cd Frontend/medi-search
npm run build

# Deploy manual con CLI de Netlify
npm install -g netlify-cli
netlify login
netlify deploy --prod --dir=dist
```

**Configuración de Netlify (`netlify.toml`):**
```toml
[build]
  base    = "Frontend/medi-search"
  command = "npm run build"
  publish = "dist"

[[redirects]]
  from   = "/*"
  to     = "/index.html"
  status = 200
```

**URL en producción:** [https://medisearch-tds.netlify.app/](https://medisearch-tds.netlify.app/)

### Backend — Cloud Hosting

```bash
# Publicar para producción
dotnet publish -c Release -o ./publish

# Subir los archivos publicados a tu proveedor (Azure App Service, Render, Railway, etc.)
```

---

## 🔧 Solución de Problemas

### Frontend

**❌ `Cannot find module` o errores de dependencias:**
```bash
rm -rf node_modules package-lock.json
npm install
```

**❌ Error de CORS en desarrollo:**
- Verifica que el Backend esté ejecutándose en `https://localhost:5001`.
- El Backend está configurado para permitir el origen `http://localhost:5173`.

**❌ Variables de entorno no detectadas:**
- El archivo `.env` debe estar en la raíz de `Frontend/medi-search/`.
- Las variables deben comenzar con el prefijo `VITE_` para ser accesibles desde el código (ej. `VITE_API_URL`).

### Backend

**❌ Error al conectar a la base de datos:**
```bash
# Verifica que las variables de entorno o appsettings.json estén configurados
# Asegúrate de que el servidor PostgreSQL esté activo y accesible
```

**❌ Migraciones pendientes:**
```bash
dotnet ef database update --project MediSearch.Infrastructure.Persistence --startup-project MediSearch.WebApi
dotnet ef database update --project MediSearch.Infrastructure.Identity --startup-project MediSearch.WebApi
```

**❌ Puerto 5001 en uso:**
```bash
# Cambia el puerto en launchSettings.json o ejecuta:
dotnet run --project MediSearch.WebApi --urls "https://localhost:5002"
```

**❌ Error de certificado SSL en desarrollo:**
```bash
dotnet dev-certs https --trust
```

**❌ Error de envío de correo electrónico:**
- Asegúrate de que `SmtpUser` y `SmtpPass` en `MailSettings` sean correctos.
- Usa una **Contraseña de Aplicación** de Gmail (no la contraseña de tu cuenta).
- Activa el acceso de aplicaciones de dos pasos en tu cuenta de Google.

---

## 🤝 Guía de Contribución

¡Las contribuciones son bienvenidas! Sigue estos pasos:

1. **Fork** el repositorio.
2. **Crea una rama** para tu funcionalidad o corrección:
   ```bash
   git checkout -b feature/nueva-funcionalidad
   ```
3. **Realiza tus cambios** siguiendo los estándares de código.
4. **Haz commit** de tus cambios:
   ```bash
   git commit -m "feat: agregar búsqueda avanzada de medicamentos"
   ```
5. **Sube tu rama:**
   ```bash
   git push origin feature/nueva-funcionalidad
   ```
6. **Abre un Pull Request** describiendo claramente los cambios realizados.

### Estándares de Código

- **Frontend:** Sigue las reglas de ESLint configuradas en el proyecto. Ejecuta `npm run lint` antes de hacer commit.
- **Backend:** Mantén la arquitectura Clean Architecture. Agrega los nuevos casos de uso como Commands o Queries en la capa `Application`.
- Incluye comentarios en lógica compleja o no obvia.
- Escribe mensajes de commit descriptivos y en español o inglés consistente.

### Convención de Commits

```
feat:     Nueva funcionalidad
fix:      Corrección de un bug
docs:     Cambios en documentación
style:    Cambios de formato (espacios, comas, etc. sin cambios de lógica)
refactor: Refactorización de código sin cambios funcionales
perf:     Mejoras de rendimiento
test:     Adición o modificación de pruebas
chore:    Cambios en configuración, dependencias o tareas de mantenimiento
```

**Ejemplos:**
```bash
git commit -m "feat: agregar filtro de productos por categoría"
git commit -m "fix: corregir error de autenticación con refresh token expirado"
git commit -m "docs: actualizar guía de instalación del backend"
```

---

## 👥 Autores

Desarrollado como Proyecto Final por estudiantes de:

- 🏛️ **Institución:** Instituto Tecnológico de Las Américas (ITLA)
- 📚 **Materia:** Tecnología de Desarrollo de Software (TDS)

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo [LICENSE](LICENSE) para más detalles.

---

## 📞 Soporte

¿Tienes preguntas o encontraste un problema?

- 🐛 **Issues:** [Crear un issue](https://github.com/DaviddelaRosa15/MediSearch-TDS/issues)
- 💬 **Discussions:** [Participar en las discusiones](https://github.com/DaviddelaRosa15/MediSearch-TDS/discussions)
- 🌐 **Sitio en vivo:** [medisearch-tds.netlify.app](https://medisearch-tds.netlify.app/)

---

*Última actualización: Abril 2026*
