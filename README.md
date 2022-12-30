# Mapa-Huantraico

### Mapa geológico del área de Huantraico, Provincia de Neuquén, Argentina

## Objetivos
Confeccionar un mapa geológico a partir de imágenes satelitales, DEMs y hojas geológicas preexistentes

## Análisis de la zona de estudio
Este trabajo tiene como objetivo confeccionar un mapa geológico de una zona asignada de manera remota. La zona de trabajo, marcada con un recuadro en la figura 1, se encuentra en el Norte de la Provincia de Neuquén, Argentina, al Sureste de la localidad de Chos Malal, cabecera del partido homónimo. El área es atravesada de Este a Sur por el Río Neuquén y al Noreste se encuentra ubicada la Sierra de Huantraico. Se puede acceder a la zona desde el Norte o desde el Este por la ruta provincial Nº7, desde el Suroeste por la ruta provincial Nº9 o desde el Sureste por la ruta provincial Nº1, como se observa en la figura 2.

La red fluvial de la zona está compuesta principalmente por el Río Neuquén, que drena hacia el Sur, y sobre el cual desembocan los cursos intermitentes. La menor cota topográfica se encuentra en el lecho del río, en el Sur de la zona, y su altura es de 698 m. La zona más elevada, en cambio, se encuentra en la Sierra de Huantraico, con una elevación de 1869 m.

<p align="center">
    <img width="200" src="https://drive.google.com/uc?export=view&id=1ICIhcGDDNRW1pnI4jokV8AvIuQX8WsYD" alt="Mapa 1">
    <img width="200" src="https://drive.google.com/uc?export=view&id=1iWaezPN3Sn3fTHgqxvA_x-v4wCaKeeR9" alt="Mapa 2">
    
Figura 1: Ubicación de la zona de estudio.
</p>

<p align="center">
    <img width="200" src="https://drive.google.com/uc?export=view&id=1-fjlC-pMkCu-SGIiX3ZNaatewBD6JVtc" alt="Mapa 3">
    
Figura 2: Mapa de la zona de estudio con los accesos y el Río Neuquén.
</p>

## Exportar, importar y referenciar información
Como base para generar las curvas de nivel se utilizaron dos modelos de elevación digital (DEM). Uno fue extraído de la base de datos de la USGS [1], desde donde se descargó el modelo obtenido en la Misión Topográfica Radar Shuttle (SRTM), propiedad de la Administración Nacional de la Aeronáutica y del Espacio de los Estados Unidos (NASA) y la Agencia Nacional de Inteligencia Geoespacial de los Estados Unidos (NGA) [2]. Esta misión adquirió datos durante 11 días en el año 2000 y llevó a bordo del transbordador dos sensores que operaban en diferentes bandas de frecuencia, uno en banda C y otro en banda X. Las bandas corresponden al tipo de onda que emite el radar, que en parte determina la resolución espacial de la imagen. La banda C trabaja con longitudes de onda de entre 3,8-7,5 cm mientras que la banda X utiliza una longitud de onda entre 2,4-3,8 cm [3]. La imagen radar utilizada en este caso corresponde a la de la banda C [4].

Los datos de elevación de esta misión fueron obtenidos por interferometría radar, donde el radar emite una señal que es reflejada por la superficie de la Tierra y captada al mismo tiempo por dos antenas que se encuentran en el transbordador a una distancia de 60 metros 2 entre ellas. Al detectar la señal desde diferentes puntos del espacio se puede obtener, mediante un análisis de la diferencia de fase, la altura a la que se reflejó, que es la altura topográfica.

La resolución espacial de este DEM es de 1 arco de segundo, aproximadamente 30 metros y tiene una precisión vertical de aproximadamente 16 metros [5].

El otro modelo utilizado corresponde al del satélite ALOS PALSAR, de la Agencia Japonesa de Exploración Aeroespacial (JAXA) que fue obtenido desde la base de datos de las Instalaciones Satelitales de Alaska (ASF) [6]. Este satélite estuvo en órbita de 2006 a 2011, pero sólo se utilizaron imágenes recopiladas entre 2010 y 2011 y tiene una resolución espacial de 12,5 metros.

El sensor PALSAR (Phased Array L-band Synthetic Aperture Radar), como sus siglas lo indican, es un sensor de radar, que emite una onda en la banda L, de entre 15-30 cm de longitud de onda. También puede obtener la altura topográfica se utiliza un radar de interferometría de apertura sintética (SAR) donde las dos señales que se utilizan para hacer interferometría no se obtienen de la misma forma que con el SRTM. En este caso las dos señales se captan en la misma antena del satélite, pero desde puntos en el espacio ligeramente diferentes. A medida que el satélite se mueve en el espacio, recibe la señal reflejada en la Tierra desde ángulos diferentes, y con esta información puede calcularse la elevación y generar el DEM.

La ventaja de ambos sensores es que la tecnología de radar permite obtener datos de noche y aunque haya nubes, porque no reflejan la señal del radar.

Para ambos modelos que pueden observarse en la figura 3, con el programa QGIS, se obtuvieron curvas de nivel con una equidistancia de 50 m. Se observó que las curvas no coincidían en el espacio, sino que había un desplazamiento relativo entre ellas. Esto es producto de los errores de cada modelo, y puede deberse a las diferencias en la obtención de los datos y la longitud de onda utilizada . Para trabajar con un solo DEM se compararon las curvas de nivel con los puntos GPS de alta precisión de la Red Nacional de Nivelación generados por el Instituto Geográfico Nacional (IGN) [7]. El DEM del SRTM resultó tener menos diferencia respecto a los puntos de Alta Precisión. Se observa en la figura 4 que las curvas de nivel de misma cota no se encuentran en el mismo lugar, y que los puntos de alta precisión parecen corresponderse más con las curvas del SRTM.

