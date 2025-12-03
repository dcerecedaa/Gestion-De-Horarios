# ✨ Sistema de Gestión de Horarios y Fichaje

**Sistema web completo para la gestión de horarios, fichajes de empleados y administración de ausencias, desarrollado con tecnologías modernas para empresas que buscan optimizar sus procesos de control horario.**

---

## 💻 Descripción General

Esta aplicación proporciona una solución integral para la gestión de recursos humanos mediante:

- **Sistema de fichaje digital** en tiempo real
- **Gestión completa de horarios** con validaciones inteligentes
- **Control de ausencias y permisos** con flujo de aprobación
- **Roles diferenciados** (administrador/empleado) con permisos específicos
- **Estadísticas y seguimiento** de horas trabajadas

**Ideal para empresas que necesitan automatizar sus procesos de control horario y gestión de personal.**

---

## 🚀 Características Principales

### 🔐 Autenticación y Seguridad
- ✅ **Sistema de registro y login** con roles (admin/usuario)
- ✅ **Encriptación avanzada** con bcrypt y migración SHA-256
- ✅ **Manejo seguro de sesiones** con localStorage
- ✅ **Validación robusta** de entradas en todas las rutas

### 👨‍💼 Panel de Administrador
- 🎯 **Gestión completa de usuarios**: Altas, bajas y modificaciones
- 🎯 **Creación y validación de horarios**: Con límites de horas anuales
- 🎯 **Aprobación de ausencias**: Flujo de trabajo con estados
- 🎯 **Visualización de estadísticas**: Horarios y fichajes consolidados

### 👩‍💼 Panel de Empleado
- ✨ **Sistema de fichaje intuitivo**: Entrada/salida con validaciones
- ✨ **Control visual de horas**: Progreso anual con alertas
- ✨ **Solicitud de ausencias**: Vacaciones, enfermedad y permisos
- ✨ **Consulta de horarios**: Visualización clara de turnos

### ⚙️ Validaciones Inteligentes
- 🧠 **Bloques de días libres**: (lunes-martes, miércoles-jueves, viernes-domingo)
- 🧠 **Límite de horas anuales**: 1,784 horas máximo por empleado
- 🧠 **Control de secuencia**: No permite fichajes duplicados
- 🧠 **Validación de archivos**: Solo PDF/JPG/PNG para justificantes

---

## 📋 Estructura de la Aplicación

| Módulo | Descripción |
|--------|-------------|
| **🔄 Autenticación** | Login, registro y gestión de sesiones |
| **📅 Gestión de Horarios** | Creación, modificación y validación |
| **⏰ Sistema de Fichaje** | Registro y cálculo de horas trabajadas |
| **🏖️ Gestión de Ausencias** | Solicitud y aprobación de permisos |
| **📊 Panel Administrativo** | Gestión global de usuarios y datos |
| **👤 Panel de Empleado** | Interfaz personalizada para usuarios |

---

## 🎮 Roles del Sistema

| Característica | 👑 **Administrador** | 👤 **Empleado** |
|----------------|---------------------|----------------|
| **Gestión usuarios** | Completa (CRUD) | Solo visualización propia |
| **Creación horarios** | ✅ Sí | ❌ No |
| **Aprobación ausencias** | ✅ Sí | ❌ No |
| **Registro fichaje** | ❌ No | ✅ Sí |
| **Solicitud ausencias** | ❌ No | ✅ Sí |
| **Ver estadísticas** | Todos los usuarios | Solo propias |

---

## 🛠️ Instalación y Configuración

### Prerrequisitos
- Node.js (v14 o superior)
- MySQL (v5.7 o superior)
- npm o yarn

### 🚀 Pasos de Instalación

