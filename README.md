## TFM Enrique Ribera Carbonell para el MPVD

El Máster de Periodismo y Visualización de Datos de la Universidad de Alcalá de Henares trata de enseñar las técnicas más innovadoras para el desarrollo del periodismo, siempre a través de herramientas de código libre.

Para la finalización de este, se presenta un trabajo que recoge lo aprendido en algunos de estos módulos, como el tratamiento de datos con Python o el web scraping. 

El trabajo es un recopilatorio de crónicas automatizadas de fútbol regional (2ª Regional Juvenil, liga 13) subidas en una página Jekyll con el tema [Minima](https://github.com/jekyll/minima).

### Inspiración

La falta de información sobre el deporte local, sumada a la gran participación de prácticas deportivas locales y regionales, han sido la inspiración para crear un boceto de crónicas con la información ofrecida por la federación encargada de organizar estas competiciones.

Otra inspiración han sido las crónicas de ligas semi-profesionales del fútbol español publicadas por el medio de comunicación Sport, con el trabajo de la empresa Narrativa que ofrece información en un medio de gran impacto a eventos deportivos que no lo tendrían a este nivel sin la ayuda de la Inteligencia Artificial.

### Proceso del trabajo

#### Creación de las crónicas
Para empezar, se analizó la página web con la información de un partido de la competición para detectar la organización de esta y poder elegir la mejor forma de obtener los datos. 

Después de este análisis, se decidió usar las librerías de Python BeautifulSoup y Request y se epezó el Web Scraping extrayendo los datos de las columnas con la información de los jugadores y cuerpos técnicos de ambos equipos y después parsearlos para conseguir todos los datos de cada jugador como los goles, entradas al campo...

Al tener los datos de los jugadores, se realiza una función que contiene todas las variables sobre los eventos del partido a través de operaciones con los datos de los jugadores parseados anteriormente y más datos de la web que no estaban en las columnas de los jugadores, como el número de la jornada, el día o el nombre del campo en el que se juega. Todas estas variables se almacenan en un diccionario que se utiliza para añadir las variables en los bloques de texto.

En el apartado de la redacción de los textos se ha dividido el texto en cinco bloques. 

1. El primero es para darle formato de post para el tema de página elegido. 
2. El segundo son las entradillas que contienen, en un párrafo, la información sobre los equipos, estadio y jornada y en otro párrafo, los titulares de cada equipo y su entrenador.
3. El tercero trata sobre lo ocurrido en la primera parte en el que el primer párrafo muestra el resultado y en el segundo la información sobre los goles (si los hay).
4. La explicación de la segunda parte ocupa el cuarto bloque y tiene el mismo orden que la información de la primera parte.
5. El último bloque es la ficha técnica del partido que recoge de forma simplificada los jugadores titulares, los suplentes y entrenadores de cada equipo.

Estos bloques cuentan con frases cortas que se van eligiendo de manera aleatoria y así dar más sensación de naturalidad y tener más diferencias entre crónicas.

El siguiente paso ha sido la extracción de todas las url de los partidos de la competición para poder pasarlo por el diccionario creado anteriormente y que recorra todos los partidos.

Para finalizar el trabajo en Python se guardan los archivos de texto en formato de Markdown ya que para subirlos a la página se necesita ese formato y se le da un nombre que comienza con una fecha en formato $Y-$m-$d por el mismo motivo.

#### Publicación de las crónicas

Como se ha dicho antes, las crónicas se publican en una página de Github con el tema Minima en el que la página principal contiene el índice con todos los partidos ordenados en orden, mostrando primero los partidos más recientes.

Se barajó la posibilidad de concatenar crónicas por jornadas, pero al final se ha desechado esa opción para darle una página individual a cada partido.


### Posibles mejoras

Las posibles mejoras para este proyecto pueden ser:

- Optimización de los comentarios.
- Añadir más variables para hacer más informativas las crónicas.
- Limpieza de código en algunas variables

### Fallos del código

Se ha detectado un fallo que produce que los datos de los jugadores parseados no recorran todas las url de los partidos.