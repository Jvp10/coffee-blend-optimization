# Formulación Óptima de Mezcla de Café

> Optimización de la composición de una mezcla de café utilizando Programación Lineal y análisis de sensibilidad para minimizar costos cumpliendo requerimientos nutricionales.

## Resumen Ejecutivo

Este proyecto desarrolla un modelo de **programación lineal** para determinar la combinación óptima de ingredientes en una formulación de café que minimiza el costo total, cumpliendo simultáneamente restricciones nutricionales y de formulación.

La solución incorpora:

- ✔️ Optimización matemática con Gurobi  
- ✔️ Análisis de sensibilidad completo  
- ✔️ Evaluación de robustez mediante simulación Monte Carlo  
- ✔️ Perfil nutricional de la mezcla óptima  

## Problema

En procesos de formulación de alimentos es común que:

> “No se dispone de información cuantitativa que permita caracterizar el desempeño operativo del proceso, dificultando la evaluación de su comportamiento y la toma de decisiones.”

**Brechas identificadas**

- Formulación basada en criterios manuales  
- Costos no optimizados  
- Falta de análisis de sensibilidad  
- Riesgo ante variabilidad de precios  

## Objetivos

### Objetivo general

Determinar la mezcla de café de **mínimo costo** que cumpla con todos los requerimientos nutricionales y de formulación.

### Objetivos específicos

- Modelar el problema como **programación lineal**  
- Incorporar restricciones nutricionales  
- Analizar **precios sombra y rangos de optimalidad**  
- Evaluar robustez frente a variaciones de precios  
- Obtener el perfil nutricional final de la mezcla  

---

## Arquitectura de la Solución

Pipeline

- Ingesta: Excel con ingredientes y requerimientos

- Modelado: variables de decisión por ingrediente

- Optimización: minimización de costo

- Post-análisis: sensibilidad y robustez

- Simulación: variación aleatoria de precios

## Stack Tecnológico

- Lenguaje: Python

- Optimización: Gurobi (gurobipy)

- Análisis de datos: pandas, numpy

- Visualización: matplotlib, plotly

- Fuente de datos: Excel

## Metodología
1. Formulación del modelo

- Variables de decisión

- Proporción de cada ingrediente en la mezcla

- Función objetivo

- Minimizar costo total de la formulación

Restricciones

- Balance de masa (la mezcla suma 1)

- Límites nutricionales mínimos y máximos

- Cotas por ingrediente (LB/UB)

## Análisis de sensibilidad

Se evaluó:

- Rangos de optimalidad de coeficientes

- Precios sombra de restricciones

- Holguras del modelo

- Rangos RHS de factibilidad

Hallazgos clave

- La restricción de mezcla es la única activa

- Varias restricciones nutricionales presentan holgura

- La solución muestra robustez moderada ante cambios de costos

## Simulación Monte Carlo

- Se ejecutaron 1000 corridas variando ±20% los precios de ingredientes para evaluar:

- Distribución del costo óptimo

- Estabilidad de la mezcla

- Riesgo de incremento de costo

Objetivo: cuantificar la robustez económica del modelo.

## Resultados

- Se obtuvo una mezcla de costo mínimo factible

- La solución es estable ante variaciones moderadas de precios

- Las restricciones nutricionales cumplen para el costo establecido

## Valor analítico

- Identificación de restricciones críticas

- Medición de robustez del modelo

- Base para decisiones de reformulación

## Nota sobre el Código

El código fuente no se publica por tratarse de propiedad intelectual del autor.

Este repositorio tiene fines de portafolio y documenta:

✔️ Enfoque matemático

✔️ Arquitectura del modelo

✔️ Metodología analítica

✔️ Resultados obtenidos

Para revisión técnica o colaboración profesional, contactar directamente.

👤 Autor

Jorge Vasquez

Ingeniería de procesos · Optimización Industrial