1. **Clona el repositorio**
   ```bash
   git clone <repositorio>
   cd proyecto-gestion-horarios
Instala las dependencias

bash
npm install
Configura las variables de entorno

bash
cp .env.example .env
Edita el archivo .env:

env
DB_HOST=localhost
DB_USER=tu_usuario
DB_PASSWORD=tu_contraseña
DB_NAME=gestion_horarios
DB_PORT=3306
PORT=3000
Configura la base de datos

bash
# Importa el esquema SQL
mysql -u root -p < database/schema.sql

# O crea las tablas manualmente
# (ver archivo database/schema.sql)
Inicia el servidor

bash
npm start
# o para desarrollo
npm run dev
Accede a la aplicación

🌐 Login: http://localhost:3000/login/a.html

👑 Admin: http://localhost:3000/admin/Admin.html

👤 Usuario: http://localhost:3000/usu/User.html

📁 Estructura del Proyecto
bash
proyecto/
├── server.js                 # Servidor principal Express
├── package.json              # Dependencias y scripts
├── .env                      # Variables de entorno
├── conector/
│   └── db.js                 # Configuración MySQL con pool
├── vista/
│   ├── admin/                # Frontend administrador
│   │   ├── admin.html
│   │   ├── admin.js
│   │   └── admin.css
│   ├── login/                # Autenticación
│   │   ├── a.html
│   │   ├── b.css
│   │   └── c.js
│   └── usu/                  # Frontend empleado
│       ├── User.html
│       ├── user.js
│       └── user.css
├── routes/                   # Rutas API
│   ├── usuarios.routes.js
│   ├── horario.routes.js
│   ├── fichaje.js
│   ├── login.routes.js
│   └── ausencia.routes.js
├── database/                 # Esquemas y scripts SQL
│   └── schema.sql
├── uploads/                  # Archivos subidos (justificantes)
│   └── [usuario_id]/
│       └── [fecha]/
└── icono/                    # Recursos estáticos
    └── favicon.png
🔌 API Endpoints Principales
🔐 Autenticación
POST /api/login/login - Iniciar sesión

POST /api/login/register - Registrar nuevo usuario

👥 Gestión de Usuarios
GET /api/usuarios - Listar todos los usuarios

POST /api/usuarios - Crear nuevo usuario

PUT /api/usuarios/:id - Modificar usuario

DELETE /api/usuarios/eliminar - Eliminar usuario

📅 Gestión de Horarios
GET /api/horario - Obtener todos los horarios

POST /api/horario - Crear nuevo horario

PUT /api/horario/:idHorario - Modificar horario

DELETE /api/horario/:idHorario - Eliminar horario

⏰ Sistema de Fichaje
POST /api/fichaje - Registrar fichaje (entrada/salida)

GET /api/fichaje/ultimo/:id_usuario - Último fichaje del usuario

GET /api/fichaje/horas/:id_usuario - Estadísticas de horas

🏖️ Gestión de Ausencias
GET /api/ausencias - Listar ausencias (filtrable por estado)

POST /api/ausencias - Crear solicitud de ausencia

PUT /api/ausencias/:id - Actualizar estado de ausencia

💻 Stack Tecnológico
Categoría	Tecnologías
Backend	Node.js, Express.js
Frontend	HTML5, CSS3, JavaScript Vanilla
Base de Datos	MySQL
Estilos	Bootstrap 5, CSS Personalizado
Autenticación	bcrypt, localStorage
Manejo de Archivos	multer
Iconos	Bootstrap Icons
🛡️ Consideraciones de Seguridad
🔒 Contraseñas encriptadas con bcrypt (hash + salt)

🛡️ Protección contra inyección SQL con consultas parametrizadas

📁 Validación de tipos de archivo en subidas

🔐 Manejo seguro de sesiones sin datos sensibles en cliente

🌐 CORS configurado para entornos específicos

📈 Escalabilidad y Mantenimiento
Arquitectura
🏗️ Arquitectura modular con separación clara de responsabilidades

🔄 Pool de conexiones a MySQL para mejor rendimiento

📁 Estructura de carpetas organizada por funcionalidad

🎯 Frontend y backend desacoplados para mayor flexibilidad

Mejores Prácticas Implementadas
✅ Manejo centralizado de errores

✅ Validación en múltiples capas

✅ Logs detallados para debugging

✅ Código documentado y estructurado

🐛 Solución de Problemas Comunes
❌ Error de conexión a MySQL
Verifica las credenciales en .env

Asegúrate que MySQL esté corriendo: sudo service mysql status

Comprueba los permisos del usuario de la BD

❌ Archivos estáticos no cargan
Verifica las rutas en server.js

Confirma que los archivos existen en vista/

Revisa los permisos de lectura de las carpetas

❌ Error en validación de horarios
Formato correcto: "08:00-15:00" o "Libre"

Días libres deben ser bloques completos

Verifica límite de horas anuales (1,784)

❌ Problemas con subida de archivos
Tamaño máximo: 5MB

Formatos permitidos: PDF, JPG, PNG

Verifica permisos de escritura en carpeta uploads/

🔄 Flujo de Trabajo Típico
👤 Empleado se registra/logea en el sistema

⏰ Registra entrada al comenzar la jornada

📅 Consulta su horario asignado

🏖️ Solicita ausencia si es necesario

⏰ Registra salida al finalizar

👑 Administrador revisa y aprueba solicitudes

📊 Genera reportes de horas trabajadas

🤝 Contribuciones
¿Quieres mejorar el proyecto?

🍴 Haz un fork del repositorio

🌿 Crea una rama para tu funcionalidad

💻 Implementa tus cambios con pruebas

📝 Actualiza la documentación si es necesario

🔀 Envía un Pull Request para revisión

👨‍💻 Autor
Desarrollado por David Cereceda
🎓 Desarrollador Fullstack | Apasionado por crear soluciones eficientes

📧 Contacto: [tu-email@dominio.com]
🔗 LinkedIn: [tu-perfil-linkedin]
🐙 GitHub: [tu-usuario-github]

📄 Licencia
Este proyecto está bajo la Licencia MIT. Ver el archivo LICENSE para más detalles.

🙏 Agradecimientos
Equipo de Bootstrap por el increíble framework CSS

Comunidad de Node.js por las herramientas y librerías

Todos los contribuyentes que han ayudado a mejorar el proyecto

Usuarios finales por sus valiosos feedbacks y sugerencias
     
