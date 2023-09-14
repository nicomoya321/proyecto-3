# Machine Learning Operations (MLOps)
Este proyecto es un sistema de recomendación de juegos basado en la similitud de los mismos. Toma la información de un juego para identifica juegos similares, además, tiene funciones para los endpoints que se consumirán en la API. El proyecto posee un notebook con el ETL, EDA y la creación de las funciones para los endpoints que usaran las apis, tambien pose un main.py con la información de las apis y una carpeta data con los parquet y csv del proyecto.

 # Preprocesamiento de Datos
Los datos provienen de PI MLOps - STEAM - Google Drive, son 3 dataset, uno con información de las reviews, otro de items y otros con los datos de los juegos de steam.

Para la limpieza de datos se desanidaron varias columnas con diccionarios, se eliminaron las columnas innecesarios, se pusieron formatos de fecha correctos, se cambiaron los tipos de datos en algunas columnas y en el df_reviews se elimino la columna reviews y se creo una nueva con un análisis de sentimiento para ver si las reseñas eran negativas positivas y neutrales. Los dataset modificados son los siguientes. Proyecto_Individual/Data at main · AlejandroManrrique/Proyecto_Individual (github.com)

# Recomendación de juegos
El sistema se basa en una similitud del coseno para calcular la similitud de los juegos mediante los generos y etiquetas.

Esta API proporciona recomendaciones de juegos en la plataforma Steam basadas en el comportamiento de los usuarios y los datos de los juegos disponibles en Steam.

# Funcion

# Entrada del Usuario: 
El usuario proporciona el ID de un juego como parámetro en la URL al hacer una solicitud GET a /recomendacion_juego/{product_id}.

Obtención de Datos del Juego de Referencia: La API obtiene los datos del juego de referencia con el ID proporcionado por el usuario desde un archivo CSV que contiene información sobre los juegos de Steam.

Procesamiento de Texto: La API combina las etiquetas (tags) y géneros del juego de referencia en una sola cadena de texto y crea un vectorizador TF-IDF.

Cálculo de Similitud: La API divide la carga de trabajo en lotes de juegos del archivo CSV y calcula la similitud de coseno entre el juego de referencia y cada juego en el lote utilizando el vectorizador TF-IDF.

Recomendación de Juegos: La API identifica algún juego similar para recomendar.

Función userdata
Además de la función principal de recomendación de películas, el proyecto también incluye una función que dado un id de usuario:

Devuelve la cantidad de dinero gastado.

El porcentaje de juegos recomendados.

La cantidad de items.
