# 🚗 Uber Rides Analytics — Dashboard Operativo

Análisis completo de las operaciones de Uber durante el año 2024, con foco en rendimiento de la flota, comportamiento de cancelaciones, ingresos por tipo de vehículo y eficiencia operativa.

---

## 📊 Herramientas utilizadas

| Herramienta | Uso |
|---|---|
| **Google Sheets** | Limpieza, transformación y exploración inicial del dataset |
| **Looker** | Dashboard interactivo con KPIs, tendencias y filtros dinámicos |

---

## 📁 Estructura del proyecto

```
uber-rides-analytics/
│
├── Uber.xlsx           # Dataset limpio con 150.000 registros
├── README.md           # Este archivo
└── capturas/           # Imágenes del dashboard (opcional)
```

---

## 🗂️ Dataset

El dataset contiene **150.000 registros** de viajes realizados entre el **1 de enero y el 31 de diciembre de 2024**.

**Columnas principales:**

| Campo | Descripción |
|---|---|
| `Booking ID` | Identificador único del viaje |
| `Booking Status` | Estado del viaje (Completed, Cancelled by Driver, etc.) |
| `Vehicle Type` | Tipo de vehículo (Auto, Bike, eBike, Go Mini, Go Sedan, Premier Sedan, Uber XL) |
| `Pickup / Drop Location` | Zona de origen y destino |
| `Booking Value` | Ingreso generado por el viaje |
| `Ride Distance` | Distancia recorrida en km |
| `Avg VTAT` | Tiempo promedio de llegada del conductor |
| `Driver Ratings` | Calificación del conductor |
| `Payment Method` | Método de pago (UPI, Cash, Credit Card, Uber Wallet, etc.) |
| `Cancellation Reason` | Motivo de cancelación (conductor o cliente) |

---

## 🔑 KPIs principales

| Métrica | Valor |
|---|---|
| Total de viajes | 150.000 |
| Tasa de viajes completados | 62% |
| Ingresos totales | $51.846.183 |
| Calificación promedio de conductores | 4,32 |

---

## 📈 Hallazgos clave

### Distribución de viajes por estado
- El **62%** de los viajes fue completado exitosamente.
- El **18%** fue cancelado por el conductor — la causa más frecuente fue "No especificado", seguida de problemas relacionados con el cliente y el vehículo.
- El **7%** fue cancelado por el cliente — en su mayoría sin motivo declarado.
- El **7%** resultó en "No Driver Found", con zonas como Khandsa y Barakhameba como puntos críticos.

### Tendencia mensual
- El volumen de viajes se mantuvo estable durante todo el año, oscilando entre **12.000 y 13.000 viajes por mes**.
- Los ingresos mensuales promediaron **$4 millones**, con un pico en marzo de **$5 millones**.

### Comportamiento por día de la semana
- El volumen de viajes es prácticamente uniforme a lo largo de la semana (~21.000 por día), sin diferencias significativas entre días hábiles y fines de semana.

### Flota e ingresos
- **Auto** es el tipo de vehículo con mayor volumen de ingresos totales: **$12.878.422**.
- La **tarifa por km** es muy similar entre todos los vehículos (~$20), siendo Go Sedan el más alto (**$20,78**) y eBike el más bajo (**$20,16**).
- El scatter plot de distancia vs. valor de reserva muestra que eBike recorre mayores distancias pero genera menor valor por viaje.

### Métodos de pago
- **UPI** y pagos no especificados dominan en todos los tipos de vehículo.
- Los pagos en efectivo son significativos, especialmente en vehículos de bajo costo como Auto y Go Mini.

### Tiempo de llegada (VTAT)
- **Uber XL** y **Bike** tienen el mayor VTAT promedio (9 minutos), mientras que el resto de la flota promedió **8 minutos**.

---

## 🔗 Dashboard interactivo

> 📌 [Ver dashboard en Looker →](https://datastudio.google.com/reporting/5b85dc65-c6d7-419a-ab90-09ed4d1a84e2)

El dashboard incluye tres vistas:
1. **Vista ejecutiva** — KPIs generales, tendencia mensual y distribución por estado
2. **Análisis operativo** — Cancelaciones por conductor y cliente, VTAT por vehículo, zonas sin conductor disponible
3. **Flota e ingresos** — Ingresos por tipo de vehículo, métodos de pago y tarifa por km

---

## 🧹 Proceso de limpieza (Google Sheets)

1. Conversión de fechas desde formato serial de Excel a fecha legible
2. Normalización de razones de cancelación (columna `Payment Method Limpio`, `Driver Cancellation Reason Limpio`)
3. Extracción del número de mes y día de la semana para análisis de tendencias
4. Eliminación de registros con `Booking Value` nulo en viajes no completados para métricas de ingreso

---

## 👤 Autor

**Jonathan Manzolido**
Estudiante de Análisis de Datos
