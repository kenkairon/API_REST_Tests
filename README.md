# Gestión de Productos

## Automatización de pruebas para API Rest en Plataforma de Comercio Electrónico

### Módulo 6 - Sesión 5 - Actividad 4

### Equipo 4: 
- Felipe Lobos
- Fabiola Díaz
- Eduardo Arellano
- Carlos Vasquez

### Objetivo: 
Demostrar y fortalecer las habilidades de testeo en APIs REST mediante la creación y ejecución de una suite de pruebas automatizadas, utilizando herramientas como Postman y Newman.

### Contexto

Imagina que formas parte del equipo de aseguramiento de calidad de una empresa que gestiona una plataforma de comercio electrónico. La API REST de la plataforma es responsable de manejar procesos críticos como el registro y autenticación de usuarios, y la gestión del catálogo de productos. Debido a la alta integración y el impacto directo que tiene en la experiencia del usuario, es fundamental asegurar que cada endpoint funcione de forma correcta y segura. Tu tarea es simular un escenario real de pruebas, en el cual deberás validar la correcta ejecución de operaciones esenciales en la API, poniendo a prueba tus conocimientos y habilidades en testeo automatizado.

### API de prueba: [click aquí](https://github.com/fabyDiaz/Gestion-de-productos-y-usuarios.git)

### Requerimientos

Configuración del Entorno en Postman:
 - Configura un entorno llamado “DemoAPI Enviromen” que incluya variables clave, como:
    - baseUrl: La URL base de la API (por ejemplo, http://localhost:8080/pi/v1).
    - JwtToken: Variable para almacenar el token de autenticación obtenido tras el login.
    - productoId: Variable para guardar el identificador del producto creado.

Creación de una Colección de Pruebas:
- Crea una colección denominada “Suite de Pruebas Demo API” que incluya al menos las siguientes peticiones:
    - Registro de Usuario:
        - Endpoint: POST/auth/register
        - Función: Permitir el registro de un nuevo usuario y confirmar mediante una respuesta existosa.
    - Login de Usuario:
        - Endpoint: POST/auth/login
        - Función: Autenticar al usuario registrado y obtener un token JWT.
    - Creación de Producto:
        - Endpoint: POST/productos
        - Función: Crear un nuevo producto en el catálogo utilizando el token JWT para autenticación.
    - Obtención de Producto:
        - Endpoint: GET/productos/{ Para cada petición, incluye scripts de tests en Postman que verifiquen:
        -         Para cada petició
        - El código de estado HTTP.

        - ▪

    - o

    Automatización con Newman:
Exporta la colección y el entorno de Postman. Luego utiliza Newman para ejecutar la suite de pruebas desde la línea de comandos, integrando la ejecución en un flujo automatizado que simule un proceso de integración continua.



### Instrucciones 
1. Instalar newman y newman-reporter
    ````cmd
    npm install -g newman
    npm install -g newman-reporter-html
    npm install -g newman-reporter-json
    ````
2. Ejecutar coleccion y generar reporte
    ```cmd
    newman run '.\Suite de Pruebas Demo API.postman_collection.json'  -e '.\DemoApi  Enviromen.postman_environment.json' -r htmlextra --reporter-htmlextra-export reporte.html 
    ```
3. Iniciar reporte html
    ````cmd
    start .\reporte.html 
    ````


4. Ejecucion de newman solamente con reporte por consola
    ````cmd
    newman run '.\Suite de Pruebas Demo API.postman_collection.json' -e '.\DemoApi  Enviromen.postman_environment.json'
    ````
