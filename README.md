<h1 align='center'>
 <b>Proyecto Data Analytics: Telecomunicaciones</b>
</h1>

## Descripción del proyecto

Fuí contratado por una empresa de telecomunicaciones Argentina para realizar un análisis del panorama de las telecomunicaciones, específicamente internet en Argentina a través de datasets del gobierno argentino.

El análisis incluye un EDA realizado en Python, creación de una base de datos SQL con los datasets limpios obtenidos del EDA, la realización de un informe con las conclusiones obtenidas del análisis y un dashboard interactivo para explicar los KPI sugeridos.

## Tecnologías utilizadas

- Se utilizó Python como lenguaje de programación.
- Se utilizaron los módulos pandas, matplotlib y seaborn para el EDA.
- Se utilizó MySQL como motor para crear la base de datos SQL.
- Se utilizó Power BI para realizar el dashboard.

## Estructura del repositorio

El repositorio cuenta con las siguientes carpetas y archivos:

- [Datasets](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/tree/main/Datasets "Datasets"): donde se encuentran todos los datasets proporcionados para realizar el proyecto.
- [Datasets_PBI](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/tree/main/Datasets_PBI "Datasets_PBI"): donde se encuentran los datasets utilizados para generar el dashboard y realizar el EDA.
- [Gráficos](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/tree/main/Graficos "Gráficos"): se encuentran los gráficos más importantes obtenidos al realizar el EDA.
- [Notebooks](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/tree/main/Notebooks): es la carpeta que contiene el notebook donde se realizó el EDA y el notebook donde se realizó la conexión a la base de datos.
- [BD](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/tree/main/BD): donde se encuentra el archivo de la base de datos.
- Dashboard.pbix: es el archivo de Power BI donde se encuentra el dashboard realizado.
- README.md: es el archivo donde está toda la información del proyecto, incluyendo el informe con los KPI propuestos, los insights y conclusiones obtenidos de los datos.

## Informe

<h4 align='center'>
 <b>Introducción</b>
</h4>

<div style="text-align: justify"><p style="text-align: justify;">
A lo largo de la historia, la humanidad ha buscado formas de lograr una comunicación más rápida y efectiva: pasando de dibujar lo que ocurría a su alrededor en paredes de cuevas, a aprender a utilizar símbolos para escribir y, posteriormente, a crear sistemas que utilicen tecnología para enviar información.

La necesidad de comunicar la información de forma más rápida y clara ha llevado a un avance en las tecnologías de forma exponencial, en pocos años los humanos pasamos de usar el telégrafo a utilizar teléfonos móviles, televisión e Internet.

El crecimiento y alcance de la tecnología ha creado una necesidad en las personas de contar con mayores velocidades de conexión, que les permitan comunicarse de la mejor forma posible y acceder a contenido de todo tipo. Esto ha llevado al gran crecimiento del Internet.

El Internet ha significado toda una revolución en el mundo de la información, pues permite conectarse con personas de todo el mundo en tiempo real y con una calidad excelente. Esto ha creado la posibilidad de que existan trabajos remotos, donde el empleado se conecta al Internet para hablar con el empleador; ha ayuda a la creación de todo tipo de trabajos online como los creadores de contenido o youtubers; ha ayudado a que personas de todo el mundo tengan acceso a educación a través de universidades o academias que brindan cursos o dan clases online.

De esta situación no escapa Argentina, en donde se ha visto un crecimiento anual del número de accesos a Internet a nivel nacional y cada vez son más los usuarios que cuentan con Internet de altas velocidades y utilizan la última tecnología del mercado: la fibra óptica, la cual proporciona las velocidades más altas de Internet y permite un acceso constante y seguro, con el mínimo de interrupciones del servicio.

En el proyecto se mostrará el panorama actual de las telecomunicaciones en Argentina, con un enfoque en el Internet: como ha crecido en los últimos años, cuales son las tendencias de los usuarios en velocidad y tecnologías y comparándolo con los otros medios de comunicación (televisión y telefonía), todo esto en función de los datos del gobierno de Argentina proporcionados por la compañía. Se presentaran los insights y conclusiones obtenidos de los datos, así como los KPI más importante que debe considerar la compañía.
</p></div>

