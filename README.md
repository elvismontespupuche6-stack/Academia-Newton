# Academia Newton — Sistema de Gestión Académica

Sistema web desarrollado para la gestión integral de matrículas, pagos y reportes financieros de **Academia Newton**, una academia preuniversitaria con múltiples sedes en la región de Lima.

---

## Tecnologías utilizadas

| Tecnología | Uso |
|------------|-----|
| Python 3.x | Lenguaje principal |
| Django 5.0 | Framework web |
| PostgreSQL | Base de datos en producción |
| SQLite | Base de datos en desarrollo |
| Bootstrap 5 | Interfaz de usuario |
| Chart.js 4 | Gráficos y reportes visuales |
| ReportLab | Generación de boletas en PDF |
| OpenPyXL | Exportación de reportes en Excel |
| WhiteNoise | Archivos estáticos en producción |
| Gunicorn | Servidor WSGI en producción |
| Render | Plataforma de despliegue |

---

## Funcionalidades principales

### Rol Secretaria
- Registro de alumnos en flujo de 4 pasos
- Gestión de alumnos (activos, inactivos, bloqueados)
- Matrículas y renovaciones con detección automática de transferencias entre sedes
- Registro de pagos (parcial/completo) con 3 métodos: efectivo, Yape, transferencia
- Generación de boletas en PDF formato 80mm (papel térmico)
- Reportes financieros por ciclo con exportación a Excel

### Rol Administrador
- Dashboard gerencial con KPIs globales y gráficos por sede
- Reportes comparativos entre sedes con indicador de salud financiera
- Historial financiero con filtros avanzados y exportación a Excel
- Mantenimiento de sedes, usuarios y ciclos académicos

---

## Características técnicas

- Sistema multi-sede con aislamiento de datos por sede
- Transferencia de alumnos entre sedes con confirmación
- Soft-delete en sedes y usuarios (no se eliminan de la BD)
- Sesiones con expiración automática a los 30 minutos
- Páginas de error personalizadas (403, 404, 500)
- Protección CSRF activa en todos los formularios

---

## Instalación local

```bash
# 1. Clonar el repositorio
git clone https://github.com/elvismontespupuche6-stack/Academia-Newton.git
cd Academia-Newton

# 2. Crear y activar entorno virtual
python -m venv venv
venv\Scripts\activate

# 3. Instalar dependencias
pip install -r requirements.txt

# 4. Crear archivo .env en la raíz del proyecto
# SECRET_KEY=tu-clave-secreta

# 5. Aplicar migraciones
python manage.py migrate

# 6. Correr el servidor
python manage.py runserver
```

---

## Estructura del proyecto

```
Academia-Newton/
├── config/          # Configuración de Django (settings, urls, wsgi)
├── web/
│   ├── models.py    # Modelos: Sede, Alumno, Ciclo, Matricula, Pago
│   ├── views/       # Vistas separadas por módulo
│   ├── templates/   # HTML por rol (secretaria / administrador)
│   ├── static/      # CSS, JS e imágenes
│   ├── middleware.py
│   ├── permisos.py  # Decorador de control de acceso por rol
│   └── utils.py     # Funciones de validación y cálculo
├── requirements.txt
├── Procfile         # Configuración para Render
└── render.yaml
```

---

## Equipo de desarrollo

Proyecto desarrollado como trabajo final para **SENATI** — 2026.

| Desarrollador | GitHub |
|---------------|--------|
| Elvis Montes | [@elvismontespupuche6-stack](https://github.com/elvismontespupuche6-stack) |
| Alexis Fernandez | [@fernandezmontesalexis-cloud](https://github.com/fernandezmontesalexis-cloud) |
