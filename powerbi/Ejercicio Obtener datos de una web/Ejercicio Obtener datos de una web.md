**Ejercicio Obtener datos de una web**

**Datos Web**

Ejemplo de como obtener datos de una web para generar un report en Power BI.

Web de muestra:

<https://guide.michelin.com/es/es/restaurantes/3-estrellas-michelin>

Seleccionar como Origen de datos: Web

![](Recursos/Aspose.Words.877fdbe4-18f1-4863-bdfb-a6c2e49d2d4c.001.png)

Nos solicita confirmación de los datos.

![](Recursos/Aspose.Words.877fdbe4-18f1-4863-bdfb-a6c2e49d2d4c.002.png)

En la previsualización podemos ver el contenido de la tabla:

![](Recursos/Aspose.Words.877fdbe4-18f1-4863-bdfb-a6c2e49d2d4c.003.png)

Seleccionamos **Transformar** para acceder al Power Query Editor


**Transformar datos**

Una vez en el Power Query Editor

1 - Cambiar el nombre a la tabla: Restaurantes

![](Recursos/paso1.png)

2 - Dividir la columna ciudad,pais en dos columnas.  Para ello usaremos la instrucción de transformación **Dividir columna**


![](Recursos/dividircolumna.png)

3 - Duplicar la columna del precio y tipo de comida (columna3).  Para ello seleccionamos la columna y con el botón derecho, seleccionamos **"Duplicar columna"**


![](Recursos/duplicarColumna.png)

4 - En la primera columna creada, extraemos los 4 primeros caracteres, mediante la instrucción **Extraer** y la opción **"Primeros caracteres"**

![](Recursos/extraer.png)

Le indicamos el número de caracteres a extraer:

![](Recursos/Aspose.Words.877fdbe4-18f1-4863-bdfb-a6c2e49d2d4c.005.png)

5 - Usamos la misma función, para extraer los últimos caracteres, pero con la opción **"Últimos caracteres"**

6 - En la última columna observamos que tenemos "Reservar una mesa" o null.  Sustituimos el valor "null" por "Sin reserva"

![](Recursos/paso2.png)





![](Recursos/Aspose.Words.877fdbe4-18f1-4863-bdfb-a6c2e49d2d4c.006.png)

![](Recursos/Aspose.Words.877fdbe4-18f1-4863-bdfb-a6c2e49d2d4c.007.png)

Insertar una tabla con Nombre y país

Insertar un mapa coropletico, añadiendo 

