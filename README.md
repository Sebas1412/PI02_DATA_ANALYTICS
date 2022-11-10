![HenryLogo](https://d31uz8lwfmyn8g.cloudfront.net/Assets/logo-henry-white-lg.png)

# **PROYECTO INDIVIDUAL Nº3**

# <h1 align="center">**`Accidentes aéreos`**</h1>

<p align="center">
<img src="https://slack-imgs.com/?c=1&o1=ro&url=https%3A%2F%2Fcdn.pixabay.com%2Fphoto%2F2016%2F09%2F15%2F16%2F13%2Fairplane-1671967_1280.jpg"  height=300>
</p>



## **Contexto**
La **Organización de Aviación Civil Internacional (OACI)**, organismo de la Organización de las Naciones Unidas, quiere investigar en profundidad los accidentes producidos desde inicios del siglo XX. Para ello, nos solicita la elaboración de un informe y un dashboard interactivo que recopile tal información. 

La OACI únicamente cuenta con un dataset sobre datos de accidentes de aviones, pero nos insta a cruzar esta información con otras fuentes de su interés. Esto con el objetivo de obtener mayor claridad y consistencia en los fundamentos del estudio.

## **Propuesta de trabajo**
Serie de tareas a cumplir: 

+ Realizar un EDA con el dataset provisto, junto con un reporte de calidad y diccionario de datos
+ Buscar y relacionar información relevante con los eventos
+ Crear una base de datos en un motor SQL e ingestar el csv procesado
+ Elaborar un dashboard e idear un storytelling con el objetivo de presentarlo ante la OACI
+ Adjuntar todo el trabajo en un repositorio de GitHub

- - -

## ***Trabajo realizado***

- En primer lugar lo que se hizo fue abrir el csv otorgado con la librería Pandas de python y convertir el datasets en dataframe.
- Se modificaron los nombres de la columnas para que sea más intuitivo y fácil de usar el dataframe.
- Se pasaron los valores que contenían '?' a nulos ya que de esta forma se ve de una forma más rápida la cantidad de valores faltantes que hay.
- Se decidio dejar la mayoría de valores faltantes y no borrarlos ya que al ser un tema delicado, imputarlos con alguna medida de tendencia central o otra técnica, podría llevar a poner datos equivocados y de lo que se está hablando es de vidad de personas. Además como el producto final se hace en Power Bi, este tiene la capacidad de obviar los valores nulos, por lo que no sería una complicación a futuro.
- Los datos que no contenían información sobre víctimas sí se decidió borrar esas filas ya que no iban a aportar información útil en el informe
- Se le dió el formato deseaedo a cada columna.
- Se realizó un pequeño ajuste en las filas relacionadas al 9 de septiembre del 2001, en la parte de civiles fallecidos, ya que el dato estaba repetido en las 2 filas, y duplicaba el valor de muertos, por lo que se decidió, dividir el valor a la mitad.
- Se creó la base de datos en MySQL
- A través de la librería SQLalchemy se ingestó la base de datos en MySQL.
- Se siguió buscando información y se logró encontrar 2 datasets, uno con más casos de accidentes aéreos y el otro es un filtrado de este mismo por la causa del accidente es debido a fallas humanas.
- Se eligió las columnas que se iban a utilizar y se normalizó el nombre de estas a los mismos que tiene el datasets original.
- Se crearon las tablas pertinentes en MySQL para la ingesta de los nuevos datasets.
- Se pudo conectar sin problemas PowerBi con MySQL
- Se crearon métricas generales con el dataset provisto por OACI en primera parte.
- Se comparó que los nuevos datasets tuvieran coherencia el dataset anteriormente nombrado.
- Se analizaron métricas específicas sobre los accidentes aéreos por fallas humanas.
- Se subio a PowerBi Server el dashboard realizado.

## **Reporte**

Dado el tema que, se indagó en el datasets y se vió que se registran accidentes desde 1908 hasta la actualidad, el último registro que hemos encontrado ha sido del 6 de noviembre de 2022, es decir hace menos de una semana atrás.

La BAAA tiene contabilizado más de 30000 accidentes aéreos alcanzando una suma de alrededor de las 160000 muertes fatales, solo contando las muertes de personas a bordo. Si le sumamos aquellas que perecieron por la colsión del avión contra el terreno, la cifra ronda los 170000 casos.

Se analizo  que la década de los 70 tiene varios años con cifras altas de muertes totales, se buscó información de por qué podría pasar esto y para nuestra sorpresa, en ese lapso, se empezó a utilizar el GPS en los aviones, lo que hizo que disminuyeran las colisiones entre 2 aviones en el cielo, por lo que se da entender que este aumento viene por otro lado. No se obtuvo el tiempo suficiente para ahondar en detalle, pero es una tarea que compartiremos en futuras actualizaciones.

El 13 de octubre 1972 se produjo en la cordillera una tragedia que por su historia dramática se llevo a los cines y libros, bautidazada como la "Tragedia de los Andes", en la cual los sobrevivientes para no perder la vida, comían fetas de carnes de sus compañeros fallecidos. La causa por vuelo controlado contra el terreno debido a un error del piloto.

En esta década tambien se dió el peor Accidente aéreo que se tiene conocimiento hasta ahora. Fue en 1977, en el aeropuerto el Rodeo, en Tenerife debido a la colisión de dos aviones Boeing 747. Se cree que fue por una mala comunicación entre la torre de control y los pilotos. Ocurrio en la pista de despegue, cuando los dos aviones estaban por dirigirse a los cielos, chocaron entre ellos, dejando una cantidad de 583 víctimas fatales.

En 1985 se produjo el mayor accidente aéreo teniendo en cuenta un solo avión. Ocurrió en Japón, y deja la cifra de 520 personas muertas. El error humano se hace presente nuevamente pero no por culpa del piloto, sino por culpa de los mecánicos que no dejaron el avión en condiciones.

Teniendo en cuenta victimas fatales por la colisión del avión contra el terreno, se debe hablar del 11 de septiembre del 2001, un ataque terrorista hace colisionar 2 aviones contras las torres de Gemela, en Nueva York, Estados Unidos, dejando alrededor de 3000 muertes.

Un dato alentador es que se puede apreciar que hay una tendencia en baja desde 1996 de muertes por año y esto se debe en gran parte a las nuevas tecnologías que han ido incorporando los aviones, como es la incoporación de sistemas electrónicos, advertencias de cercanía con el terreno y tecnología "Fly By Wire", disminuyendo el riesgo de accidentes.

Con la primer tanda de primera generación, ocurrían 3 accidentes fatales por millón de vuelos, esa cifra se ha visto reducida a tan solo 0,1 accidentes por millón de vuelo con los aviones que se tienen hoy en día.

Según los datos de la BAAA se tiene que más del 33% de los accidentes son debido al factor humano, más del 50% de las vidas perdidas son por culpa del hombre. Algunos investigadores han llegado a la conclusión que del 70 al 90% de los accidentes aéreos son por culpa de las personas. Comparando con los registros que se tiene por incidencia del tiempo, se obtienen que es práctimente 7 veces más la incidencia del hombre que de la naturaleza. Es una cifra considerable.

Si se compara las fallas humanas contra las fallas técnicas desde 1996, las primeras duplican a las segundas en totalidad accidentes.

Por lo que haciendo un análisis rápido, se puede llegar a la conclusión es que para reducir en gran parte los accidentes aéreos se debe trabajar sobre el hombre, si bien la tecnología puede ayudar a disminuir los accidentes y se debe seguir invirtiendo en ella, el factor humano es donde se debe hacer incapié. De parte de los pilotos, tienen que tener la habilidad de adaptarse rápidamente a las nuevas tecnologías para sacarle todo su provecho, si han llegado a ser pilotos, es porque están capacitados, solo que tienen que ir modernizándose. También se tiene que trabajar y no dejar de lado la salud de toda la tripulación, y cuando se habla de salud se hace referencia tanto física como mentalmente. Un piloto debe tener la responsabilidad de estar en sus plenas capacidades cuando pilotean. Habría que analizar si duermen las horas recomendadas por OMS o si pasa como con los viajes de media y larga distancia de autobuses. En relación a los operarios de las torres de control, hay que tener en cuenta que deben pasar directivas claras y precisas. Por parte de los mécanicos, ver y reveer su trabajo, es indispensable que el avión esté en perfectas condiciones. Y por último, no dejar estos problemas como un asunto privado, sino que los Estados deben invertir en políticas que ayuden a reducir los accidentes aéreos ya que la aviación es un foco de desarrollo para ellos.

## **Diccionario**

- fecha : fecha del accidente
- horaAccidente : hora declarada en la que se produjo el accidente
- lugarAccidente : Localizacción donde tuvo lugar el accidente
- compania :Es la compañia aérea a la cual pertenece el avión y/o operador del vuelo que son responsables de asegurarse de que los vuelos despegan a tiempo y del cumplimiento de todos los reglamentos de salud y seguridad. 
- numeroVuelo : número de vuelo
- destino : destino del vuelo
- modeloAvion: tipo de aeronave
- matriculaAvion : matrícula del avión, es como la patante de un automóvil
- numeroSErie : Número de serie de la aeronave
- TotalPersonas : suma de pasajeros y tripulantes a bordo
- pasajeros: pasajeros a bordo
- tripulacion: tripulantes a bordo
- fallecidosTotales: suma de tripulantes y pasajeros fallecidos
- pasajerosFatales : cantidad de pasajeros fallecidos
- tripulacionFatal : cantidad de tripulantes fallecidos
- civilesFatales : cantidad de víctimas que no se encontraban a bordo del avión
- descripcion : breve resumen del accidente
- BAAA : Bureau of Aircraft Accidents Archives
- GPS : sistema de posicionamiento global
- vuelo controlado contra el terreno : tipo de colisión en el cual una aeronave, bajo total control del piloto, vuela de manera inadvertida contra el terreno o contra un obstáculo
- sistema que reemplaza los controles de vuelo manuales convencionales de un aeronave con una interfaz electrónica
- Generación de aviones : Primera generación (mediados de los 1940 - mediados de los 1950) / Segunda generación (mediados de los 1950 - principios de los 1960) / Tercera generación (mediados de los 1960 - principios de los 1970) / Cuarta generación (1970 - actualidad) / Quinta generación (1990 - actualidad)



## **Bibliografía**

- https://www.baaa-acro.com/crash-archives/
- https://es.wikipedia.org/wiki/Fly-by-wire
- https://es.wikipedia.org/wiki/Vuelo_controlado_contra_el_terreno
- https://elpais.com/diario/2001/10/26/internacional/1004047212_850215.html
- https://es.wikipedia.org/wiki/Vuelo_123_de_Japan_Airlines
- https://es.wikipedia.org/wiki/Accidente_del_avi%C3%B3n_571_de_la_Fuerza_A%C3%A9rea_Uruguaya
- http://i3campus.co/CONTENIDOS/wikipedia/content/a/dc-3.html
- https://www.infobae.com/historias/2022/03/27/a-45-anos-de-la-mayor-tragedia-aerea-de-la-historia-el-choque-de-dos-jumbos-cuerpos-en-llamas-y-olor-a-muerte/
- https://a21.com.mx/aeronautica/2021/05/03/reducen-las-2-principales-causas-de-accidentes-aereos
- https://www.redalyc.org/pdf/801/80113673011.pdf


