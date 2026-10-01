# Análisis Macroeconómico y Ecosistema Cripto (2021-2026) 📊

## 1. Descripción del Proyecto
Este proyecto es un análisis integral basado en datos que explora la relación entre el mercado financiero tradicional (acciones y divisas) y el ecosistema de criptomonedas durante un ciclo de mercado completo (2021 - 2026). 

El objetivo principal es responder a preguntas de negocio clave: ¿Existe correlación entre la renta variable y el riesgo descentralizado? ¿Cuándo ocurre el trasvase de capital hacia las "Altcoins" (Dominancia)? ¿Cómo impactan los grandes hitos históricos en la acción del precio?

## 2. Estructura del Repositorio
El proyecto sigue una arquitectura de datos organizada para facilitar su reproducibilidad:

📁 **`datos/raw/`**: Contiene los datasets originales extraídos vía API (Cripto y Macro).
📁 **`datos/processed/`**: Contiene el dataset final transformado, normalizado y listo para ingestar.
📁 **`notebooks/`**: Script de Python (`.ipynb`) con el proceso ETL (Extracción, Transformación y Carga) y análisis estadístico exploratorio (mapas de calor de correlación).
📁 **`dashboard/`**: Archivo `.pbix` con el cuadro de mando interactivo en Power BI.

## 3. Metodología y Pipeline Técnico
El flujo de trabajo se ha dividido en dos grandes fases:

1. **Ingeniería de Datos (Python - Pandas & yfinance):**
   * Extracción de datos financieros de la API de Yahoo Finance.
   * Resolución de formatos MultiIndex y sincronización de zonas horarias (UTC vs Local).
   * Generación de una estructura de formato largo (*Long Format*) para optimizar el modelado.
2. **Modelado y Visualización (Power BI):**
   * Diseño de un **Modelo en Estrella** (Star Schema) con tablas de dimensiones (`Dim_Calendario`, `Dim_Activos`) y una tabla de hechos (`Fact_cotizaciones`).
   * Desarrollo de métricas avanzadas mediante **DAX** (rendimientos YTD escalables, medias móviles, diferenciales de Alpha, control de granularidad diaria para evitar acumulación de precios y *Time Intelligence*).
   * Implementación de *Tooltips* narrativos impulsados por bases de datos de hitos históricos.

## 4. Informe del Análisis (Insights Clave)
Tras la estructuración y visualización de los datos, el análisis revela las siguientes conclusiones:

**Sincronización Macro-Cripto:** El gráfico de dispersión temporal (Scatter Plot) demuestra que, en periodos de expansión monetaria y apetito por el riesgo (como finales de 2021 o principios de 2024), el S&P 500 y Bitcoin muestran una fuerte correlación positiva. Sin embargo, Bitcoin actúa como un activo de "beta alta", amplificando los movimientos macroeconómicos tanto al alza como a la baja.
**Flujo de Capital y Dominancia (Altseasons):** El análisis de volumen apilado y el diferencial de rentabilidad mensual revelan patrones claros de rotación de capital. Típicamente, los flujos institucionales impulsan primero a Bitcoin y, semanas después de su estabilización, el capital rota hacia activos de mayor riesgo (como Ethereum o Solana), generando picos de dominancia en las "Altcoins" (barras verdes de diferencial en el panel de correlación).
**Resiliencia ante Eventos de Estrés:** El ecosistema mostró fuertes contracciones ante eventos endógenos (caída de Terra/Luna, quiebra de FTX en 2022) rompiendo temporalmente la correlación con el S&P 500. No obstante, la aprobación de los ETFs de Bitcoin en enero de 2024 marcó un punto de inflexión estructural, dotando al activo de un comportamiento de mercado mucho más institucionalizado y dependiente de la macroeconomía tradicional.

---
*Proyecto finalizado empleando Python y Power BI.*