Por ejemplo, se observa en la figura 4 que cotas cercanas a 1100 m (imagen izquierda) se encuentran casi sobre la curva de nivel de 1100 m de SRTM. Asimismo, cotas intermedias como el punto de 1071 m, deberían encontrarse a una distancia media entre las curvas de 1050 m y 1100 m y esto sucede con las curvas del SRTM. Se ve en este caso que la curva 1100 m del ALOS PALSAR coincide con la cota de 1071 m, dando cuenta que el modelo de ALOS PALSAR tiene una diferencia vertical de aproximadamente 30 m.

También se compararon las curvas de nivel con la elevación que informa Google Earth y se observó que las curvas del ALOS PALSAR tenían un error de 50 m aproximadamente mientras que las del SRTM 1 se encuentran desplazadas menos de 20 m. Esto se debe a que Google Earth Pro utiliza el DEM de SRTM y por eso la diferencia es menor.

Dado que se continuó trabajando con las imágenes satelitales de Google Earth Pro y los puntos de Alta Precisión del IGN se correspondían más con las curvas del SRTM , se decidió utilizar el DEM de SRTM.

## Análisis y digitalización de estructuras
En Google Earth, mediante la técnica de contornos estructurales, se midieron actitudes a lo largo de toda la zona. Con esta información, más el mapeo de unidades realizado previamente con la Hoja Geológica 3769-III Chos Malal del SEGEMAR como referencia, se pudieron identificar diferentes estructuras.

La zona Oeste del mapa se encuentran las unidades más antiguas que pertenecen al Grupo Mendoza, del Cretácico Inferior, que se encuentran deformadas por un sistema de plegamientos. Se identificaron tanto pliegues sinclinales como anticlinales, todos ellos con ejes buzantes de rumbo Norte-Sur o Noroeste-Sureste. Como se observa en la figura 5, los ejes en su mayoría buzan hacia el Sur, excepto el del anticlinal que se encuentra al Sur del mapa, cuyo eje buza hacia el Norte.

En discordancia sobre los pliegues se encuentran unidades del Cretácico Superior, que tienen actitudes variables. Al Este de las unidades del Cretácico Inferior se extienden de Norte a Sur una serie de afloramientos de las mismas unidades, que inclinan entre 10º y 20º hacia el Este, y que se encuentran dislocados por fallas inversas de entre 20º y 40º de rumbo y que inclinan hacia el Sureste.

También se reconoció otra falla inversa al Norte del mapa, donde se observa una repetición de contactos tectónicos de unidades del Cretácico Superior cuyos estratos buzan unos 27º hacia el Sureste del mapa. Un poco más al norte de esta falla se observa el afloramiento de diques de la Formación Desfiladero Negro de edad neógena miocena generando un contacto intrusivo con unidades del Cretácico Superior.

## Provincias geológicas
La zona de Huantraico se encuentra ubicada en el Engolfamiento Neuquino, una de las provincias geológicas de la Argentina descriptas por Ramos en Geología Argentina [8]. Esta provincia geológica se extiende en el sur de Mendoza y la región extrandina de Neuquén. En el mapa realizado se observan algunas características propias de esta provincia, como el vulcanismo de lavas basálticas de edad neógena miocena que caracterizan la zona Norte de esta provincia, y que en el mapa de Huantraico se encuentra representado por el Basalto Huantraico y el Basalto Cerro Cabras. También se observa la secuencia Cretácica de ambiente continental y el basamento marino del Cretácico Inferior compuesto por el Grupo Mendoza.

##Referencias
- [1] USGS Earth Explorer: [USGS EarthExplorer](https://earthexplorer.usgs.gov/)
- [2] USGS Archivo EROS, DEM SRTM 1Arc-Second Global: [USGS EROS Archive - Digital Elevation - Shuttle Radar Topography Mission (SRTM) 1 Arc-Second Global](https://www.usgs.gov/centers/eros/science/usgs-eros-archive-digital-elevation-shuttle-radar-topography-mission-srtm-1-arc?qt-science_center_objects=0#qt-science_center_objects)
- [3] Earth Data, NASA: [What is Synthetic Aperture Radar? | Earthdata](https://earthdata.nasa.gov/learn/backgrounders/what-is-sar)
- [4] Jet Propulsion Laboratory, California Institute of Technology NASA [Shuttle Radar Topography Mission](https://www2.jpl.nasa.gov/srtm/dataprod.htm)
- [5] Mnas Makul et al. Uncertainties in the Shuttle Radar Topography Mission (SRTM) Heights: Insights from the Indian Himalaya and Peninsula. Publicado online 8/02/2017. doi: 10.1038/srep41672
- [6] ASF Data Search Vertex: [ASF Data Search (alaska.edu)](https://search.asf.alaska.edu/#/)
- [7] IGN Red de Nivelación de Alta precisión: [Capas SIG | Instituto Geográfico Nacional (ign.gob.ar)](https://www.ign.gob.ar/NuestrasActividades/InformacionGeoespacial/CapasSIG)
- [8] Ramos, V. (1999) Geología Argentina. Cap 3: Las provincias geológicas del territorio Argentino. Instituto de Geología y Recursos Minerales, Buenos Aires.
