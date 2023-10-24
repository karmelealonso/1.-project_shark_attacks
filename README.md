# 1.-project_shark_attacks

<img width="952" alt="imagen sharck_attack" src="https://github.com/karmelealonso/1.-project_shark_attacks/assets/144480807/236df0f7-ae5b-4781-8252-bcf1e548d5e1">






**a)	ENFOQUE DEL PROBLEMA:**

Mi enfoque principal al llevar a cabo este proyecto no se ha centrado en la obtención de resultados específicos para el análisis de un conjunto particular de variables. Más bien, mi objetivo primordial ha sido el de realizar una limpieza, columna a columna, de los datos proporcionados (en un intento de que fuera integral y exhaustiva). 
La fase de limpieza de datos ha sido el núcleo central o eje vertebrador del trabajo, pues mi intención, más allá de la obtención de resultados específicos, ha sido la de "preparar" los datos de manera que sean aptos para su uso en diversos estudios, independientemente de los objetivos que se quieran alcanzar. Es decir, para analizar las relaciones o discrepancias entre todas las variables disponibles (aunque, por supuesto, algunos datos como el nombre de la fuente u otros de naturaleza similar no me han parecido tan relevantes como otros).

**b)	DESARROLLO DEL MISMO:**

1.	Exploración inicial.

2.	Anulación de elementos duplicados: En la etapa inicial de la limpieza de datos, se identificaron elementos duplicados durante una exploración preliminar. Dado que los duplicados no añaden valor al análisis, se optó por eliminarlos.

3.	Exploración y anulación de valores nulos:
-	Se eliminaron las filas con más del 95% de valores nulos, ya que no aportaban información relevante.
-	Se eliminaron temporalmente las columnas "Unnamed: 22" y "Unnamed: 23" debido a la alta presencia de valores nulos en las mismas.
-	"Case Number": Se completaron manualmente los dos valores nulos que contenía usando información de la columna inmediatamente anterior.
-	"Type": Se completaron los valores nulos con la etiqueta "Unknown" ya que la información disponible no permitía determinarlos.
-	"Country": Se descartaron filas en las que no se encontraron valores en las columnas "Country," "Area" o "Location." Luego, se investigó y completaron los valores nulos en la columna "Country", uno a uno.
-	"Area": Se completaron los valores nulos con la etiqueta "Area situada en {nombre del país al que pertenece (obtenido de la columna "Country")}".
-	"Activity": Se completaron los valores nulos con la etiqueta "Unknown".
-	"Name" y "Sex": Se eliminaron las filas sin valores tanto en la columna "Name" como en "Sex". Los valores de nombre desconocidos se reemplazaron con "Unknown." En cuanto a "Sex," se eliminaron las filas con valores que no coincidían con "M" o "F".
-	"Age": Se llenaron temporalmente los valores nulos con ceros para operar con la columna. Se creó una nueva columna "Age2" llena de ceros y se sustituyeron los valores que cumplían la condición de "Age" en "Age2." Luego, se convirtió la columna a tipo float y se completaron los valores previamente asignados como cero con la media de las edades conocidas.
-	"Injury": Se eliminaron filas con valores nulos, ya que no tenían un impacto significativo en las estadísticas finales.
-	"Fatal (T/N)": Se completaron las filas en la columna "Fatal (Y/N)" con "Y" cuando la palabra "FATAL" estaba en la columna "Injury" y con "N" en el resto de los casos.
-	"Time": Se eliminó la columna en su conjunto debido al alto porcentaje de valores nulos, ya que la información carecía de relevancia en el análisis.
-	"Species": Se completaron los valores nulos con "Shark".
-	"Investigator or Source": Se eliminaron los valores nulos.
-	"href formula": Se escribió el valor nulo con el valor de la misma fila en "href".
-	"Case Number. 1" y "Case Number. 2": Se identificaron las filas con valores nulos en ambas columnas y se eliminaron directamente. Al ser solo siete valores, no afectarían significativamente el estudio estadístico posterior.

4.	Comparativa de los gráficos de valores nulos al comienzo del proyecto y una vez retirados estos del Dataframe.

5.	Limpieza y depuración de los datos existentes:
-	"Case Number": Los caracteres adicionales ("a," "b," "c," "d," y "R") que a veces acompañaban a los valores de esta columna se eliminaron. Estos caracteres proporcionan información sobre múltiples incidentes en el mismo día o si el caso había sido reportado, sin embargo, esta información ya estaba registrada en otras columnas.
-	"Year": Se identificaron valores poco verosímiles, como años extremadamente inusuales (e.g., 500, 77, 5, 0), que se eliminaron para mantener la integridad de los datos.
-	"Type": Se unificaron valores similares, como "Boat" y "Boatomg," en "Boating" para simplificar la columna. Los demás valores se mantuvieron intactos.
-	"Country": Debido a la falta de uniformidad en los datos, se abordaron los errores de forma individual: algunos se eliminaron. Además, la columna se renombró como "Country, ocean or sea" para reflejar la diversidad de los datos.
-	"Activity": Se implementó un enfoque genérico mediante una función y condicionales específicos con el fin de unificar las actividades de manera más coherente.
-	"Name" y "Fatal (Y/N)": Se examinaron los valores únicos restantes y se mofificaron de forma manual. 
-	"Species": Se eliminaron las casillas en las que no estaba clara la presencia del tiburón en el daño y al resto se les atribuyó el valor de "Sharck Involved".

**c)	BREVE ANÁLISIS DE LOS DATOS OBTENIDOS (ESTO LO DEJO PARA ESTUDIOS POSTERIORES).**

**d)ALGUNAS CONCLUSIONES PERTINENTES.**

En esta fase del proyecto, se crearon dos nuevas columnas con el fin de representar rangos de años y edades con el propósito de facilitar la visualización de datos a través de histogramas. Esto nos permite identificar tendencias y patrones más claramente.
Por ejemplo, con la observación de los histogramas, pudimos destacar la existencia de un período de años en los que se han producido más accidentes. Asimismo, mediante el análisis del rango de edades en los que se registran la mayoría de los incidentes, pudimos obtener información relevante sobre los grupos de edad más afectados por los ataques de tiburones, lo cual nos permite identificar posibles tendencias futuras. Además, al considerar el género, notamos que los ataques son más frecuentes en individuos de sexo masculino.

Este proyecto me ha hecho consciente de la importancia que desempeña la limpieza de un dataframe en la preparación de datos para estudios estadísticos futuros, pues es realmente lo que garantiza la calidad de los mismos, lo que a su vez tiene un impacto inmediato en la validez de los resultados y es lo que, en última instancia, hace que de algún modo u otro podamos estar más o menos seguros y confiar en los resultados de investigaciones estadísticas.
