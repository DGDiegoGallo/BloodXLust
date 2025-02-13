# BloodXLust
# E-Commerce Application

## Descripción
Esta aplicación es una plataforma de comercio electrónico que consta de dos partes principales:
- **Storefront**: Frontend desarrollado con Next.js
- **Backend**: API REST desarrollada con NestJS

## Estructura del Proyecto
```
.
├── storefront/    # Frontend - Next.js
└── back/          # Backend - NestJS
```

## Requisitos Previos
- Node.js (v16 o superior)
- npm o yarn
- Base de datos (configurada en el backend)
- Credenciales de Shopify
- Cuenta de Shopify Partner

## Configuración de Shopify

### 1. Crear una Nueva Aplicación en Shopify

1. Accede a tu panel de administración de Shopify
2. Ve a "Apps y canales de ventas"
3. Haz clic en "Desarrollar apps"
4. Haz clic en "Crear una app"

![Crear App en Shopify](https://i.imgur.com/1KVUZPf.png)

![Configuración Inicial](https://i.imgur.com/Ee2Pjaz.png)

### 2. Configuración de Permisos Admin API

1. En la nueva aplicación, ve a la pestaña "Configuración"
2. Selecciona "Configurar alcances de la API Admin"
3. Marca los permisos necesarios (En este caso, todos los permisos)

![Configuración de Permisos](https://i.imgur.com/PCZtgM6.png)

![Selección de Permisos](https://i.imgur.com/jC2oVD7.png)

### 3. Obtener Credenciales de Admin API. ¡Para Backend!

Después de configurar los permisos, podrás acceder a:
- Token de acceso de Admin API = SHOPIFY_ACCESS_TOKEN
- Clave API = SHOPIFY_API_KEY
- Clave secreta API = SHOPIFY_API_SECRET

![Credenciales Admin API](https://i.imgur.com/B71POl1.png)

## Adicional. ¡RECUERDA INSTALAR LA APP! En desarrollo de aplicaciones, en la esquina superior derecha debe de estar instalada la app.

### 4. Configuración de API Storefront (Headless) ¡Para Backend y Frontend!

(Recuerda instalar el app en tu tienda Shopify la aplicación Headless)

1. En el panel lateral, selecciona "Headless"
2. Ve a "Gestionar acceso a la API"
3. Haz clic en "Gestionar" en la sección API Storefront
4. Aquí encontrarás los tokens público y privado para el acceso Storefront

![Acceso API Storefront](https://i.imgur.com/z5kGFND.png)

![Tokens Storefront API](https://i.imgur.com/LXC9q8Z.png)

### Configuración de Variables de Entorno

#### Backend (.env)
```
# Configuración de Shopify Admin API. Por favor revisar pasos 1, 2 y 3 Del la sección "Configuración de Shopify"
SHOPIFY_SHOP_NAME=tu-tienda.myshopify.com
SHOPIFY_ACCESS_TOKEN=shpat_xxx... # Token de acceso Admin API
SHOPIFY_API_KEY=xxxxx... # Clave API
SHOPIFY_API_SECRET=xxxxx... # Clave secreta API
SHOPIFY_STOREFRONT_TOKEN=xxxxx... # Token de acceso | Storefront API Revisar paso 4 de la sección "Configuración de Shopify"
```

#### Frontend (.env)
```
# Configuración de Shopify Storefront API
SHOPIFY_STORE_DOMAIN=tu-tienda.myshopify.com
SHOPIFY_STOREFRONT_PRIVATE_TOKEN=shpat_xxx... # Token privado de Storefront API (solo si es necesario)
SHOPIFY_REVALIDATION_SECRET=... # Generar un secreto aleatorio

```

## Instalación

### Backend
```bash
cd back
npm install
npm run start:dev
```

### Frontend
```bash
cd storefront
npm install
npm run dev
```

## Características Principales
- Integración con Shopify
- Gestión de productos
- Sistema de pedidos
- Gestión de stock
- Pagos pendientes

## Desarrollo

Para ejecutar el proyecto en modo desarrollo:

1. Iniciar el backend:
```bash
cd back
npm run start:dev
```

2. Iniciar el frontend:
```bash
cd storefront
npm run dev
```

## Endpoints Principales
- Frontend: `http://localhost:3001`
- Backend: `http://localhost:3000`

## Contribución
Por favor, asegúrate de seguir las mejores prácticas de código y documentar adecuadamente cualquier nueva característica o cambio.

## Configuración Adicionales

### 1. Configuración de Webhooks

1. En settings de la app en Shopify, ve a la sección de "Notificaciones" Y luego seleccionar "Webhooks"   

2. Crear un nuevo Webhooks

3. Se puede añadir la firma en el .env del Backend

![Webhooks](https://i.imgur.com/qg11dQV.png)


SHOPIFY_WEBHOOK_SECRET=...

### 2. Ngrok se encuentra instalado en el Backend (Opcional)

1. Ejecutar el comando `npm run start:dev`
2. Ejecutar el comando `ngrok http 3000`

## Licencia
[MIT](https://opensource.org/licenses/MIT) 