<h4 align='center'>
 <b>Desarrollo</b>
</h4>

#### Panorama General

<div style="text-align: justify"><p style="text-align: justify;">
El proyecto fue realizado utilizando los datos suministrados por la compañía. Los datos pertenecen al ENACOM, el cual es el Ente Nacional de Comunicaciones de Argentina. El enfoque principal del análisis fueron los datos pertenecientes a Internet, pero se incluyeron algunos datos de las otras tecnologías de telecomunicación: televisión, telefonía fija y móvil.

El análisis exploratorio de los datos fue realizado utilizando el lenguaje de programación Python, específicamente los módulos requests para obtener la información de la API de ENACOM, Pandas para la creación de los DataFrame y Matplotlib y Seaborn para la creación de los gráficos que permitieron obtener los insights y conclusiones. Para el motor de base de datos se utilizó MySQL, creando la base de datos y las tablas desde Python usando el módulo pymysql.

Antes de comenzar a analizar los datos del ENACOM, se buscó la población de las diferentes provincias de Argentina para ayudar a entender la distribución poblacional y a obtener los diferentes insights y conclusiones. Con los datos de la población se realizó el siguiente gráfico:

![Población](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/assets/113273616/16ee7eac-fc51-4dba-b126-b12322e2a531)

Vemos en el gráfico que las provincias de Buenos Aires, Córdoba y Santa Fé son las más pobladas, mientras que las provincias de Tierra del Fuego, Santa Cruz y La Pampa son las menos pobladas. Este es el comportamiento de esperarse, pues las provincias más pobladas son las más cercanas a los centros urbanos más grandes.

Una vez observada la distribución poblacional se procedió a realizar el análisis de los datasets obtenidos de la API del ENACOM utilizando el módulo requests de Python. Al realizar la conexión a la API, se obtuvo un JSON que contaba con los links a los diferentes datasets. Con estos links se obtuvo acceso a los datasets, los cuales fueron importados en formato .csv utilizando el módulo pandas. Es importante señalar que eran un total de 16 datasets presentes en la API, pero solo se utilizaron los datasets que contribuyen más con los objetivos del análisis y ayudaron a definir las KPI que se presentarán más adelante.

Para poder realizar el análisis correctamente y poder determinar los mejores KPI, primero fue necesario observar el comportamiento general del Internet. Para ello se realizó una comparación de la cantidad de usuarios del Internet de banda angosta y del banda ancha anualmente, desde el primer trimestre del 2014 hasta el tercer trimestre del 2022:

![Comparacion_usuarios_por_banda](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/assets/113273616/0240f55e-b7cf-40ec-b4a4-78a11148a0eb)

En el gráfico se observa la gran diferencia en la cantidad de usuarios: los de banda angosta apenas llegaron, en el 2014, a 150 mil y van disminuyendo a lo largo de los años, mientras que los de banda ancha van aumentando a lo largo de los años con un pico de 4 millones en el 2021. También se observa una disminución en la cantidad de usuarios para banda ancha en el 2022, pero se debe recordar que no están incluidos los datos del cuarto semestre de ese año, por lo que es de esperar que al incluirlos aumenten aún más.

Este gráfico nos muestra la gran tendencia actual de los usuarios: prefieren el Internet de banda ancha sobre el de banda angosta, lo que indica un deseo en tener un Internet con mayores velocidades y mayor estabilidad. Por esto, el enfoque del proyecto será el Internet de Banda ancha, ya que es el que presenta mayor ganancia de usuarios.

Luego, se realizó la comparación entre la cantidad de usuarios con acceso a Internet de banda ancha y la cantidad de hogares conectados a Internet cada 100 hogares para el año 2022, obteniéndose el siguiente gráfico:

![Comparacion_usuarios_provincia_100_hogares](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/assets/113273616/7a1a5261-bdcb-474e-9a9f-012c7a48c69b)

