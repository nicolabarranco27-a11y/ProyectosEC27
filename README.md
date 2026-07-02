# BullySalta

**Plataforma integral para la prevención, detección y gestión del acoso escolar**

BullySalta es un sistema digital diseñado para instituciones educativas de la Provincia de Salta que permite a alumnos, docentes y familias intervenir de manera temprana y coordinada frente a situaciones de acoso escolar. La plataforma unifica el reporte de incidentes, el seguimiento institucional de cada caso y la difusión de contenido preventivo en un solo entorno seguro y accesible.

Desarrollado por [EstalingradoCorp](https://github.com/estalingradocorp) — Nicola Barranco Mentesana, a cargo del proyecto.

---

## Contexto

El acoso escolar requiere canales de comunicación claros, seguros y con trazabilidad. BullySalta nace para resolver tres problemas concretos:

1. **Alumnos** necesitan una forma confidencial de reportar sin miedo a represalias.
2. **Escuelas** necesitan herramientas para gestionar, dar seguimiento y documentar cada caso.
3. **Familias** necesitan información y recursos para detectar señales y acompañar el proceso.

La plataforma opera bajo el marco de la Ley Nacional N.º 26.892 (Convivencia Escolar) y la Ley Provincial N.º 8.406.

> Proyecto en desarrollo — prototipo funcional.

---

## Módulos

### Alumnos
- Reporte guiado en 4 pasos con interfaz progresiva
- Opción de anonimato preservando la identidad del denunciante
- Adjunto de evidencias multimedia
- Código único de seguimiento generado aleatoriamente
- Radar de bienestar escolar (encuesta semanal de clima áulico)
- Recursos de orientación categorizados por tema
- Vinculación familiar mediante código de 4 caracteres

### Escuelas
- Panel de gestión de casos con listado y detalle completo
- Dashboard con KPIs y gráficos estadísticos (Chart.js)
- Filtros por tipo, estado, fecha y búsqueda por texto o código
- Trazabilidad cronológica de cada actuación institucional
- Registro de intervenciones con estado asociado (Recibido → En análisis → Cierre)
- Generación de actas oficiales listas para imprimir o exportar como PDF
- Visualización de evidencias con lightbox integrado
- Radar escolar con métricas semanales de participación, seguridad y exclusión

### Padres
- Vinculación segura con hijos mediante código
- Contenido preventivo organizado en módulos pedagógicos
- Recursos para detección temprana y acompañamiento familiar
- Guías sobre convivencia escolar y ciudadanía digital
- Dashboard de progreso formativo

---

## Funcionalidades clave

- Roles independientes con paneles y navegación propia
- Interfaz responsiva adaptada a dispositivos móviles
- Modo offline con datos simulados (prototipo funcional sin backend)
- Persistencia opcional mediante API REST (backend Python)
- Notificaciones tipo toast no invasivas
- Arquitectura SPA con renderizado dinámico del DOM

---

## Stack tecnológico

| Capa | Tecnología |
|------|-----------|
| Frontend | HTML5, CSS3, JavaScript ES6+ |
| Estilos | Tailwind CSS (CDN) |
| Gráficos | Chart.js |
| Backend | Python 3, FastAPI / Flask |
| Base de datos | SQLite |
| PDF | Impresión nativa del navegador |

---

## Instalación y uso

### Requisitos
- Navegador actualizado
- Python 3.9+ (solo para backend)
- Conexión a internet (CDN Tailwind, Chart.js)

### Frontend standalone
```bash
Abrir BullySalta.html en el navegador
```
Los datos se almacenan en memoria. No hay persistencia entre recargas.

### Frontend + Backend
```bash
# 1. Configurar entorno
cd backend
cp .env.example .env     # Crear archivo de configuración

# 2. Iniciar servidor
python -m venv venv
venv\Scripts\activate   # Windows
pip install -r requirements.txt
python run.ps1          # Inicia en http://localhost:8000

# 3. Servir frontend (otra terminal)
python -m http.server 8080
# Abrir http://localhost:8080/BullySalta.html
```

### Dispositivos móviles
El archivo debe servirse desde un servidor web. Las rutas `file://` no ejecutan JavaScript en navegadores móviles modernos.

```bash
# Desde la carpeta del proyecto
python -m http.server 8080
# Abrir http://<IP_LOCAL>:8080/BullySalta.html en el celular
```

---

## Estructura del repositorio

```
BullySalta/
├── BullySalta.html          # Aplicación frontend (SPA)
├── api-client.js            # Cliente HTTP para API REST
├── backend/
│   ├── app/                 # Lógica del servidor
│   ├── data/                # Base de datos
│   ├── requirements.txt     # Dependencias Python
│   ├── seed_data.py         # Datos semilla para pruebas
│   ├── run.ps1              # Script de inicio
│   ├── .env.example         # Modelo de configuración
│   └── .env                 # Configuración local (no subir)
├── .gitignore               # Archivos excluidos del repo
├── iniciar.ps1              # Inicio rápido integrado
├── INFORME_CAMBIOS.md       # Registro de cambios
└── README.md
```

---

## Roadmap previsto

- [x] Reporte de incidentes paso a paso
- [x] Panel de gestión escolar con trazabilidad
- [x] Módulo de contenido preventivo para familias
- [x] Radar de bienestar escolar
- [x] Generación de actas oficiales
- [ ] Autenticación y gestión de usuarios real
- [ ] Migración a frontend modular (componentes)
- [ ] Notificaciones push y alertas por estado
- [ ] Integración con sistemas de gestión educativa (GEM)
- [ ] Despliegue en producción con base de datos centralizada

---

## Licencia

© 2026 EstalingradoCorp. Todos los derechos reservados.

Diseñado para instituciones educativas de la Provincia de Salta.

---

*Proyecto a cargo de Nicola Barranco Mentesana — EstalingradoCorp*
