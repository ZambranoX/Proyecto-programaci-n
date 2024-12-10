# Analisis de Vulnerabilidad Volcanica Tonila-Queseria
Proyecto de programacion 2 en conjunto con proyecto Integrador
Código markdown
# Título del Proyecto
**Autores:** Miguel Zambrano Pascual

## Introducción
El presente proyecto aborda el analisis de vulnerabilidad respecto a la actividad volcanica del volcan de Colima en las zonas geograficas de Tonila y Queseria. Con el principal objetivo de identificar las principales amenazas, evaluar los riesgos potenciales y proponer estrategias de mitigación y preparación que contribuyan a la seguridad y resiliencia de las comunidades locales.
El vínculo con el curso de programación en este proyecto sin duda alguna no es mas que nada atendiendo a la necesidad de incorporar la parte tecnologica en el ambito del análisis de datos geoespaciales y el manejo correcto de los datos que se tienen para obtener un mayor provecho de los mismos. Tenemos claro que la finalidad de la  programacion es sin duda alguna facilitar tareas que parecen muy complejas y a su vez dar resolucin a las mismas y tambien la optimizacion del tiempo, por ello tenemos presente que la progracion es una herramienta bastante util para el analisis y manejo de datos. Mediante el uso de herramientas y aplicaciones informáticas, será posible procesar grandes volúmenes de datos, generar modelos predictivos y crear sistemas de alerta temprana que permitan una toma de decisiones más eficiente y oportuna. Así, la integración de la programación no solo enriquece el análisis técnico, sino que también contribuye a mejorar la preparación y respuesta ante posibles emergencias volcánicas, protegiendo a las comunidades locales y promoviendo su resiliencia ante desastres naturales.
Lo que se pretende en este proyecto de programacion es de acuerdo a la informacion que hemos obtenido en nuestro proyecto integrador elaborar un programa que nos ayude a analizar dicha informacion pero ahora de una manera geoespacial y visual y objetivamente, de tal manera que podamos comprender el comportamiento de los datos obtenidos. Durante el curso de programacion estuvimos viendo algunas librerias y modulos muy importantes con el manejo de datos geoespaciales por lo tanto tenemos presente que tenemos las bases para fortaleer nuestro proyecto integrador.
El uso de la programación nos  permitirá automatizar procesos de monitoreo constante, haciendo tareas complejas de una manera mas sencilla y rapida lo que nos ayudara a otimizar los tiempos de las personas que colaboren en dicho proyecto lo que facilitará la detección temprana de eventos volcánicos. Esta información procesada de manera eficiente se transformará en alertas tempranas, las cuales son fundamentales para reducir la exposición a los riesgos y minimizar los efectos de una posible erupción.
Con el uso de lenguajes de programación como Python, es posible manipular y analizar estos datos geoespaciales, generar modelos de simulación de flujos de lava y lahares, y realizar predicciones basadas en patrones históricos de actividad volcánica. Además, las bibliotecas como GeoPandas, Folium y Shapely ofrecen poderosas herramientas para trabajar con datos espaciales, visualizando la propagación de peligros volcánicos en mapas interactivos y detallados.
A través del uso de la programación, se pueden desarrollar plataformas interactivas de monitoreo y alerta temprana que ayuden a las autoridades locales y a la población a estar preparadas ante una posible erupción. Estas plataformas permiten la visualización en tiempo real de la actividad volcánica y la predicción de su impacto en diferentes zonas, evaluando la proximidad de las áreas vulnerables y ofreciendo recomendaciones para una evacuación eficiente. Además, el uso de simulaciones numéricas y modelos de riesgo permite evaluar el impacto de distintos tipos de erupciones, como la caída de ceniza o los flujos piroclásticos, sobre las infraestructuras, los cultivos y la población.