Es importante mencionar que la cantidad de accesos cada 100 hogares se basa en la cantidad total de la población, se considera como un porcentaje de la población que tiene acceso a Internet. Este gráfico comparativo es muy importante porque vemos, por ejemplo, que la provincia de Buenos Aires es la que tiene mayor cantidad de usuarios con acceso a Internet, pero es apenas la quinta provincia en cantidad total de hogares conectados cada 100 hogares. De igual forma, Tierra del Fuego es la antepenúltima provincia con cantidad total de usuarios que tienen acceso a Internet banda ancha, pero es la segunda en accesos cada 100 hogares.

El gráfico de accesos cada 100 hogares es de mucha importancia, pues señala el porcentaje de accesos que hay por provincia, sin tomar en cuenta la población. Como se pudo ver en el gráfico de la distribución poblacional, las provincias argentinas no tienen toda la misma población, este gráfico lo que hace es tomar en cuenta la población individual de cada provincia y representar la cantidad de accesos como porcentaje, esto lo hace de mayor importancia y relevancia pues permite ver que provincias tienen poco o mucho acceso a Internet. Así, provincias como Tierra del Fuego, que tiene la población más pequeña de Argentina, tiene casi un 80% de acceso a internet cada 100 hogares.

Es importante observar aquellas provincias con pocos accesos a Internet cada 100 hogares, para tener una idea de en cuales es posible tener un mayor crecimiento al prestar un mejor servicio, con mejor conexión a Internet y con planes más accesibles a la población, entre éstas se encuentran Formosa, Santiago del Estero, Santa Cruz y San Juan. De igual forma, provincias como Mendoza, la cual tiene la quinta mayor población y menos del 50% de la población tiene acceso a internet.

**- Televisión**

Se realizó un gráfico comparativo de televisión satelital, por suscripción e Internet de banda ancha de forma anual:

![television_vs_internet](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/assets/113273616/b8b47596-284d-4bde-8791-5fca59a701b2)

Se puede ver como a medida que pasan los años, la cantidad de usuarios que utilizan televisión disminuye, mientras que la de Internet aumenta. Además, la diferencia en el total de usuarios de Internet es mayor (40 millones) que la de los servicios de televisión (30 millones) para el año 2021. 

La gran disminución en la cantidad de suscriptores del servicio de televisión tiene relación con la gran cantidad y oferta de plataformas streaming (Netflix, Disney+, HBO MAX, etc.) que hay actualmente. El gran catálogo, la alta calidad de video y la disponibilidad de estas plataformas ha creado una migración de los usuarios de televisión a Internet.

**- Telefonía fija**

Se realizó un gráfico anual de la cantidad de usuarios de telefonía fija para los diferentes uso que se le da (hogares, comercios, gobiernos, otros):

![telefonia_fija](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/assets/113273616/db9332a6-de0e-40b0-b554-7d0ea68bd2ac)

Se observa que el comportamiento es igual al de la televisión, ha medida que pasan los años, la cantidad de usuarios de telefonía fija disminuye constantemente.

Esto guarda relación con las tendencias actuales, donde las personas están migrando al uso de la telefonía móvil por la gran capacidad y variedad de los teléfonos móviles, la posibilidad de conectarlos a Internet, poder llevarlos a todos lados, entre otras características. Considerando esto, la empresa puede ofertar planes que incluyan onus o modems que tengan wifi o, incluso, rentar routers para que los usuarios tengan acceso a la red wifi y utilicen el Internet de la empresa.

**- Telefonía móvil**

Al igual que en los casos anteriores, se realizó un gráfico que muestra la cantidad de usuarios de forma anual para los clientes de telefonía móvil prepago y postpago:

![telefonia_movil](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/assets/113273616/00886bf8-eefd-49c8-bf5a-307dcd0d70f3)

En este caso, a diferencia de la televisión y telefonía fija, la cantidad total de usuarios se ha mantenido prácticamente constante a lo largo de los años. Esto se debe a lo que ya se mencionó, los teléfonos móviles tienen grandes características que los hacen interesantes para los usuarios, además de que les permiten matenerse conectados e informados en cualquier lugar en cualquier momento.

Con todo lo antes expuesto, la compañía puede considerar aplicar el siguiente KPI:

1- **Cantidad de usuarios ganados por provincia:** este KPI permitirá medir la eficacia de la empresa en captar nuevos usuarios en las provincias con menor acceso a un buen servicio de Internet. De acuerdo a los datos y las gráficas mostradas, se puede definir el KPI:

