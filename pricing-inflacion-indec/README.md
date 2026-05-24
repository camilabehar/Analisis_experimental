# 📊 Motor de Pricing Demográfico y Efecto Sustitución ante Shocks Inflacionarios

**Un enfoque empírico para la optimización de estrategias de *Pricing* y Surtido en contextos de alta inflación.**

Este proyecto traduce microdatos oficiales y agregados macroeconómicos en recomendaciones accionables de negocio. Utilizando series del Instituto Nacional de Estadística y Censos (INDEC) de Argentina, el análisis modela la erosión del salario real y predice el comportamiento del consumidor (efecto ingreso y efecto sustitución) para responder a una pregunta directiva crítica.

## 🎯 La Pregunta de Negocio
> *"Con la inflación proyectada, ¿nuestros clientes mantendrán su nivel de consumo en la línea 'premium', o enfrentaremos un riesgo de abandono (churn) que justifique el lanzamiento urgente de una segunda marca (flanker brand) más económica?"*

## 🛠️ Fuentes de Datos (Microdatos INDEC)
El análisis se fundamenta en el procesamiento empírico de las siguientes bases oficiales:
* **Cuenta de Generación del Ingreso (CGI):** Remuneración al Trabajo Asalariado (RTA) y Puestos de Trabajo del sector registrado, segmentados por variables demográficas (edad y sexo).
* **Índice de Precios al Consumidor (IPC):** Serie histórica de cobertura nacional para la deflactación y cálculo del poder adquisitivo base 2016=100.

## ⚙️ Metodología y Pipeline de Datos
1. **Ingesta y Limpieza:** Extracción automatizada desde repositorios en la nube (`pandas`, `read_excel`), manejo de estructuras no estandarizadas y tratamiento de valores nulos.
2. **Feature Engineering (Transformación Económica):** * Cálculo del Salario Nominal Promedio Demográfico: $W_{nominal} = \frac{RTA}{Puestos}$.
   * Construcción del Índice de Salario Real (Poder de Compra): w = (W/IPC)*100
3. **Nowcasting:** Extrapolación de series temporales hacia 2025 integrando variables adelantadas de inflación y negociaciones paritarias.
4. **Data Visualization:** Creación de *dashboards* estáticos de alto impacto directivo utilizando `seaborn` y `matplotlib`.

## 💡 Hallazgos y Recomendación Estratégica
* **Perforación del Umbral Crítico:** El modelo proyecta que el salario real del target principal perforará el 80% de su capacidad histórica de compra (base 2016).
* **Ilusión Monetaria y Elasticidad:** Ajustar los precios indexando directamente al IPC general genera una **falacia de composición**. El servicio se encarece en términos reales para el consumidor, incrementando exponencialmente la elasticidad precio de la demanda.
* **Recomendación:** Implementar una arquitectura de precios defensiva. Se dictamina el **lanzamiento de una segunda marca (o plan *lite*)** para absorber el *down-trading* defensivo del consumidor, retener el volumen de ventas, diluir costos fijos y mitigar la fuga hacia competidores.
---
*Análisis desarrollado para portfolio de Data Science Aplicada a la Economía Empresarial.*
