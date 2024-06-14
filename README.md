# Documentación de Uso del API para Gestión de Productos

Este documento describe cómo utilizar el API disponible en `https://frontend.rrhh.data.cr/api/products` para gestionar productos. Este API permite realizar operaciones de obtención, creación, edición y eliminación de productos. Todas las operaciones requieren autenticación mediante un token.

## Autenticación

Para realizar cualquier solicitud a este API, es necesario incluir el siguiente token de autenticación en los encabezados de la solicitud:

```
Authorization: Bearer 0fsZhSwlAX9wiNa7WU6EKMTe4UpSuIsfxGWMDZ9jsy3DT
```

## Endpoints Disponibles

### 1. Obtener Lista de Productos (GET)

**Endpoint:**
```
GET https://frontend.rrhh.data.cr/api/products
```

**Descripción:**
Este endpoint devuelve una lista de productos. Cada producto tiene la siguiente estructura:

```json
[
    {
        "id": 1,
        "name": "Internet de 100MB",
        "type": "Internet",
        "bandwidth": 100,
        "iptv": false,
        "telephony": false,
        "image": ""
    },
    ...
]
```

**Ejemplo de Solicitud:**

```http
GET /api/products HTTP/1.1
Host: frontend.rrhh.data.cr
Authorization: Bearer 0fsZhSwlAX9wiNa7WU6EKMTe4UpSuIsfxGWMDZ9jsy3DT
```

### 2. Crear Producto (POST)

**Endpoint:**
```
POST https://frontend.rrhh.data.cr/api/products/create
```

**Descripción:**
Este endpoint permite crear un nuevo producto. El cuerpo de la solicitud debe tener la siguiente estructura JSON:

```json
{
    "id": '',
    "name": '',
    "type": '',
    "bandwidth": '',
    "iptv": '',
    "telephony": '',
    "image": ''
}
```

**Ejemplo de Solicitud:**

```http
POST /api/products/create HTTP/1.1
Host: frontend.rrhh.data.cr
Authorization: Bearer 0fsZhSwlAX9wiNa7WU6EKMTe4UpSuIsfxGWMDZ9jsy3DT
Content-Type: application/json

{
    "id": 2,
    "name": "Internet de 200MB",
    "type": "Internet",
    "bandwidth": 200,
    "iptv": true,
    "telephony": true,
    "image": "url_imagen"
}
```

### 3. Editar Producto (POST)

**Endpoint:**
```
POST https://frontend.rrhh.data.cr/api/products/update
```

**Descripción:**
Este endpoint permite editar un producto existente. El cuerpo de la solicitud debe tener la siguiente estructura JSON:

```json
{
    "id": 1,
    "data": {
        "name": "Plan 0",
        "bandwidth": 150,
        "telephony": true,
        "image": ""
    }
}
```

**Ejemplo de Solicitud:**

```http
POST /api/products/update HTTP/1.1
Host: frontend.rrhh.data.cr
Authorization: Bearer 0fsZhSwlAX9wiNa7WU6EKMTe4UpSuIsfxGWMDZ9jsy3DT
Content-Type: application/json

{
    "id": 1,
    "data": {
        "name": "Plan 0",
        "bandwidth": 150,
        "telephony": true,
        "image": ""
    }
}
```

### 4. Eliminar Producto (POST)

**Endpoint:**
```
POST https://frontend.rrhh.data.cr/api/products/delete
```

**Descripción:**
Este endpoint permite eliminar un producto. El cuerpo de la solicitud debe tener la siguiente estructura JSON:

```json
{
    "id": 4
}
```

**Ejemplo de Solicitud:**

```http
POST /api/products/delete HTTP/1.1
Host: frontend.rrhh.data.cr
Authorization: Bearer 0fsZhSwlAX9wiNa7WU6EKMTe4UpSuIsfxGWMDZ9jsy3DT
Content-Type: application/json

{
    "id": 4
}
```

### 5. Eliminar Productos por Categoría (POST)

**Endpoint:**
```
POST https://frontend.rrhh.data.cr/api/products/delete_type
```

**Descripción:**
Este endpoint permite eliminar productos por categoría. El cuerpo de la solicitud debe tener la siguiente estructura JSON:

```json
{
    "type": "Internet"
}
```

**Ejemplo de Solicitud:**

```http
POST /api/products/delete_type HTTP/1.1
Host: frontend.rrhh.data.cr
Authorization: Bearer 0fsZhSwlAX9wiNa7WU6EKMTe4UpSuIsfxGWMDZ9jsy3DT
Content-Type: application/json

{
    "type": "Internet"
}
```

## Notas Adicionales

- Asegúrese de reemplazar los valores de los campos JSON según sea necesario para las operaciones que desee realizar.
- Es importante incluir siempre el token de autenticación en el encabezado de la solicitud para garantizar el acceso adecuado al API.

Este documento proporciona la guía necesaria para interactuar con el API de gestión de productos. Para cualquier otra consulta o detalle adicional, por favor, comuníquese con el equipo de soporte técnico.
