# counterSystemAndroid
Repositorio de aplicación ContadorIoT para dispositivos Android

# ContadorIoT — CounterClient & DashboardReceiver

Repositorio con los dos proyectos Android usados en la evaluación **Aplicaciones Móviles para IoT (Unidad 2)**.

---

## 📁 Estructura del ZIP / repositorio

```
ContadorIoT/
├─ CounterClient/               ← Proyecto Android Studio (Cliente / Emisor)
├─ DashboardReceiver/           ← Proyecto Android Studio (Dashboard / Servidor)
├─ apks/                        ← APKs generados (opcional)
│  ├─ CounterClient.apk
│  └─ DashboardReceiver.apk
└─ README.md
```

---

## ✅ Requisitos previos (PC)

| Requisito                     | Versión recomendada |
|-----------------------------|---------------------|
| Android Studio               | Arctic Fox / Chipmunk o superior |
| SDK Platform                 | **Android 34** |
| Build Tools                  | **34.0.0** |
| Mínimo SDK del dispositivo   | **24 (Android 7.0)** |
| JDK                          | **Java 11** |
| ADB (Android Debug Bridge)   | Incluido con SDK |

---

## 📂 Rutas recomendadas (Windows)

> Para evitar errores de Gradle en Windows, usar rutas cortas sin espacios

```
C:\Dev\ContadorIoT\CounterClient
C:\Dev\ContadorIoT\DashboardReceiver
```

---

## 🚀 Cómo abrir en Android Studio

1. **Descomprime el ZIP**
2. Abre Android Studio → **Open**
3. Selecciona `CounterClient/` → abrir → esperar a que gradle sincronice
4. Repite con `DashboardReceiver/`
5. Si Android Studio pide descargar SDK o Build Tools → aceptar

---

## 🔧 Configuración importante en el código

### IP del servidor (DashboardReceiver)
En `CounterClient/MainActivity.kt` debe estar configurado así:

```kotlin
private var DASHBOARD_IP = "192.168.43.1" // IP del dispositivo que actúa como servidor
private val PORT = 5000
```

> 💡 **IMPORTANTE:** No usar la IP del cliente. La IP correcta del servidor suele ser la **Puerta de enlace (Gateway)** que aparece en la red Wi-Fi del cliente.

---

## 🏗 Cómo generar APK desde Android Studio

1. Build → **Build Bundle(s) / APK(s)** → **Build APK(s)**
2. Android Studio generará el archivo `.apk` en:
```
<nombre-del-proyecto>/app/build/outputs/apk/debug/app-debug.apk
```
3. Puedes copiar ese APK al teléfono o instalar con **ADB**

---

## 📱 Instalación del APK en Android

### Método 1 — Manual (sin ADB)
1. Copiar el `.apk` al teléfono
2. Abrir con gestor de archivos
3. Permitir instalación desde fuentes desconocidas

### Método 2 — Con ADB (recomendado)
```
adb install -r CounterClient/app/build/outputs/apk/debug/app-debug.apk
adb install -r DashboardReceiver/app/build/outputs/apk/debug/app-debug.apk
```

---

## 📡 Ejecución y prueba

| Paso | Acción |
|------|------------------------------------------------|
| 1 | Activar hotspot en el dispositivo **DashboardReceiver (servidor)** |
| 2 | Conectar el **Cliente (CounterClient)** a esa red Wi-Fi |
| 3 | Abrir primero **DashboardReceiver** — debe poner "Servidor escuchando" |
| 4 | En cliente, ingresar o dejar IP como `192.168.43.1` (gateway típica) |
| 5 | Presionar **Conectar al Dashboard** |
| 6 | Si la conexión es correcta → el servidor muestra "Cliente conectado" |
| 7 | Presionar **Incrementar y enviar** → número debe aparecer en el Dashboard |

---

## 🛠 Errores comunes y soluciones

| Error | Causa | Solución |
|------|-------|----------|
| `ECONNREFUSED` | El servidor no estaba ejecutando o IP incorrecta | Abrir DashboardReceiver primero y verificar que IP sea **Gateway**, no del cliente |
| `Android resource linking failed` | Falta AppCompat / Tema | Verificar dependencias y `Theme.Material3.NoActionBar` |
| No aparece `Rebuild Project` | Versión nueva de Android Studio | Usar `Build → Make Project` o `Build APKs` |

---

## 🧠 Notas útiles

- La IP del dispositivo **servidor** (hotspot) casi siempre es **192.168.43.1**
- El puerto local variable (ejemplo: 47182) que aparece en logs **no es un error**
- El puerto del servidor (5000) debe ser el mismo en ambos proyectos
- Puedes editar la IP desde el código o añadir un `EditText` para ingresarla manualmente

---

## ✒ Créditos

Proyecto desarrollado para la asignatura **Aplicaciones Móviles para IoT**  
Institución: **INACAP — Sede San Pedro de la Paz**  
Autor: **[ Cristian Alejandro Muñoz Mora ]**

---