## Desarrollo
El Volcán de Colima, reconocido como uno de los más activos de México y América Latina, representa una amenaza latente y significativa para las comunidades circundantes, especialmente para las zonas geográficas de Tonila y Quesería. Estas localidades se encuentran en una región de alta susceptibilidad a eventos volcánicos como erupciones explosivas, flujos piroclásticos, lahares y caída de ceniza, fenómenos que históricamente han tenido un impacto devastador en áreas similares. La vulnerabilidad de estas comunidades no solo radica en su proximidad al volcán, sino también en una serie de factores que agravan el riesgo, como la densidad poblacional, la infraestructura inadecuada, la falta de planes de evacuación eficientes, y la limitada conciencia pública sobre los peligros asociados con la actividad volcánica.
El Volcán de Colima, ubicado en la frontera entre los estados de Jalisco y Colima en México, es uno de los volcanes más activos del país. Las comunidades cercanas, como Tonila y Quesería, se ven afectadas periódicamente por su actividad eruptiva. La actividad volcánica representa una amenaza constante debido a fenómenos como flujos piroclásticos, ceniza volcánica, lahares (flujos de lodo y escombros), y terremotos volcánicos.

Este proyecto busca integrar diversas fuentes de datos para realizar un análisis de vulnerabilidad, evaluando el riesgo potencial en estas dos zonas geográficas específicas y generando un sistema que permita una mejor toma de decisiones en materia de protección civil.
Principales objetivos
Obtener datos geoespaciales de las zonas de Tonila y Quesería.
Integrar datos sobre la actividad volcánica del Volcán de Colima (como erupciones pasadas, emisiones de ceniza, monitoreo sísmico, etc.).
Desarrollar un modelo de vulnerabilidad basado en la ubicación geográfica de las comunidades, su infraestructura y la proximidad al volcán.
De acuerdo con los datos propuestos podemos obtener algunos resultados que nos serán muy útiles para nuestro proyecto como, por ejemplo, saber la ubicación entre cada una de las comunidades como Tonila y Quesería respecto al volcán de Colima y de esta manera identificar su grado de vulnerabilidad ante un acontecimiento volcánico como lo es una erupción volcánica o incluso la caída de ceniza que es un evento muy frecuente debido a la actividad volcánica de tal volcán. 
De la misma manera con algunas librerías podemos obtener un mapa que nos permita tener un elemento visual que nos ayude a realizar este análisis de vulnerabilidad, esto de acuerdo con el código que hayamos implementado para lograr tal fin.

 Metodología:
  Recopilación de Datos:
Datos Geoespaciales:

Uso de sistemas de información geográfica (SIG) para obtener mapas topográficos y geográficos de las áreas de Tonila y Quesería.
Datos de infraestructuras (vías de comunicación, hospitales, escuelas, etc.).
Uso de plataformas como Google Earth Engine o QGIS para visualizar áreas de riesgo.
## Manejo de Datos
Estos son algunos codigos que nos podran ayudar con nuestro proyecto:

!pip install geopy matplotlib



from geopy.distance import geodesic
import matplotlib.pyplot as plt

# Coordenadas del cráter del Volcán de Colima
crater_coords = (19.514, -103.617)  # Latitud, Longitud

# Definir niveles de riesgo según la distancia
def calcular_riesgo(lat, lon):
    distancia = geodesic(crater_coords, (lat, lon)).kilometers
    if distancia < 10:
        return "Alto"
    elif distancia < 30:
        return "Moderado"
    else:
        return "Bajo"

# Ejemplo de puntos alrededor del volcán
lugares = [
    {"nombre": "Ciudad Guzmán", "coords": (19.703, -103.461)},
    {"nombre": "Colima", "coords": (19.243, -103.725)},
    {"nombre": "Quesería", "coords": (19.386533548675246, -103.57492819091863)},
    {"nombre": "Tonila", "coords": (19.411082000407788, -103.5483929881344)},
]

# Evaluar riesgos para cada lugar
for lugar in lugares:
    riesgo = calcular_riesgo(*lugar["coords"])
    lugar["riesgo"] = riesgo
    print(f"{lugar['nombre']}: Riesgo {riesgo}")

# Visualizar puntos y riesgos en un gráfico simple
fig, ax = plt.subplots()
for lugar in lugares:
    lat, lon = lugar["coords"]
    color = {"Alto": "red", "Moderado": "orange", "Bajo": "green"}[lugar["riesgo"]]
    ax.scatter(lon, lat, c=color, label=lugar["nombre"])
    ax.text(lon, lat, lugar["nombre"], fontsize=8)

