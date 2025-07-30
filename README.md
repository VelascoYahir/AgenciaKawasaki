# 🚀 Proyecto Java - Sistema de Login Creativo
Nombre del proyecto ("Sistema de venta de motos Kawasaki").

Número de equipo: 13

Integrantes ( "VELASCO LUIS YAHIR FERMIN - Desarrollador y diseñador", "MATEOS ORTIZ LUIS ANGEL - diseñador").

Este proyecto es una aplicación Java de escritorio de venta de motos Kawasaki que implementa un sistema de login personalizado con interfaz gráfica (Swing), conexión a base de datos MySQL, envío de correos y redirección por roles. Además, emplea efectos visuales y validaciones para una mejor experiencia de usuario.

Tipo de sistema ( Desktop App en Java, con Swing).

Librería externa implementada ("Usamos la librería 'correoElectronico' del Equipo 2 para enviar correos al registrar un usuario y al momento de comprar una moto (enviar factura)",  https://github.com/olmomomo/Libreria_correoElectronico    )

## 🧩 Funcionalidades clave


Aqui se muestra el CRUD de usuarios
<img width="1616" height="924" alt="image" src="https://github.com/user-attachments/assets/94e7b675-6dba-48ae-802e-d8e6d6c17302" />



Aqui se muestra el CRUD de productos
<img width="1624" height="927" alt="image" src="https://github.com/user-attachments/assets/9d1c5c40-1343-4d52-838b-27d895b7d9df" />



Aqui se compra una moto
<img width="1616" height="928" alt="image" src="https://github.com/user-attachments/assets/0f08d0ec-cdab-467f-b927-c335a8161a8c" />




<img width="1620" height="922" alt="image" src="https://github.com/user-attachments/assets/d89faca2-c2e3-47d9-8b28-ab70619699e3" />




<img width="1312" height="821" alt="image" src="https://github.com/user-attachments/assets/398c27a4-5ec5-4606-a701-3a9661563109" />




<img width="1614" height="927" alt="image" src="https://github.com/user-attachments/assets/c2aa3fd8-d0eb-49ea-9aff-0598547724c7" />




<img width="1909" height="891" alt="image" src="https://github.com/user-attachments/assets/fef359ce-1227-40b6-97fb-b0b548b54190" />




[angeljoseramirez_75_gmail_com_20250729_114836.pdf](https://github.com/user-attachments/files/21494782/angeljoseramirez_75_gmail_com_20250729_114836.pdf)


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
