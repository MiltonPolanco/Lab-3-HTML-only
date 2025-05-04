# Sistema Integrado de Reportes

**Descripción:**  
Aplicación de escritorio desarrollada en Python con Tkinter para la generación de reportes, visualización de gráficos y ejecución de consultas SQL sobre el sistema de reservas de canchas deportivas.

---

## 1. Requisitos

- **Python**: versión 3.8 o superior.  
- **PostgreSQL**: servidor operativo con la base de datos configurada y las siguientes tablas:
  - `reserva`
  - `cancha`
  - `usuario`
  - `pago`
  - `servicio_adicional`
  - `reserva_servicio`
- **Permisos**: credenciales de usuario con privilegios de lectura y escritura en la base de datos.

---

## 2. Instalación y Entorno

### 2.1 Clonar repositorio

git clone https://github.com/tu-usuario/sistema-reportes.git
cd sistema-reportes
2.2 Instalar dependencias
bash
Copiar
Editar
pip install tk psycopg2-binary tkcalendar matplotlib fpdf
2.3 (Opcional) Crear y activar un entorno virtual
bash
Copiar
Editar
python -m venv venv
source venv/bin/activate     # Linux / macOS
venv\Scripts\activate        # Windows
3. Configuración de la conexión
Edite el bloque de conexión en el archivo admin.py con sus parámetros de PostgreSQL:

python
Copiar
Editar
self.conn = psycopg2.connect(
    dbname="negroshima",
    user="postgres",
    password="0512",
    host="localhost",
    options='-c client_encoding=UTF8'
)
Ajuste los valores de dbname, user, password y host según su entorno.

4. Ejecución
Para iniciar la aplicación, ejecute:

bash
Copiar
Editar
python admin.py
Al cargar, se mostrará una interfaz con las siguientes pestañas:

Reportes por Fecha: filtro por rango de fechas y estado, exportación a CSV o PDF.

Gráficas: generación dinámica de gráficos de barras y sectores.

Editor SQL: área para ejecutar consultas arbitrarias y visualizar resultados.

Ingresos por Cancha: resumen de ingresos agrupados.

Uso de Servicios: conteo de servicios adicionales utilizados.

Reservas por Usuario: detalle de reservas filtrado por usuario.

Duración de Reservas: análisis según tiempo de reserva.

Comparativo Mensual: métricas de un mes específico.

