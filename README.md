Esto es un pequeño proyecto en el que se hace una búsqueda vectorial y luego se pasa el resultado de la consulta como contexto en el prompt de un modelo de lenguaje.

Primero se abre una conexión con MongoDB, luego se generan embeddings utilizando el modelo (en estee caso hemos usado TinyLlama cuantificado 2Q) sobre una historia de unos 500 caracteres aproximadamente. Estos embeddings se guardan en mongodb y haciendo una búsqueda vectorial buscamos aquellos que estén más cercanos al vector generado para la consulta. Una vez hecha la consulta, obtenemos los párrafos relacionados con la consulta y estos párrafos los metemos en el prompt que enviaremos a un modelo más potente. Así pues, le pasamos al segundo modelo la pregunta inicial junto con los párrafos obtenidos de la primera consulta y obtenemos la respuesta final. 