"Aumentar la cantidad de usuarios con acceso a un buen servicio de Internet en 5%, de forma anual, enfocándose especialmente en las provincias que tengan menor cantidad de accesos."

El KPI se medirá sumando los usuarios nuevos que se ganen en cada una de las provincias en un año. Se toma el 5 % de forma anual, porque es lo que aumentan, en promedio, la cantidad de usuarios que utilizan Internet de banda ancha en un año a nivel nacional.
</p></div>

#### Velocidades y Tecnologías

<div style="text-align: justify"><p style="text-align: justify;">
Una vez analizado el panorama general nacional y provincial de las conexiones a Internet en Argentina, veamos como se comporta el total de usuarios con acceso a Internet en función de diferentes rangos de velocidades de conexión. Para ello se utilizó un gráfico de líneas con progreso anual a nivel nacional:

![Usuarios_rangos_velocidad_anual](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/assets/113273616/311f05af-a0b7-48c6-aec3-8fe96b957dcd)

En el gráfico observamos como a medida que pasan los años, la cantidad de usuarios de internet con velocidades mayores a 30 Mbps han ido en aumento y la cantidad de usuarios que utilizan internet con velocidades entre 6 y 10 Mbps se ha mantenido constante, la cantidad de usuarios en todas las demás velocidades ha disminuido. La tendencia observada en el gráfico muestra las necesidades actuales de los usuarios por adquirir Internet con las mejores velocidades de conexión posibles. 

El caso de que las velocidades de conexión entre 1 a 6 Mbps hayan mantenido una cantidad de usuarios constante a lo largo de los años, muestra que la relación entre el costo del servicio de Internet y la velocidad obtenida es satisfactoria para esos planes.

Se puede observar en el gráfico como disminuye la cantidad de usuarios para las velocidades entre 1 a 6 Mbps, hasta que en 2019 son superadas por las mayores a 30 Mbps, esto es debido a la pandemia del COVID-19. La pandemia creó la necesidad en las personas de tener una conexión más rápida a Internet para poder realizar videollamadas y comunicarse con sus seres queridos, además que durante la pandemia aumentó la cantidad de personas que trabajaban de forma remota, necesitando un Internet de alta velocidad para poder realizar llamadas y presentaciones de sus trabajos.

El comportamiento observado en el gráfico va acorde a lo visto en el gráfico comparativo de banda ancha y banda angosta, donde la cantidad de usuarios que utilizan el primero va en aumento constante, mientras que la cantidad de usuarios que utiliza banda angosta va disminuyendo anualmente. 

Por todo lo mencionado, la compañía debe enfocarse en ofertar planes de Internet con buenas velocidades de conexión y planes accesibles para adquirir la mayor cantidad de usuarios posibles, es decir, velocidades entre 6 a 10 Mbps y mayores a 30 Mbps.

Al haber observado el comportamiento de los diferentes rangos de velocidad a nivel nacional, uno se puede preguntar: ¿Cuál es el comportamiento de los rangos de velocidad por provincia? Para responder está pregunta, se creó un gráfico de barras que muestra la cantidad de usuarios con acceso a Internet por velocidad para el año 2022, tomando en cuenta solo los rangos de velocidad de interés, es decir, de 6 a 10 Mbps y mayores a 30 Mbps:

![Velocidad_por_provincia](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/assets/113273616/23b98eea-b2e0-498f-b48f-53dd0c6716e7)

El gráfico muestra que la mayoría de las provincias cuenta con Internet en las velocidades de estudio, es decir, de 6 a 10 Mbps y mayores a 30 Mbps. Además, permite observar como las provincias de San Luis o Tierra del Fuego cuentan con poca cantidad de usuarios para las velocidades mencionadas. La compañía debe enfocar sus esfuerzos en mejorar la velocidad de conexión de Internet y brindar planes accesibles a los usuarios en las provincias que presenten menor cantidad de usuarios conectados con las velocidades mencionadas y poder atraer y ganar una mayor cantidad de usuarios.

