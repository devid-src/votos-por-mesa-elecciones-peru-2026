# Documentación del Dataset de Mesas de Votación - ONPE

--

## Descripción General

Este dataset contiene información sobre **88,064 mesas de votación** disponibles en la API oficial de la Oficina Nacional de Procesos Electorales (ONPE) de Perú. El archivo `data_verificado.csv` consolida el registro completo de mesas electorales con sus resultados de votación.

## Metodología de Extracción

### Fuente de Datos

- **Origen**: API oficial de la ONPE
- **Endpoint**: Consulta de mesas electorales
- **Tipo de Extracción**: Consulta por rango de IDs

### Proceso de Recopilación

- **Rango de Búsqueda**: 0 a 999,999
- **Total de Registros Obtenidos**: 88,064 mesas
- **Método**: Iteración secuencial a través de identificadores únicos

## Estructura del Dataset

### Columnas del CSV

| Campo          | Tipo   | Descripción                                      |
| -------------- | ------ | ------------------------------------------------ |
| `mesa`         | Entero | Identificador único de la mesa electoral         |
| `departamento` | Texto  | Departamento donde se ubica la mesa              |
| `provincia`    | Texto  | Provincia del departamento                       |
| `distrito`     | Texto  | Distrito específico                              |
| `local`        | Texto  | Institución educativa o local de votación        |
| `electores`    | Entero | Cantidad de electores habilitados para votar     |
| `emitidos`     | Entero | Total de votos emitidos en la mesa               |
| `validos`      | Entero | Total de votos válidos (excluye blancos y nulos) |
| `Keiko`        | Entero | Votos obtenidos por Keiko Fujimori               |
| `Sanchez`      | Entero | Votos obtenidos por Pedro Castillo Terrones      |
| `Aliaga`       | Entero | Votos obtenidos por Luis Aliaga                  |
| `Nieto`        | Entero | Votos obtenidos por Óscar Nieto                  |
| `Belmon`       | Entero | Votos obtenidos por Rodrigo Belmont              |
| `Alvares`      | Entero | Votos obtenidos por Hernando de Alvares Thorne   |
| `Lopez Chau`   | Entero | Votos obtenidos por Juan López Chau              |
| `blancos`      | Entero | Votos en blanco                                  |
| `nulos`        | Entero | Votos nulos o anulados                           |
| `estado`       | Texto  | Estado de la mesa (ej: "Contabilizada")          |

## Características del Dataset

### Cobertura Geográfica

- **Alcance**: Total
- **División Administrativa**: Estructura de Departamentos, Provincias y Distritos
- **Locales**: Incluye todas las instituciones educativas habilitadas como centros de votación

### Información Electoral

- **Candidatos**: Se incluyen 7 candidatos presidenciales principales
- **Votos**: Se registran categorías de votos válidos, blancos y nulos
- **Participación**: Se documenta la participación electoral por mesa

### Estados de Procesamiento

El campo `estado` indica la situación de cada mesa:

- **Contabilizada**: Mesa con resultados finales procesados

## Discrepancia de Datos - Actas Faltantes

⚠️ **NOTA IMPORTANTE**: Existe una discrepancia significativa entre los datos reportados y los disponibles en el sistema:

- **Mesas Reportadas por ONPE**: 92,766
- **Mesas Obtenidas del Dataset**: 92,731
- **Actas Agregadas**: Se identificaron y agregaron más de **4,000 actas que comienzan con 9**
- **Actas Pendientes**: **35 actas** aún por encontrar

### Preguntas Abiertas

¿Dónde están el resto de actas electorales? ¿Por qué no figuran en el sistema disponibilizado por la ONPE?
¿Por que las actas que comienzan con 9 favores de una manera desproporcionada a Sanchez?

**Ejemplo de Mesa Faltante:**

- **Mesa No. 087704**: Esta acta electoral NO aparece en el dataset extraído, a pesar de estar dentro del rango de búsqueda consultado (0-999,999).

### Fuentes Combinadas

Este dataset es el resultado de la combinación de dos fuentes de datos:

1. **Extracción Directa de API ONPE**: Datos obtenidos mediante consulta iterativa a la API oficial
2. **Dataset de PrimeInstitute**: Extraida por ellos mediante api de la ONPE

---

## Contacto

Para consultas, sugerencias o reportar errores:

- **Email**: devid_src@proton.me
