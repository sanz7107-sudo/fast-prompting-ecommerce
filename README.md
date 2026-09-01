# IA: Entretejiendo Imaginación y Algoritmos
## Fast Prompting aplicado a la automatización de contenido para e-commerce

**Autora:** Amparo Sanz  
**Curso:** Diplomatura en Data Science – Prompt Engineering  
**Comisión:** #96165  

## Resumen

Este proyecto aborda una problemática frecuente en pequeños e-commerce: la necesidad de producir contenido promocional de forma constante sin disponer siempre de tiempo, conocimientos de marketing o presupuesto para tercerizar la tarea.

La propuesta desarrolla una prueba de concepto (POC) en Jupyter Notebook que utiliza técnicas de **Fast Prompting** para generar dos recursos complementarios a partir de la información de un producto: contenido promocional mediante un modelo **texto → texto** y un prompt optimizado para generar una pieza visual mediante un modelo **texto → imagen**.

## 1. Introducción

### Nombre del proyecto
**Fast Prompting aplicado a la automatización de contenido para e-commerce**

### Presentación del problema

Muchos pequeños emprendimientos y tiendas online utilizan redes sociales como uno de sus principales canales de promoción y comunicación. Sin embargo, producir contenido atractivo de manera constante requiere tiempo, conocimientos de marketing digital y recursos que un pequeño negocio puede no tener disponibles.

Como consecuencia, las publicaciones pueden ser irregulares, poco consistentes o no estar correctamente adaptadas al público objetivo, reduciendo las posibilidades de alcance, interacción y conversión.

### Propuesta de solución

La POC recibe información estructurada de un producto:

- nombre;
- características;
- público objetivo;
- canal;
- tono;
- objetivo de comunicación.

A partir de estos datos se desarrollan dos etapas:

1. **Texto → texto:** se compara un prompt básico con un Fast Prompt estructurado para generar una publicación comercial con texto promocional, CTA y hashtags.
2. **Texto → imagen:** se construye un Fast Prompt visual para generar una pieza publicitaria coherente con el mismo producto, público y canal.

El Fast Prompt organiza las instrucciones mediante **rol, contexto, tarea, restricciones y formato de salida**, reduciendo ambigüedad y aumentando el control sobre los resultados.

### Viabilidad

La POC es técnicamente viable porque utiliza Python, Jupyter Notebook y una integración sencilla con la API de OpenAI para la generación de texto. No requiere entrenamiento de modelos ni infraestructura especializada.

La API key se configura mediante la variable de entorno `OPENAI_API_KEY`, evitando incluir credenciales en el repositorio.

Para la generación de imagen se utiliza una herramienta externa gratuita, como NightCafe u otra alternativa compatible con prompts de texto. De esta manera, la etapa texto → imagen puede demostrarse sin depender de una API paga.

## 2. Objetivos

### Objetivo general

Desarrollar una POC que demuestre cómo Fast Prompting puede mejorar y facilitar la generación de contenido promocional textual y visual para pequeños e-commerce.

### Objetivos específicos

- Diseñar prompts reutilizables para contenido comercial.
- Comparar un prompt simple con uno estructurado.
- Generar una publicación adaptada al público, canal, tono y objetivo.
- Diseñar un prompt optimizado para generación de imágenes.
- Analizar claridad, consistencia y cumplimiento de requisitos.
- Reducir consultas innecesarias a la API.
- Crear una solución adaptable a diferentes productos.
- Evaluar los resultados obtenidos mediante Fast Prompting.

## 3. Metodología

El proyecto se desarrolla en siete etapas:

1. **Definición del problema:** se identifica la necesidad de producir contenido comercial consistente.
2. **Ingreso de variables:** se recopilan los datos relevantes del producto.
3. **Diseño del prompt básico:** se genera una instrucción inicial con poco contexto.
4. **Diseño del Fast Prompt:** se incorporan rol, contexto, tarea, restricciones y formato.
5. **Experimentación:** se comparan ambos prompts sobre el mismo producto.
6. **Generación visual:** se crea un Fast Prompt específico para un modelo texto → imagen.
7. **Evaluación:** se analiza el cumplimiento de los criterios establecidos.

La comparación de prompts forma parte del experimento académico. En un flujo productivo se utiliza únicamente el prompt optimizado.

## 4. Herramientas y tecnologías

- **Python:** lógica de la POC.
- **Jupyter Notebook:** entorno reproducible para combinar código, texto y resultados.
- **OpenAI API:** generación de contenido texto → texto.
- **gpt-4o:** modelo utilizado para la generación textual.
- **Variables de entorno:** protección de la API key.
- **NightCafe o herramienta equivalente:** generación texto → imagen sin necesidad de integrar una API paga.
- **GitHub:** repositorio público de la entrega.

### Técnicas de Fast Prompting

**Role prompting:** se asigna al modelo un rol específico según la tarea.

**Context prompting:** se proporcionan producto, audiencia, canal, tono y objetivo.

**Prompt estructurado:** se separan claramente rol, contexto, tarea, restricciones y formato.

