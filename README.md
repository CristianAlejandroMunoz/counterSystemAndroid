# counterSystemAndroid
Repositorio de aplicación ContadorIoT para dispositivos Android

# 📲 Instalación rápida — Contador IoT (APKs Android)

Este repositorio contiene **dos aplicaciones Android (.apk)** listas para instalar en dispositivos físicos para la demostración del proyecto **Contador IoT**.

---

## 📁 Ubicación de los archivos APK

```
ContadorIoT/
├─ README.md ← este archivo
└─ APKs/
   ├─ CounterClient.apk          ← Instalar en dispositivo CLIENTE (TCL 408)
   └─ DashboardReceiver.apk      ← Instalar en dispositivo SERVIDOR (HUAWEI Y5 2018)
```

---

## ⚙️ Requisitos

| Elemento | Detalle |
|----------|--------|
| Dispositivo **Servidor** | HUAWEI Y5 2018 – debe activar **Zona Wi-Fi / Hotspot** |
| Dispositivo **Cliente** | TCL 408 – debe conectarse al hotspot del servidor |
| Permiso necesario | **Permitir instalación desde fuentes desconocidas** en ambos dispositivos |
| Método de instalación | Copia manual del APK o mediante cable USB / gestor de archivos |

---

## 🚀 Instalación del APK en dispositivo SERVIDOR (DashboardReceiver.apk)

1. Copiar `DashboardReceiver.apk` desde la carpeta `/APKs/` al dispositivo **HUAWEI Y5 2018**.
2. Abrir el archivo desde **Gestor de archivos / Descargas**.
3. Aceptar **Instalar desde fuente desconocida** si Android lo solicita.
4. Instalar y abrir la aplicación.
5. **Activar el Hotspot Wi-Fi** del teléfono (este dispositivo será el SERVIDOR).
6. La app mostrará **"Servidor escuchando"** si está lista.

---

## 📡 Instalación del APK en dispositivo CLIENTE (CounterClient.apk)

1. Copiar `CounterClient.apk` al dispositivo **TCL 408**.
2. Conectar este dispositivo al **Hotspot del HUAWEI** (servidor).
3. Abrir el archivo y permitir instalación desde fuente desconocida.
4. Iniciar la aplicación y presionar **Conectar al Dashboard**.
5. Confirmar que la IP por defecto sea **192.168.43.1** (IP típica del hotspot Android).
6. Cuando aparezca **"Conectado"**, comenzar a presionar el botón **Incrementar y Enviar**.

---

## ✅ Orden de ejecución recomendado

| Paso | Acción | Dispositivo |
|------|--------|------------|
| 1 | Instalar `DashboardReceiver.apk` y abrir la app | **HUAWEI (Servidor)** |
| 2 | Activar hotspot Wi-Fi | **HUAWEI (Servidor)** |
| 3 | Instalar `CounterClient.apk` | **TCL (Cliente)** |
| 4 | Conectarse al hotspot del HUAWEI | **TCL (Cliente)** |
| 5 | Abrir `CounterClient` y conectar | **TCL (Cliente)** |
| 6 | Verificar que el servidor muestre "Cliente Conectado" | **HUAWEI (Servidor)** |
| 7 | Enviar conteos y monitorear en Dashboard | Ambos |

---

## 🎯 Consejo rápido para pruebas

- Si al conectar aparece **ECONNREFUSED**, asegúrate de:
  - Haber abierto primero la app del servidor.
  - Haber conectado el cliente a la red Wi-Fi del servidor.
  - Tener la IP configurada como **192.168.43.1** y puerto **5000**.

---

## 🧠 Recordatorio final

> **Servidor = DashboardReceiver.apk (HUAWEI Hotspot)**  
> **Cliente = CounterClient.apk (TCL conectado al hotspot)**

---

💬 Si necesitas instalar mediante **ADB con cable USB**, puedo generar un script `.bat` para instalación automática. Solo dime: **“Generar script ADB”**.
