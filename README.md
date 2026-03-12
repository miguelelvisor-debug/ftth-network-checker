# 📡 FTTH Network Checker

Herramienta de análisis y reporting para redes de fibra óptica FTTH.  
Lee un CSV con el estado de los nodos de red y genera un **informe HTML interactivo** con KPIs, alertas y detalle completo.

> Desarrollada a partir de experiencia real como técnico de telecomunicaciones en proyectos de despliegue FTTH.

---

## 🖥️ Demo del informe

El informe generado incluye:

- **KPIs en tiempo real**: nodos activos, en alerta, caídos, SLA estimado, velocidades medias
- **Resumen por zona**: visión geográfica del estado de la red
- **Top incidencias**: nodos con mayor número de fallos en el mes
- **Alertas de revisión**: nodos sin revisar en más de 30 días
- **Tabla detallada**: todos los nodos con estado, splitters y velocidades

---

## 🚀 Instalación y uso

### 1. Clonar el repositorio
```bash
git clone https://github.com/tu-usuario/ftth-network-checker.git
cd ftth-network-checker
```

### 2. Instalar dependencias
```bash
pip install -r requirements.txt
```

### 3. Ejecutar con los datos de ejemplo
```bash
python main.py
```

El informe se genera en `reports/informe_ftth.html`. Ábrelo en cualquier navegador.

### 4. Usar con tus propios datos
```bash
python main.py --csv ruta/a/tus_datos.csv --output reports/mi_informe.html
```

---

## 📁 Estructura del proyecto

```
ftth-network-checker/
├── main.py                  # Punto de entrada
├── requirements.txt
├── data/
│   └── nodos.csv            # Datos de ejemplo
├── reports/                 # Informes generados (gitignored)
└── src/
    ├── ftth_analyzer.py     # Lógica de análisis y métricas
    └── report_generator.py  # Generación del informe HTML
```

---

## 📋 Formato del CSV de entrada

| Campo | Tipo | Descripción |
|---|---|---|
| `nodo_id` | str | Identificador único del nodo |
| `zona` | str | Zona geográfica |
| `municipio` | str | Municipio |
| `tipo` | str | Tipo de nodo: `OLT` o `NAP` |
| `estado` | str | `activo`, `alerta` o `caído` |
| `ultima_revision` | date | Fecha última revisión (YYYY-MM-DD) |
| `incidencias_mes` | int | Número de incidencias en el mes |
| `splitters_activos` | int | Splitters en uso |
| `splitters_total` | int | Capacidad total de splitters |
| `velocidad_bajada_mbps` | float | Velocidad de bajada medida |
| `velocidad_subida_mbps` | float | Velocidad de subida medida |

---

## 🛠️ Stack técnico

- **Python 3.10+**
- **pandas** — análisis y transformación de datos
- **Jinja2** — generación de informes HTML con plantillas
- Salida en **HTML estático** — sin dependencias externas para visualizar

---

## 👤 Autor

**Miguel Angel Susarte**  
Técnico de Telecomunicaciones → Developer  
[LinkedIn](https://linkedin.com/in/miguelangel) · [GitHub](https://github.com/tu-usuario)
