# Proyecto de Gestión de Facturación

Este proyecto es una aplicación web desarrollada en PHP para el backend y Angular para el frontend. Está diseñado para gestionar la información de clientes, productos y proveedores mediante una interfaz sencilla y funciones CRUD (Crear, Leer, Actualizar y Eliminar).

## Funcionalidades

### Clientes

- **Listar Clientes**: Muestra una tabla con todos los clientes registrados, incluyendo su nombre, dirección, teléfono, cédula y correo electrónico.
- **Crear y Editar Clientes**: Formulario para crear nuevos clientes o editar los existentes. Los datos se envían al backend para ser procesados.
- **Eliminar Clientes**: Permite eliminar clientes de la lista.

### Productos

- **Listar Productos**: Muestra una tabla con los productos registrados, incluyendo código de barras, nombre del producto y si grava IVA.
- **Crear y Editar Productos**: Formulario para agregar nuevos productos o modificar los existentes.
- **Eliminar Productos**: Permite eliminar productos de la lista.

### Proveedores

- **Listar Proveedores**: Muestra una tabla con los proveedores registrados.
- **Crear y Editar Proveedores**: Formulario para gestionar la información de los proveedores.
- **Eliminar Proveedores**: Permite eliminar proveedores de la lista.

## Estructura del Proyecto

La estructura principal del proyecto incluye:

- **Controladores**: Manejan la lógica de negocio y las interacciones entre el frontend y el backend.
  - `clientes.controller.php`
  - `productos.controller.php`
  - `proveedores.controller.php`

- **Modelos**: Se encargan de la interacción con la base de datos.
  - `clientes.model.php`
  - `productos.model.php`
  - `proveedores.model.php`

- **Vistas (JavaScript)**: Manejan la interacción del usuario y las peticiones AJAX hacia los controladores.
  - `clientes.js`
  - `productos.js`

## Endpoints del Backend y Pruebas en JSON

### Clientes

- **Obtener todos los clientes**:
  - **Endpoint**: `GET /controllers/clientes.controller.php?op=todos`
  - **Respuesta**:
    ```json
    [
      {
        "id": 1,
        "Nombres": "Juan Pérez",
        "Direccion": "Calle Falsa 123",
        "Telefono": "0987654321",
        "Cedula": "1234567890",
        "Correo": "juan@example.com"
      },
      ...
    ]
    ```

- **Insertar/Editar cliente**:
  - **Endpoint**: `POST /controllers/clientes.controller.php?op=insertar`
  - **Cuerpo (FormData)**:
    ```json
    {
      "Nombres": "Juan Pérez",
      "Direccion": "Calle Falsa 123",
      "Telefono": "0987654321",
      "Cedula": "1234567890",
      "Correo": "juan@example.com"
    }
    ```
  
### Productos

- **Obtener todos los productos**:
  - **Endpoint**: `GET /controllers/productos.controller.php?op=todos`
  - **Respuesta**:
    ```json
    [
      {
        "id": 1,
        "Codigo_Barras": "1234567890123",
        "Nombre_Producto": "Producto A",
        "Graba_IVA": "Sí"
      },
      ...
    ]
    ```

- **Insertar/Editar producto**:
  - **Endpoint**: `POST /controllers/productos.controller.php?op=insertar`
  - **Cuerpo (FormData)**:
    ```json
    {
      "Codigo_Barras": "1234567890123",
      "Nombre_Producto": "Producto A",
      "Graba_IVA": "Sí"
    }
    ```

### Proveedores

- **Obtener todos los proveedores**:
  - **Endpoint**: `GET /controllers/proveedores.controller.php?op=todos`
  - **Respuesta**:
    ```json
    [
      {
        "id": 1,
        "Nombre_Proveedor": "Proveedor A",
        "Contacto": "contacto@proveedora.com",
        ...
      },
      ...
    ]
    ```

- **Insertar/Editar proveedor**:
  - **Endpoint**: `POST /controllers/proveedores.controller.php?op=insertar`
  - **Cuerpo (FormData)**:
    ```json
    {
      "Nombre_Proveedor": "Proveedor A",
      "Contacto": "contacto@proveedora.com",
      ...
    }
    ```
