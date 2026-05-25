# 📅 WeekPlanner — Dr. Julio Leyrer

Sistema de planificación semanal con recordatorios automáticos por email.

## 🚀 Setup en 5 pasos

### Paso 1 — Crear el repositorio en GitHub

1. Ve a [github.com/new](https://github.com/new)
2. Nombre del repositorio: **`WeekPlanner`** (exactamente así)
3. Marca **Public**
4. **NO** marques "Add README" (ya tenemos uno)
5. Crea el repositorio

### Paso 2 — Subir los archivos

Desde la carpeta `WeekPlanner` en tu computador, ejecuta en terminal:

```bash
git init
git add .
git commit -m "feat: WeekPlanner inicial"
git branch -M main
git remote add origin https://github.com/JLOLYR/WeekPlanner.git
git push -u origin main
```

### Paso 3 — Activar GitHub Pages

1. Ve a tu repositorio en GitHub → **Settings** → **Pages**
2. En "Source" selecciona: **Deploy from a branch**
3. Rama: **main** / Carpeta: **/ (root)**
4. Guarda — en 1-2 minutos tu dashboard estará en:
   👉 **https://jlolyr.github.io/WeekPlanner/**

### Paso 4 — Configurar contraseña de aplicación Gmail

Para que GitHub Actions pueda enviar correos desde tu Gmail:

1. Ve a tu cuenta Google → **Seguridad** → **Verificación en 2 pasos** (actívala si no la tienes)
2. Luego ve a → **Contraseñas de aplicación**
3. Selecciona "Otra (nombre personalizado)" → escribe "WeekPlanner GitHub"
4. Copia la contraseña de 16 caracteres que te genera

### Paso 5 — Agregar Secrets en GitHub

1. En tu repositorio → **Settings** → **Secrets and variables** → **Actions**
2. Agrega estos 3 secrets con el botón "New repository secret":

| Nombre | Valor |
|--------|-------|
| `GMAIL_USER` | `j.leyrer01@gmail.com` |
| `GMAIL_APP_PASSWORD` | (la contraseña de 16 dígitos del paso 4) |
| `RECIPIENT_EMAIL` | `j.leyrer01@gmail.com` |

✅ **¡Listo!** Los correos se enviarán automáticamente.

---

## 📬 Recordatorios automáticos

| Día | Hora | Tipo |
|-----|------|------|
| Lunes | 8:30 AM | Recopilación semanal — formulario para agregar actividades |
| Martes | 8:30 AM | Recordatorio de actividades pendientes |
| Miércoles | 8:30 AM | Recordatorio de actividades pendientes |
| Jueves | 8:30 AM | Recordatorio de actividades pendientes |
| Viernes | 8:30 AM | Recordatorio de actividades pendientes |

> **Nota:** El cron usa UTC. Chile está en UTC-4 (verano) o UTC-3 (invierno). Si los emails llegan desincronizados, ajusta el cron en los archivos `.github/workflows/*.yml`.

### Probar un email manualmente

1. Ve a tu repositorio → **Actions**
2. Selecciona "📅 Recordatorio Lunes" o "📬 Recordatorio Diario"
3. Haz clic en **Run workflow**

---

## 🎯 Funcionalidades del Dashboard

- **Vista semanal** con pipeline por día (Lun–Vie)
- **Actividades carryover**: las no completadas de semanas pasadas aparecen destacadas
- **Categorías**: Docencia, Investigación, Administración, Personal
- **Deadlines** con alertas visuales de vencimiento
- **Estadísticas** con 4 gráficos interactivos
- **Historial** completo con filtros
- **Modo oscuro/claro** — se guarda tu preferencia
- **Exportar datos** como JSON (backup)
- **Atajo**: presiona `N` para agregar nueva actividad

---

## 📁 Estructura del proyecto

```
WeekPlanner/
├── index.html              # Dashboard principal
├── README.md               # Esta guía
└── .github/
    └── workflows/
        ├── monday-reminder.yml   # Email lunes 8:30 AM
        └── daily-reminder.yml    # Email mar-vie 8:30 AM
```

---

## 💾 Almacenamiento

Los datos se guardan en el **localStorage** de tu navegador. Esto significa:
- Los datos persisten entre sesiones en el mismo navegador/dispositivo
- Para hacer backup: usa el botón **Exportar** en el dashboard
- Para transferir a otro dispositivo: importa el JSON exportado (próximamente)

---

*WeekPlanner — Sistema de planificación para académicos e investigadores*