**Constraints:** se establecen límites explícitos para evitar información inventada o respuestas fuera del objetivo.

**Output formatting:** se define la estructura de la respuesta para aumentar la consistencia.

**Prompt templates:** las variables se mantienen separadas de las instrucciones, permitiendo reutilizar el mismo sistema con distintos productos.

## 5. Implementación

La implementación completa se encuentra en:

`Fast_Prompting_Ecommerce_ENTREGA_FINAL.ipynb`

La notebook permite:

- configurar los datos de un producto;
- construir un prompt básico;
- construir un Fast Prompt texto → texto;
- comparar ambos enfoques;
- ejecutar opcionalmente el modelo mediante API;
- registrar métricas básicas de uso;
- construir un Fast Prompt texto → imagen;
- reutilizar la solución con otros productos;
- visualizar la imagen final cuando se encuentra en el repositorio.

## 6. Implementación texto → imagen

La POC utiliza los mismos datos del producto para construir una instrucción destinada a un generador de imágenes.

El prompt visual define:

- producto y características;
- público objetivo;
- canal;
- rol de director creativo;
- estilo visual;
- composición;
- restricciones;
- formato 1:1 para Instagram.

El prompt generado en la notebook se copia en NightCafe o en una herramienta gratuita equivalente. La imagen obtenida se guarda en el repositorio como:

`zapatillas_urban_street.png`

De esta manera se documentan tanto el **prompt utilizado** como su **resultado visual**.

## 7. Resultados

La comparación entre el prompt básico y el Fast Prompt muestra que la versión estructurada ofrece mayor control sobre aspectos como público objetivo, tono, CTA, cantidad de hashtags y formato de salida.

El modelo texto → imagen complementa la solución permitiendo generar una propuesta visual a partir de la misma ficha de producto. De esta forma, texto e imagen mantienen un objetivo comercial común.

La POC demuestra que la estructura del prompt permite transformar datos simples de producto en instrucciones reutilizables para diferentes modalidades de IA generativa.

## 8. Optimización de costos

La estrategia distingue diferentes escenarios:

- **Construcción y visualización de prompts:** 0 consultas.
- **Experimento académico texto → texto:** 2 consultas.
- **Uso productivo texto → texto:** 1 consulta por contenido generado.
- **Texto → imagen con herramienta gratuita:** sin llamada a la API de OpenAI.
- **Cambio de producto:** no requiere consulta hasta ejecutar la generación.

El costo monetario no se fija en el repositorio porque depende del modelo y de las tarifas vigentes.

## 9. Mejoras respecto de las entregas anteriores

Las principales mejoras incorporadas son:

- configuración portable de la API key mediante variable de entorno;
- utilización de `gpt-4o` en la llamada implementada;
- prompts parametrizados y reutilizables;
- comparación controlada entre prompt básico y Fast Prompt;
- restricciones y formato de salida explícitos;
- incorporación del modelo texto → imagen;
- análisis de resultados;
- análisis de eficiencia y número de consultas;
- estructura de la notebook adaptada a los requisitos de la entrega final.

## 10. Conclusiones

La POC demuestra que el valor del Prompt Engineering no depende únicamente de formular instrucciones más extensas, sino de proporcionar al modelo información relevante de forma clara, estructurada y reutilizable.

Fast Prompting permite transformar una solicitud genérica en un proceso más controlado. En el caso de un pequeño e-commerce, esto puede facilitar la creación de contenido y mejorar su consistencia sin necesidad de entrenar un modelo propio.

La incorporación de los modelos **texto → texto** y **texto → imagen** demuestra además que una misma ficha de producto puede utilizarse para producir recursos promocionales complementarios y orientados al mismo público y canal.

Los objetivos planteados se consideran alcanzados mediante una POC reproducible en Jupyter Notebook y adaptable a diferentes productos.

## 11. Ejecución

1. Instalar dependencias:

```bash
pip install -r requirements.txt
```

2. Configurar la variable de entorno `OPENAI_API_KEY`.
3. Abrir `Fast_Prompting_Ecommerce_ENTREGA_FINAL.ipynb`.
4. Ejecutar las celdas en orden.
5. Mantener `usar_api = False` si solo se desea recorrer la POC sin consumir API.
6. Cambiar `usar_api = True` únicamente cuando se quiera realizar una consulta real.
7. Para texto → imagen, copiar el prompt generado en la herramienta seleccionada.
8. Guardar la imagen resultante como `zapatillas_urban_street.png` en el mismo repositorio.

> **Importante:** nunca subir una API key al repositorio.

## 12. Archivos del repositorio

La versión final del repositorio debe contener:

- `README.md`
- `Fast_Prompting_Ecommerce_ENTREGA_FINAL.ipynb`
- `requirements.txt`
- `zapatillas_urban_street.png`

## 13. Referencias

- Documentación oficial de OpenAI.
- NightCafe o herramienta de generación de imágenes seleccionada.
- Material teórico de la Diplomatura en Data Science – Prompt Engineering.
