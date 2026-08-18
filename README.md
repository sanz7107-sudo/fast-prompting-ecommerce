# Fast Prompting en Acción: Automatización de contenido para e-commerce

**Autora:** Amparo Sanz  
**Curso:** Diplomatura en Data Science – Prompt Engineering  
**Comisión:** #96165  

## 1. Introducción

### Nombre del proyecto
**Aplicación de Fast Prompting para la automatización de contenido en e-commerce**

### Presentación del problema
Muchos pequeños emprendimientos y tiendas online utilizan redes sociales como uno de sus principales canales de promoción y comunicación. Sin embargo, producir contenido atractivo de manera constante requiere tiempo, conocimientos de marketing digital y, en muchos casos, recursos económicos que un pequeño negocio no posee.

La consecuencia puede ser una publicación irregular, poco consistente o poco adaptada al público objetivo, reduciendo las posibilidades de alcance, interacción y conversión.

Este proyecto continúa la propuesta de la Preentrega 1 y busca demostrar, mediante una POC en Jupyter Notebook, cómo distintas configuraciones de prompts pueden mejorar la generación automática de contenido comercial.

### Propuesta de solución
La POC recibe información básica de un producto:
- nombre;
- características;
- público objetivo;
- canal;
- tono;
- objetivo de comunicación.

A partir de esos datos se construyen distintas versiones de prompts. Se compara un **prompt básico** con un **prompt estructurado mediante técnicas de Fast Prompting**, incorporando rol, contexto, objetivo, restricciones y formato de salida.

El resultado esperado es una publicación utilizable en redes sociales que contenga texto promocional, llamado a la acción y hashtags.

### Viabilidad
La POC es técnicamente viable porque requiere únicamente Python, Jupyter Notebook y acceso a un modelo de lenguaje mediante API. No requiere entrenamiento de modelos ni infraestructura especializada.

Para controlar costos, la implementación:
1. permite visualizar los prompts sin consumir API;
2. separa las pruebas comparativas de la generación final;
3. realiza una sola consulta en el flujo productivo;
4. limita la extensión solicitada;
5. registra el uso de tokens informado por la API cuando está disponible.

La generación de imágenes queda como mejora futura opcional. Esto permite concentrar la POC en la experimentación de Fast Prompting y evitar dependencias o costos adicionales.

## 2. Objetivos

### Objetivo general
Desarrollar una POC que demuestre cómo Fast Prompting puede mejorar la generación automática de contenido para pequeños e-commerce.

### Objetivos específicos
- Diseñar prompts reutilizables para contenido comercial.
- Comparar un prompt simple con uno estructurado.
- Analizar claridad, consistencia, adecuación al canal y cumplimiento de requisitos.
- Reducir consultas innecesarias a la API.
- Crear una solución adaptable a distintos productos, públicos y tonos.
- Evaluar las mejoras respecto de la propuesta inicial.

## 3. Metodología

El proyecto se desarrolla en cinco etapas:

1. **Definición del problema:** se delimita la POC a la generación de una publicación comercial.
2. **Ingreso de variables:** se recopilan los datos relevantes del producto.
3. **Diseño de prompts:** se construye una versión básica y una versión optimizada.
4. **Experimentación:** se ejecutan ambos prompts sobre el mismo caso para poder comparar.
5. **Optimización:** el flujo final utiliza únicamente el prompt optimizado, evitando consultas duplicadas.

La comparación de prompts se utiliza como experimento de la notebook y no como comportamiento obligatorio de una aplicación en producción.

## 4. Herramientas y tecnologías

- **Python:** lógica de la POC.
- **Jupyter Notebook:** demostración reproducible.
- **OpenAI API:** generación de texto.
- **Variables de entorno:** protección de la API key.

### Técnicas de prompting
**Role prompting:** se asigna al modelo el rol de especialista en marketing digital y e-commerce.

**Context prompting:** se proporcionan producto, audiencia, canal, tono y objetivo.

**Prompt estructurado:** se separan claramente contexto, tarea, restricciones y formato esperado.

**Constraints:** se establecen límites explícitos para reducir respuestas demasiado extensas o fuera de objetivo.

**Output formatting:** se define la estructura de la respuesta para obtener resultados consistentes.

**Prompt templates:** las variables se separan de las instrucciones, permitiendo reutilizar el mismo prompt con diferentes productos.

## 5. Implementación

La implementación completa se encuentra en `Fast_Prompting_Ecommerce.ipynb`.

La notebook permite:
- configurar un producto;
- construir dos prompts;
- inspeccionarlos sin consumir API;
- ejecutar una comparación opcional;
- ejecutar el flujo optimizado con una sola llamada;
- observar métricas básicas de uso.

## 6. Optimización de costos

La estrategia de costos distingue dos escenarios:

**Experimento académico:** 2 consultas, una para el prompt básico y otra para el optimizado. Esto permite demostrar la mejora.

**Uso productivo:** 1 consulta por contenido generado. Una vez seleccionado el prompt optimizado, no existe necesidad de volver a ejecutar el prompt básico.

El costo monetario no se fija en el repositorio porque depende del modelo y de las tarifas vigentes. La notebook muestra tokens de entrada y salida cuando la API los informa, de modo que el análisis pueda actualizarse sin modificar la arquitectura.

## 7. Mejoras respecto de la Preentrega 1

La primera propuesta planteaba un conjunto amplio de contenidos de texto e imagen. En esta segunda etapa se transforma la idea en una POC concreta y medible.

Las principales mejoras son:
- reducción del alcance a un caso demostrable;
- prompts parametrizados y reutilizables;
- comparación controlada entre estrategias;
- restricciones y formato de salida explícitos;
- análisis del número de llamadas a la API;
- separación entre experimentación y uso productivo.

## 8. Conclusión

La POC demuestra que el valor del Prompt Engineering no depende únicamente de formular instrucciones más largas, sino de proporcionar al modelo información relevante de forma clara, estructurada y reutilizable.

Fast Prompting permite transformar una solicitud genérica en un proceso controlado. Para un pequeño e-commerce, esto puede reducir el tiempo dedicado a redactar contenido y mejorar su consistencia sin necesidad de desarrollar o entrenar un modelo propio.

## Ejecución

1. Instalar dependencias:

```bash
pip install -r requirements.txt
```

2. Configurar la variable de entorno `OPENAI_API_KEY`.
3. Abrir `Fast_Prompting_Ecommerce.ipynb`.
4. Ejecutar las celdas en orden.
5. Cambiar `usar_api = True` únicamente cuando se quiera consumir la API.

> Nunca subir una API key al repositorio.
