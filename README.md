# 📚 Web API Gestión Académica APE_3

Este proyecto implementa una API RESTful con **ASP.NET Web API** como backend y un frontend en **HTML, CSS y JavaScript puro**,
orientado a la gestión académica de asignaciones, carreras, cursos y estudiantes. Uno de los módulos clave es el **registro de usuarios**, 
que incluye múltiples validaciones en tiempo real y al enviar el formulario.

---

## 🚀 Tecnologías Utilizadas

- **Backend**: ASP.NET Web API (.NET Framework)  
- **Frontend**: HTML5, CSS3, JavaScript (Vanilla JS)  
- **Servidor de desarrollo**: Node.js (para levantar el frontend con un servidor simple)

### Herramientas
- Visual Studio (Backend)
- Visual Studio Code (Frontend)

### Dependencias
- Node.js
- Express (para el servidor local del frontend)

---

## 🏛️ Estructura del Proyecto

- 📁 WebApi_GestionAcademica          - Backend (API ASP.NET)
- 📁 Controllers                   -Controladores de la API
- 📁 Models                        - Modelos de datos
- 🗂️ WebApi_GestionAcademica.sln   - Archivo de solución de Visual Studio

- 📁 frontend                      - Frontend (HTML/CSS/JS)

- 🗂️ index.html                  - Página principal
- 🗂️ registro.html              - Página de registro
- 📁 css                         - Estilos CSS
- 📁 js                          - Scripts JS
- 🗂️ registro.js             - Validaciones del formulario de registro
- 
-🗂️ server.js                  - Servidor Node.js opcional (para pruebas o despliegue local)

✅ Validaciones Implementadas en el Registro (registro.js)
El formulario de registro incluye un conjunto completo de validaciones tanto en el cliente como contra la API, asegurando integridad de datos y buena experiencia de usuario:

1. Validación de Cédula Ecuatoriana
Algoritmo oficial (coeficientes y dígito verificador)

Debe contener exactamente 10 dígitos

Se rechazan cédulas incorrectas o ya registradas

2. Validación de Usuario Único
Al perder el foco (blur) en el campo usuario, se consulta la API

Se verifica si el nombre de usuario ya está en uso

Muestra mensajes dinámicos si el usuario existe

3. Validación de Correo Electrónico
Valida el formato usando expresión regular

Consulta la API para asegurar que el correo no esté ya registrado

4. Coincidencia de Contraseñas
Las contraseñas deben coincidir antes de enviar el formulario

Si no coinciden, se muestra un mensaje en tiempo real

5. Validación General al Enviar el Formulario
Antes de enviar:

Se revalidan las contraseñas

Se valida la cédula con el algoritmo

Se asegura que el usuario y correo sean únicos

Si todo es válido, se hace un POST a la API con los datos

⚙️ Instalación y Ejecución
## Backend (API)
1.- Clonar el repositorio
2.- Abrir WebApi_GestionAcademica.sln con Visual Studio
3.- Ejecutar la API (usualmente en https://localhost:44306)

## Frontend
1.- Descmprimir la carpeta del frontend
2.- Abrir la carpeta frontend/ con VS Code
3.- Si deseas levantar un servidor simple para pruebas locales:
npm install
node server.js
4.- Accede al frontend en http://localhost:3000/registro.html

🛡️ Seguridad y Manejo de Errores
Todos los errores de conexión con la API se manejan con try-catch

Se muestra al usuario un alert si ocurre un error inesperado

La validación en tiempo real evita peticiones innecesarias o registros inválidos
