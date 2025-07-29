# 🚀 Proyecto Java - Sistema de Login Creativo

Este proyecto es una aplicación Java de escritorio que implementa un sistema de login personalizado con interfaz gráfica (Swing), conexión a base de datos MySQL, envío de correos y redirección por roles. Además, emplea efectos visuales y validaciones para una mejor experiencia de usuario.

## 🧩 Características

- Interfaz moderna con imagen de fondo.
- Inicio de sesión con correo y contraseña.
- Mostrar/ocultar contraseña con checkbox.
- Validación de usuario desde base de datos MySQL.
- Redirección según rol (cliente, administrador, etc.).
- Envío de correos electrónicos de bienvenida o confirmación.
- Integración con librerías externas (`javax.mail`, `iText`, `MySQL Connector`, etc.).

## 📦 Estructura del Proyecto

Login/
├── src/ # Código fuente Java
│ ├── login/ # Lógica de autenticación
│ ├── Agencia/ # Módulos por roles (Agencia4, etc.)
├── *.jar # Librerías externas necesarias
├── build.xml # Archivo de construcción (Ant)
├── correo_generado.html # Plantilla de correo HTML
└── manifest.mf # Configuración del manifiesto

markdown
Copiar
Editar

## ⚙️ Requisitos

- Java JDK 8 o superior
- NetBeans IDE (recomendado)
- Servidor de base de datos MySQL
- Librerías externas (ya incluidas en el proyecto):
  - `mysql-connector-j-8.0.33.jar`
  - `javax.mail-api-1.6.2.jar`
  - `kernel-7.2.5.jar` (iText)
  - y más...

## 🛠️ Configuración

1. **Clonar o descomprimir el proyecto.**

2. **Importar el proyecto en NetBeans:**
   - `Archivo > Abrir Proyecto` y selecciona la carpeta `Login`.

3. **Conectar la base de datos:**
   - Asegúrate de tener un esquema con tabla `usuarios` y `roles`.
   - Edita la clase `ConexionBD.java` para poner tus credenciales de MySQL:
     ```java
     String url = "jdbc:mysql://localhost:3306/tu_base_datos";
     String user = "root";
     String password = "tu_contraseña";
     ```

4. **Ejecutar:**
   - Ejecuta la clase `LoginCreativo.java` desde `main()`.

## 🧪 Ejemplo de estructura MySQL

```sql
CREATE TABLE roles (
  id INT PRIMARY KEY,
  puesto VARCHAR(50)
);

CREATE TABLE usuarios (
  id INT PRIMARY KEY,
  usuario VARCHAR(100),
  password VARCHAR(100),
  nombre VARCHAR(100),
  FOREIGN KEY (id) REFERENCES roles(id)
);
