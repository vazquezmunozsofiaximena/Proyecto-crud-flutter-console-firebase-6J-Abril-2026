Configurar Firebase para Flutter es un paso fundamental para escalar cualquier aplicación. Aquí tienes la guía completa para preparar tu entorno en Windows, desde Node.js hasta la vinculación con tu proyecto.

---

## 1. Software necesario para NPM y Node.js
Para gestionar paquetes como **Firebase CLI**, necesitas el entorno de ejecución **Node.js**, el cual incluye automáticamente **NPM** (Node Package Manager).

* **Instalador oficial:** Descarga la versión **LTS** (Long Term Support) desde [nodejs.org](https://nodejs.org/). Es la más estable para desarrollo.
* **Permisos:** Necesitas una cuenta con permisos de **Administrador** en Windows para la instalación global.

---

## 2. Verificación de instalación
Antes de instalar nada, verifica si ya cuentas con estas herramientas abriendo una terminal (**PowerShell** o **CMD**) y ejecutando:

```bash
node -v
npm -v
```
> **Nota:** Si aparecen números de versión (ej. `v20.12.0`), ya estás listo. Si recibes un error de "comando no encontrado", sigue los pasos a continuación.

---

## 3. Instalación paso a paso de Node.js (Global)

1.  **Ejecuta el instalador:** Abre el archivo `.msi` descargado.
2.  **Acepta los términos:** Haz clic en *Next* hasta llegar a la sección de "Custom Setup".
3.  **Configuración Global:** Asegúrate de que la opción **"Add to PATH"** esté seleccionada (esto es lo que permite usar `npm` de manera global en cualquier carpeta).
4.  **Herramientas adicionales:** El instalador te preguntará si deseas instalar "Tools for Native Modules". Es recomendable marcar la casilla si planeas trabajar con plugins complejos en Flutter.
5.  **Finalizar:** Haz clic en *Install* y reinicia tu computadora (o al menos la terminal) para que los cambios en el PATH surtan efecto.

---

## 4. Instalación de Firebase CLI (`firebase-tools`)
Una vez que `npm` funciona, instalaremos las herramientas de Firebase.

### a) Comando de instalación global
Ejecuta el siguiente comando en tu terminal:
```bash
npm install -g firebase-tools
```
El parámetro `-g` indica que la instalación es **global**, permitiéndote usar el comando `firebase` desde cualquier directorio de tu PC.

### b) Acceso a Firebase con tu cuenta de Google
Para vincular tu terminal con tu consola de Firebase, utiliza el comando:
```bash
firebase login
```
**Procedimiento:**
1.  Se abrirá automáticamente una ventana en tu navegador web.
2.  Selecciona tu cuenta de Google vinculada a Firebase.
3.  Haz clic en **"Permitir"** para otorgar acceso a las herramientas de línea de comandos.
4.  En la terminal verás el mensaje: `✔  Success! Logged in as user@gmail.com`.

---

## 5. Integración específica con Flutter
Para que Firebase "hable" con Flutter de forma moderna, Google recomienda usar el paquete **FlutterFire CLI**.

1.  **Instala el activador de Dart:**
    ```bash
    dart pub global activate flutterfire_cli
    ```
2.  **Configura tu proyecto:**
    Navega hasta la carpeta raíz de tu aplicación Flutter y ejecuta:
    ```bash
    flutterfire configure
    ```
Este comando te permitirá seleccionar tus proyectos existentes en la consola de Firebase y generará automáticamente el archivo `firebase_options.dart`, configurando Android, iOS y Web al mismo tiempo.

---

### Resumen de comandos útiles
| Tarea | Comando |
| :--- | :--- |
| **Verificar versiones** | `node -v` / `npm -v` |
| **Instalar Firebase CLI** | `npm install -g firebase-tools` |
| **Iniciar Sesión** | `firebase login` |
| **Cerrar Sesión** | `firebase logout` |
| **Listar proyectos** | `firebase projects:list` |
