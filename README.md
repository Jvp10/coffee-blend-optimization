# Formulación Óptima de Mezcla de Café

> Optimización de la composición de una mezcla de café mediante Programación Lineal para minimizar costos cumpliendo requerimientos nutricionales y de formulación.

---

## Resumen Ejecutivo

Este proyecto desarrolla un modelo de **programación lineal (PL)** para determinar la combinación óptima de ingredientes en una formulación de café que minimiza el costo total, cumpliendo simultáneamente restricciones nutricionales y operativas.

La solución integra:

- ✔️ Optimización matemática con Gurobi  
- ✔️ Análisis de sensibilidad del modelo  
- ✔️ Evaluación de robustez mediante simulación Monte Carlo (1000 corridas)  
- ✔️ Verificación del perfil nutricional de la mezcla óptima  

El enfoque permite cuantificar el desempeño económico de la formulación y apoyar la toma de decisiones en entornos con incertidumbre de precios.

---

## Problema

En procesos de formulación de alimentos es frecuente que:

> “No se dispone de información cuantitativa que permita caracterizar el desempeño operativo del proceso, dificultando la evaluación de su comportamiento y la toma de decisiones.”

### Brechas identificadas

- Formulación basada en criterios manual  
- Costos no optimizados sistemáticamente  
- Ausencia de análisis de sensibilidad  
- Exposición al riesgo por variabilidad de precios  

---

## Objetivos

### Objetivo general

Determinar la mezcla de café de **mínimo costo** que cumpla con los requerimientos nutricionales y de formulación.

### Objetivos específicos

- Modelar el problema como **programación lineal**  
- Incorporar restricciones nutricionales explícitas  
- Analizar sensibilidad del modelo (holguras y precios sombra)  
- Evaluar robustez frente a variaciones de precios  
- Obtener el perfil nutricional de la mezcla óptima  

---

## Arquitectura de la Solución

**Pipeline analítico**

1. **Ingesta de datos**  
   - Excel con ingredientes y requerimientos  

2. **Modelado matemático**  
   - Variables de decisión por ingrediente  
   - Función objetivo de costo mínimo  
   - Restricciones de mezcla y nutrición  

3. **Optimización**  
   - Resolución con Gurobi  

4. **Post-análisis**  
   - Sensibilidad y holguras  

5. **Simulación de incertidumbre**  
   - Monte Carlo sobre precios  

---

## Stack Tecnológico

- **Lenguaje:** Python  
- **Optimización:** Gurobi (gurobipy)  
- **Análisis de datos:** pandas, numpy  
- **Visualización:** matplotlib, plotly  
- **Fuente de datos:** Excel  

---

## Metodología

### Formulación del modelo

**Variables de decisión**

- Proporción de cada ingrediente en la mezcla

**Función objetivo**

- Minimizar el costo total de la formulación

**Restricciones**

- Balance de masa (∑xᵢ = 1)  
- Límites nutricionales mínimos y máximos  
- Cotas de inclusión por ingrediente (LB/UB)  

---

## Análisis de sensibilidad

Se evaluaron:

- Holguras de restricciones  
- Precios sombra  
- Comportamiento de la restricción de mezcla  

### Hallazgos clave

- La restricción de mezcla actúa como principal limitante económica  
- Varias restricciones nutricionales presentan holgura positiva  
- La solución muestra robustez moderada ante cambios en costos  

---

## Simulación Monte Carlo

Se ejecutaron **1000 corridas** variando ±20% los precios de ingredientes para evaluar:

- Distribución del costo óptimo  
- Estabilidad de la solución  
- Riesgo de incremento de costo  

**Propósito:** cuantificar la robustez económica del modelo bajo incertidumbre paramétrica.

---

## Resultados principales

- Se obtuvo una mezcla factible de **costo mínimo**  
- La solución permanece estable ante variaciones moderadas de precios  
- Los requerimientos nutricionales se cumplen en la solución óptima  
- La dispersión del costo indica **riesgo controlado**

---

## Cómo reproducir (entorno de referencia)

Este proyecto fue desarrollado en el siguiente entorno computacional:

- **Python:** 3.10+  
- **Optimizador:** Gurobi (gurobipy)  
- **Análisis de datos:** pandas, numpy  
- **Visualización:** matplotlib, plotly  
- **Fuente de datos:** archivos Excel  

### Flujo general de ejecución

1. Carga de datos desde Excel (ingredientes y requerimientos)  
2. Construcción del modelo de programación lineal  
3. Optimización del costo de la mezcla con Gurobi  
4. Análisis de sensibilidad (holguras y precios sombra)  
5. Simulación Monte Carlo (1000 corridas, ±20% en costos)  
6. Visualización de la distribución del costo óptimo  

### Notas

- Los resultados publicados corresponden a ejecuciones reales del modelo.  
- El repositorio documenta el enfoque metodológico y analítico.  

---

## Nota sobre el código

El código fuente completo no se publica por tratarse de propiedad intelectual del autor.

Este repositorio tiene fines de portafolio y documenta:

- ✔️ Enfoque matemático  
- ✔️ Arquitectura del modelo  
- ✔️ Metodología analítica  
- ✔️ Resultados obtenidos  

Para revisión técnica o colaboración profesional, contactar directamente.

---

## Valor analítico

Este enfoque permite:

- Identificar restricciones realmente vinculantes  
- Cuantificar la robustez económica de la formulación  
- Apoyar decisiones de reformulación y compras  
- Reducir incertidumbre en planificación de costos  

---

## 👤 Autor

**Jorge Vasquez**  
Ingeniería de procesos · Optimización industrial