Es posible crear un KPI a partir de la información de la velocidad. Sin embargo, uno puede llegar a preguntarse: ¿Existe alguna relación entre las velocidades de conexión y la tecnología de Internet? Para responder está pregunta, primero es necesario analizar el comportamiento de las diferentes tecnologías de Internet a nivel nacional de forma anual:

![Usuarios_tecnologia_anual](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/assets/113273616/234f67d8-1f15-4369-aa18-9ff25dabd725)

En el gráfico se observa el aumento constante en la cantidad de usuarios que utilizan fibra óptica y Cablemodem anualmente y la disminución constante de la cantidad de usuarios en las otras tecnologías, especialmente en ADSL, la cual fue por mucho tiempo la tecnología más utilizada. Solo en el último año se observa una disminución en la cantidad de usuarios de Cablemodem y puede debeserse a la falta de los datos en el último trimestre del año 2022.

El comportamiento del gráfico concuerda con los gráficos anteriores, especialmente los de velocidad de conexión donde se ve un aumento en la cantidad de usuarios con mayores conexiones a Internet, ya que las tecnologías fibra óptica y Cablemodem son las que ofrecen las mayores velocidades de conexión. Específicamente fibra óptica, es la que ofrece el Internet más rápido y estable en el mercado actual. Estas tecnologías son las que cumplen con las necesidades actuales de los usuarios al permitir realizar videollamadas y proveer una mejor calidad en el servicio.

Por lo mencionado, la compañía debe enfocarse en ofrecer Internet con las mejores tecnologías: fibra óptica y Cablemodem, a través de planes accesibles  y, así, lograr captar y mantener la mayor cantidad de usuarios posibles.

Al igual que con la velocidad, se observa el comportamiento en cada provincia de las tecnologías más importantes (Cablemodem y fibra óptica) para el año 2022:

![tecnologia_por_provincia](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/assets/113273616/b7c8750c-f310-40a1-b58c-adb544f6f1a6)

Se puede observar que para el 2022 el Cablemodem es la tecnología más utilizada en casi todas las provincias de Argentina. Además, al comparar el gráfico con el de la población por provincia, se ve que la fibra óptica se encuentra principalmente en las provincias más pobladas. Lo observado en el gráfico tiene sentido, pues es la tendencia que se ha visto en todo el análisis: los usuarios están migrando a mayores velocidades por lo que necesitan las tecnologías que las suministren, y estas son Cablemodem y fibra óptica.

En el gráfico se ve como provincias como San Luis o San Juan tienen pocos usuarios de Cablemodem y fibra óptica, esto debido a la geografía montañosa de las provincias, lo que dificulta la instalación de la infraestructura necesaria para poder utilizar dichas tecnologías. En estas provincias es de esperarse que la tecnología más utilizada sea la Wireless (inalámbrica), la cuál también provee de altas velocidades de conexión y no necesita la instalación de infraestructura específica.

Por último, el hecho de que la fibra óptica se encuentre en los centros más poblados permite concluir que la tecnología es nueva en el país y, por ser nueva, llega primero a esas provincias más pobladas. Esto implica una gran oportunidad de crecimiento para la empresa, ya que puede invertir en fibra óptica y crecer a mayor velocidad que la competencia.

Una vez realizado el análisis a la cantidad de usuarios para la velocidad y la tecnología de forma individual, se realiza un mapa de calor para observar si existe alguna relación entre ellas:

