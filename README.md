# 🚀 Proyecto Java - Sistema de Login Creativo
Nombre del proyecto ("Sistema de venta de motos Kawasaki").

Número de equipo: 13

Integrantes ( "VELASCO LUIS YAHIR FERMIN - Desarrollador y diseñador", "MATEOS ORTIZ LUIS ANGEL - diseñador").

Este proyecto es una aplicación Java de escritorio de venta de motos Kawasaki que implementa un sistema de login personalizado con interfaz gráfica (Swing), conexión a base de datos MySQL, envío de correos y redirección por roles. Además, emplea efectos visuales y validaciones para una mejor experiencia de usuario.

Tipo de sistema ( Desktop App en Java, con Swing).

Librería externa implementada ("Usamos la librería 'correoElectronico' del Equipo 2 para enviar correos al registrar un usuario y al momento de comprar una moto (enviar factura)",  https://github.com/olmomomo/Libreria_correoElectronico    )

## 🧩 Características

- Interfaz moderna con imagen de fondo.
- Inicio de sesión con correo y contraseña.
- Mostrar/ocultar contraseña con checkbox.
- Validación de usuario desde base de datos MySQL.
- Redirección según rol (cliente, administrador, etc.).
- Envío de correos electrónicos de bienvenida o confirmación.
- El sistema utiliza javax.mail para enviar correos al registrarse o iniciar sesión. Asegúrate de configurar correctamente los datos del remitente en la clase correspondiente (Correo.java o similar).
- Integración con librerías externas (`javax.mail`, `iText`, `MySQL Connector`, etc.).
- La imagen de fondo debe estar en esta ruta: C:\Users\angel\Downloads\Kawasaki-ZX-6R-2024-min-1200x675.png, Puedes cambiar la ruta o reemplazar por otra imagen de fondo en el constructor de LoginCreativo.

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
