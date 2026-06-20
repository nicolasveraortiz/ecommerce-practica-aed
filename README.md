# CV Apart - Tech Co-Living & Workspace
## Actividad Formativa N.° 2: Diseñando un e-Commerce con Inteligencia Artificial
### Cátedra: Algoritmos y Estructuras de Datos | ISI - UTN FRRE

---

## 1. Nombre y Descripción del e-Commerce

* **Nombre del Proyecto:** CV Apart - Tech Co-Living & Workspace
* **Descripción Operativa:** Es una plataforma transaccional no convencional enfocada en la oferta, reserva y contratación por día de unidades de infraestructura habitacional especializada para ingenieros, desarrolladores de software y nómades digitales en Resistencia, Chaco. A diferencia de un e-commerce inmobiliario o turístico tradicional, el servicio paquetiza en una tarifa diaria única el acceso a hardware periférico de alta gama (displays curvos, insonorización profesional, servidores locales, UPS redundantes) y conectividad simétrica de misión crítica, encuadrándose como una solución tecnológica integrada y bajo demanda.

---

## 2. Diseño de los Registros (Backend Teórico en Memoria Interna)

Para modelar la información necesaria para el funcionamiento del sistema en un ambiente algorítmico, se diseñaron las siguientes estructuras utilizando la nomenclatura formal literaria de la cátedra:

```pascal
REGISTRO: Fecha (Estructura Anidada - Campo Continente)
CAMPOS:
    dia  : Entero        // Rango restringido: 1..31
    mes  : Entero        // Rango restringido: 1..12
    anio : Entero        // Representación cronológica de 4 dígitos
FIN_REGISTRO

REGISTRO: AlojamientoTech (Estructura Principal de Entidad)
CAMPOS:
    id_apartado    : Entero        // Campo Contenido [CLAVE PRIMARIA]
    denominacion   : AN(50)        // Campo Contenido (Alfanumérico para el nombre comercial)
    capacidad_max  : Entero        // Campo Contenido (Límite físico de usuarios)
    tarifa_diaria  : Real          // Campo Contenido (Precisión flotante para costos)
    fecha_alta     : Fecha         // CAMPO CONTINENTE (Registro Fecha embebido)
    disponibilidad : Carácter      // Campo Contenido (Código de estado lógico: 'D' u 'O')
FIN_REGISTRO

REGISTRO: Reserva (Estructura Transaccional de e-Commerce)
CAMPOS:
    id_reserva    : Entero        // Campo Contenido [CLAVE PRIMARIA DE OPERACIÓN]
    id_depto      : Entero        // Campo Contenido [CLAVE FORÁNEA - Relación con AlojamientoTech]
    dni_cliente   : Entero        // Campo Contenido [CLAVE SECUNDARIA]
    nombre_cliente: AN(45)        // Campo Contenido
    fecha_check_in: Fecha         // CAMPO CONTINENTE (Registro Fecha embebido)
    cant_noches   : Entero        // Campo Contenido
    monto_total   : Real          // Campo Contenido (Calculado: cant_noches * tarifa_diaria)
FIN_REGISTRO