![Correlacion_tecnologia_velocidad](https://github.com/luissgtorres/Data_Analytics_Project-Internet_Argentina/assets/113273616/607d818b-7c80-4620-abfb-1a0b7050757d)

En el mapa de calor se observan algunas correlaciones fuertes entre: velocidades mayores a 30 Mbps y fibra óptica, velocidades entre 1 a 6 Mbps y ADSL y entre 6 a 10 Mbps y ADSL y Cablemodem.

Estas correlaciones ayudan a confirmar lo expuesto en los gráficos anteriores, esto es: las mayores velocidades son alcanzadas por las mejores tecnologías, es decir, Cablemodem y fibra óptica. También, ayudan a ver la importancia de contar con buena tecnología para poder alcanzar las mejores velocidades de Internet. Por esto es importante que la compañía invierta en las mejores tecnologías y pueda captar la mayor cantidad de usuarios posibles.

Con todo el análisis realizado para la velocidad y tecnología, se plantea el siguiente KPI:

2- **Porcentaje de usuarios que adquieren internet de alta velocidad y tecnologías avanzadas por provincia:** este KPI reflejará el enfoque de la empresa en ofrecer el mejor servicio de Internet en el país. Con el análisis realizado, se puede definir el KPI de la siguiente forma:

"El objetivo es aumentar la cantidad de usuarios que utilizan fibra óptica o Cablemodem y adquieran planes de Internet de altas velocidades en un 14% anualmente, con especial enfoque en las provincias que tengan las velocidades de internet más bajas y cuenten con poco acceso a las mejores tecnologías."

Se toma el valor de 14%, pues es el promedio del aumento anual de Cablemodem que se puede observar en el gráfico de líneas para tecnologías. Se toma el valor del Cablemodem ya que es el que presenta la mayor cantidad de usuarios (más de 2 millones) al compararlo con las diferentes tecnologías y las diferentes velocidades.

El KPI se medirá sumando la cantidad total de usuarios que adquieran los planes de internet de alta velocidad con las tecnologías Cablemodem y fibra óptica por provincia, divididos entre el número total de usuarios de internet de la compañía en esa provincia y multiplicado por 100 para obtener el porcentaje.

Este KPI permite medir el éxito de la empresa en proveer servicios de calidad al unificar la velocidad y la tecnología. También permite identificar las provincias donde se está logrando un mayor impacto y en donde es necesario realizar mayores esfuerzos para captar más usuarios.

3- **Tasa de retención de usuarios:** este KPI refleja la capacidad de la empresa para retener a los usuarios que han optado por sus servicios, en este caso, servicios de Internet de alta velocidad con las mejores tecnologías del mercado. Se puede definir de la siguiente forma:

"Ofertar Internet accesible de la más alta calidad (alta velocidad y las últimas tecnologías), que permita mantener una tasa de retención de clientes de, al menos, 80% de forma anual a nivel nacional"

De acuerdo a [investigaciones realizadas](https://www.paddle.com/resources/industry-retention-rates), el valor de 80% es el valor promedio de tasa de retención en industrias de telecomunicaciones, por lo que se establece como el valor deseado para la empresa.

El KPI se medirá restando el número total de usuarios al final del año menos el número de usuarios nuevos, todo dividido entre el número total de usuarios al comienzo de ese año, multiplicado por 100 para obtener la tasa como porcentaje.

Este KPI permite evaluar los esfuerzos de la empresa en ofertar un servicio de calidad que satisfaga las necesidades de los usuarios actuales que tiene la industria. Le permite saber si está yendo en la dirección correcta al apostar por nuevas tecnologías e Internet más rápido.

Es importante señalar que, además de contar con el servicio de Internet de mejor calidad a nivel nacional, es necesario que la empresa cuenten con un servicio al cliente de calidad y tenga precios competitivos para poder tener una elevada tasa de retención.
</p></div>

<h4 align='center'>
 <b>Conclusiones</b>
</h4>

- El Internet es el único servicio de telecomunicaciones en Argentina que se mantiene en aumento anualmente.
- La tendencia actual en Argentina de los usuarios es Internet de banda ancha, Internet de alta velocidad y con las mejores tecnologías.
- Las velocidades que están adquiriendo mayor cantidad de usuarios son las que superan los 30 Mbps.
- La tecnología que tiene mayor cantidad de usuarios es el Cablemodem. Sin embargo, la fibra óptica ha mantenido un aumento en la cantidad de usuarios de forma anual.
- Algunas provincias no cuentan con servicio de Internet de calidad.

<div style="text-align: justify"><p style="text-align: justify;">
Como último comentario, es importante que las acciones que se tomen sean en base a los datos y los insights obtenidos a partir de estos. Y que se busque la mejor forma, a través de publicidades, inversión, promociones o alianzas, para lograr captar la mayor cantidad de usuarios posibles, mantener a los usuarios que ya son clientes y aumentar la rentabilidad de la empresa.
</p></div>

## Autor

[Luis Torres](luisgtorres16@gmail.com)
