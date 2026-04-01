# 🖨️ Mi Copiadora — Sistema de Ventas

Sistema completo para gestionar ventas de un negocio de fotocopiado e impresiones.
Desarrollado en Python Flask con SQLite. Incluye CRM con sistema de puntos de fidelización.

---

## 🔑 Usuarios por defecto

| Usuario | PIN  | Rol   |
|---------|------|-------|
| Admin   | 1234 | Admin |
| Apoyo   | 0000 | Apoyo |

> **⚠️ Importante:** Cambia los PINs desde la base de datos después del primer despliegue.

---

## 💻 Instalación local

### Requisitos
- Python 3.10 o superior → [python.org/downloads](https://www.python.org/downloads/)
- Conexión a internet para instalar dependencias

### Pasos

1. **Descarga el proyecto** y descomprime la carpeta `mi_copiadora`

2. **Abre una terminal** (símbolo del sistema en Windows, Terminal en Mac/Linux)
   en la carpeta del proyecto

3. **Instala las dependencias:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Inicia la aplicación:**
   ```bash
   python app.py
   ```

5. **Abre el navegador** en: `http://localhost:5000`

6. **Acceso desde celular** (en la misma red WiFi):
   - En la PC, abre Símbolo del sistema y escribe `ipconfig` (Windows) o `ifconfig` (Mac/Linux)
   - Busca tu IP local (ej: `192.168.1.5`)
   - En el celular, abre: `http://192.168.1.5:5000`

---

## ☁️ Publicar en Render.com (gratis)

1. **Crea cuenta en GitHub:** [github.com](https://github.com)

2. **Crea un repositorio nuevo** llamado `mi-copiadora` (público)

3. **Sube todos los archivos** del proyecto al repositorio:
   - Opción fácil: arrastra los archivos al repositorio desde la web de GitHub
   - O usa git: `git init`, `git add .`, `git commit -m "inicio"`, `git push`

4. **Crea cuenta en Render.com:** [render.com](https://render.com)
   (puedes usar la misma cuenta de Google o email)

5. En Render, haz clic en **"New +"** → **"Web Service"**

6. **Conecta con GitHub** y selecciona el repositorio `mi-copiadora`

7. Render detecta automáticamente la configuración del `render.yaml`. Haz clic en **"Create Web Service"**

8. Espera **3-5 minutos** mientras Render construye la app

9. **Copia la URL generada** (ej: `mi-copiadora.onrender.com`) y compártela con tu personal de apoyo

> **Nota sobre el plan gratuito:** La app "duerme" después de 15 min de inactividad.
> El primer acceso puede tardar ~30 segundos en despertar. El sistema hace pings automáticos
> cada 10 minutos para mantenerla activa mientras alguien la está usando.

---

## 📱 Uso diario

### Iniciar sesión
1. Abre la URL de la app en el celular o computadora
2. Ingresa tu PIN de 4 dígitos con el teclado en pantalla
3. **Admin (PIN 1234):** accede al Panel completo
4. **Apoyo (PIN 0000):** accede directamente a Ventas

### Registrar una venta
1. En la pantalla de **Ventas**, toca el servicio que el cliente pidió
2. Ingresa la cantidad (o usa los botones rápidos: 1, 5, 10, 20, 50, 100)
3. Opcionalmente, busca al cliente por nombre o celular para acumular puntos
4. El total se calcula automáticamente
5. Toca **"Registrar venta"**

### Sistema de puntos CRM
- Cada S/10 en compras = 1 punto para el cliente
- Con 10 puntos → 1 copia gratis (Copia B&N texto)
- Para canjear: en Ventas, selecciona al cliente y usa el botón "Canjear puntos"
- El admin puede ver el ranking de clientes frecuentes en **CRM**

### Exportar reporte Excel
1. Ve al **Panel** (admin)
2. Selecciona el rango de fechas
3. Haz clic en **"Descargar Excel"**
4. El archivo incluye 5 hojas: Resumen, Ventas por día, Por servicio, Detalle completo y Rentabilidad

---

## 🗂️ Módulos del sistema

| Módulo      | Quién accede | Descripción |
|-------------|-------------|-------------|
| Ventas      | Admin + Apoyo | Registro rápido de ventas con botones grandes |
| Panel       | Solo Admin   | Dashboard con estadísticas y gráficos del día |
| Historial   | Solo Admin   | Tabla de ventas con filtros y exportación |
| Inventario  | Solo Admin   | Control de hojas y reposiciones |
| Servicios   | Solo Admin   | Editar precios y activar/desactivar |
| CRM         | Solo Admin   | Gestión de clientes y puntos de fidelización |

---

## 🛠️ Soporte técnico

Si la app no inicia, verifica:
- Que Python 3.10+ esté instalado: `python --version`
- Que las dependencias estén instaladas: `pip install -r requirements.txt`
- Que el puerto 5000 esté libre (cierra otras apps si es necesario)

---

*Desarrollado con Flask + SQLAlchemy + openpyxl · Diseño mobile-first para celulares desde 360px*
