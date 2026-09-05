# Tarea · Saber 11: ¿puede el contexto socioeconómico predecir el desempeño académico?

**Cloud Computing 4 Data Science · Magíster en Data Science UAI 2026**

## El caso

Modelo de **clasificación**: predecir si un estudiante quedará sobre o bajo la mediana
nacional en matemáticas de la prueba Saber 11, conociendo **solo su contexto**
(estrato, educación de los padres, internet y computador en casa, tipo de colegio,
área, jornada, género y departamento). El modelo no sabe nada del estudiante como
estudiante — si aun así predice bien, ese es el hallazgo.

## Fuente de los datos

**ICFES** (Instituto Colombiano para la Evaluación de la Educación) ·
"Resultados únicos Saber 11" · portal de datos abiertos de Colombia (Socrata).
- Página: https://www.datos.gov.co/d/kgxf-xxbe
- API: https://www.datos.gov.co/resource/kgxf-xxbe.json

**Privacidad — minimización de datos desde el origen:** la extracción usa `$select`
en la API para traer solo las columnas que el modelo necesita. Ningún
cuasi-identificador (ID del estudiante, fecha de nacimiento, colegio, municipio)
entra al pipeline.

## Contenido

| Archivo | Qué es |
|---|---|
| `EDA_saber11.ipynb` | Exploración: carga, limpieza, brechas socioeconómicas, construcción del target `rendimiento_alto`, guardado del dataset de modelo |
| `saber11_muestra.parquet` | Muestra de trabajo: 150.000 estudiantes del período 2022-4, 13 columnas minimizadas |
| `Propuesta_Caso_Saber11.docx` | La propuesta del caso presentada al grupo |

## Estado

- [x] Caso investigado y datos verificados
- [x] EDA y target construido (clases balanceadas 51/49)
- [ ] Entrenamiento (regresión logística vs. Random Forest) → exportar `.pkl`
- [ ] App FastAPI local con `/predict`