# Añadir el volcán al gráfico
ax.scatter(crater_coords[1], crater_coords[0], c="black", label="Volcán de Colima")
ax.text(crater_coords[1], crater_coords[0], "Volcán", fontsize=10, color="black")

ax.set_title("Riesgos Volcánicos en el Volcán de Colima")
ax.set_xlabel("Longitud")
ax.set_ylabel("Latitud")
plt.legend()
plt.show()

Un codigo mas que nos permite obtener la distancia que existe entre el volcan de Colima y cada una de las localides en cuestion de analisis, aunque este programa no nos arroja un resultado visual nos permite tener un dato certero y a su vez poder utilizarlo para calcular algunas distancias que sean requeridas teniendo como referencias esta comunidades.
from shapely.geometry import Point
from geopy.distance import geodesic

# Coordenadas del volcán de Colima
volcan_coords = (19.514, -103.724)

# Coordenadas de las zonas (Tonila y Quesería)
tonila_coords = (19.256, -103.614)
queseria_coords = (19.324, -103.563)

# Crear los puntos
volcan_point = Point(volcan_coords[1], volcan_coords[0])  # Longitud, Latitud
tonila_point = Point(tonila_coords[1], tonila_coords[0])
queseria_point = Point(queseria_coords[1], queseria_coords[0])

# Calcular la distancia entre el volcán y las zonas
distancia_tonila = geodesic(volcan_coords, tonila_coords).km
distancia_queseria = geodesic(volcan_coords, queseria_coords).km

# Imprimir los resultados
print(f'Distancia entre el Volcán y Tonila: {distancia_tonila:.2f} km')
print(f'Distancia entre el Volcán y Quesería: {distancia_queseria:.2f} km')



## Resultados
De acuerdo con los datos propuestos podemos obtener algunos resultados que nos seran muy utiles para nuestro proyecto como por ejemplo, saber la ubicacion entre cada unas de las comunidades como Tonila y Queseria respecto al volcan de Colima y de esta manera identificar su grado de vulnerabilidad ante un acontecimiento volcanico como lo es una erupcion volcanica o incluso la caida de ceniza que es un evento muy frecuente debido a la actividad volcanica de tal volcan. 
De la misma manera con algunas librerias podemos obtener un mapa que nos permita tener un elemento visual que nos ayude a realizar esta analisis de vulnerabilidad, esto de acuerdo con el codigo que hayamos implementado para lograr tal fin.



## Conclusiones
Los codigos que implementamos son algunas herramientas que nos ayudaron con el procesamiento de datos espaciales, y con ello realizar un analisis mas completo para la realizacion de nuestro proyecto. Esto codigos lo modificamos de acuerdo a nuestro objetivo y nuestro proyecto con la finalidad de elaborar un analisis mas exhaustivo respto a la actividad volcanica del Volcan de Colima especialmente en las zonas geograficas de Tonila y Quesería.
Sin duda alguna este proyecto nos permitira tener informacion confiable y accessibles para poder afrentar un acontecimiento volcanico, ademas contribuira a las autoridades a la toma de decisiones en situaciones de emergencia de manera preventiva.
Código Mejorado

Código para mostrar en mapa interactivo comunidades aledañas al volcán 
import folium
from IPython.display import display

# Crear un mapa centrado en el Volcán de Colima
mapa = folium.Map(location=[19.514, -103.724], zoom_start=10)

# Agregar marcadores para las zonas de riesgo
folium.Marker([19.40979, -103.55071], popup='Tonila').add_to(mapa)
folium.Marker([19.38756, -103.57219], popup='Quesería').add_to(mapa)
folium.Marker([19.37504, -103.71179], popup='Suchitlan').add_to(mapa)
folium.Marker([19.51239, -103.61686], popup='Volcán de Colima', icon=folium.Icon(color='red')).add_to(mapa)

# Mostrar el mapa 
display(mapa) 


