# Analisis de Vulnerabilidad Volcanica Tonila-Queseria
Proyecto de programacion 2 en conjunto con proyecto Integrador
Código markdown
# Título del Proyecto
**Autores:** Miguel Zambrano Pascual/ Jose Manuel Rivera Ramirez

## Introducción
El presente proyecto aborda el analisis de vulnerabilidad respecto a la actividad volcanica del volcan de Colima en las zonas geograficas de Tonila y Queseria. Con el principal objetivo de identificar las principales amenazas, evaluar los riesgos potenciales y proponer estrategias de mitigación y preparación que contribuyan a la seguridad y resiliencia de las comunidades locales.

## Desarrollo
El Volcán de Colima, reconocido como uno de los más activos de México y América Latina, representa una amenaza latente y significativa para las comunidades circundantes, especialmente para las zonas geográficas de Tonila y Quesería. Estas localidades se encuentran en una región de alta susceptibilidad a eventos volcánicos como erupciones explosivas, flujos piroclásticos, lahares y caída de ceniza, fenómenos que históricamente han tenido un impacto devastador en áreas similares. La vulnerabilidad de estas comunidades no solo radica en su proximidad al volcán, sino también en una serie de factores que agravan el riesgo, como la densidad poblacional, la infraestructura inadecuada, la falta de planes de evacuación eficientes, y la limitada conciencia pública sobre los peligros asociados con la actividad volcánica.
El Volcán de Colima, ubicado en la frontera entre los estados de Jalisco y Colima en México, es uno de los volcanes más activos del país. Las comunidades cercanas, como Tonila y Quesería, se ven afectadas periódicamente por su actividad eruptiva. La actividad volcánica representa una amenaza constante debido a fenómenos como flujos piroclásticos, ceniza volcánica, lahares (flujos de lodo y escombros), y terremotos volcánicos.

Este proyecto busca integrar diversas fuentes de datos para realizar un análisis de vulnerabilidad, evaluando el riesgo potencial en estas dos zonas geográficas específicas y generando un sistema que permita una mejor toma de decisiones en materia de protección civil.
Principales objetivos
Obtener datos geoespaciales de las zonas de Tonila y Quesería.
Integrar datos sobre la actividad volcánica del Volcán de Colima (como erupciones pasadas, emisiones de ceniza, monitoreo sísmico, etc.).
Desarrollar un modelo de vulnerabilidad basado en la ubicación geográfica de las comunidades, su infraestructura y la proximidad al volcán.
 Metodología:
  Recopilación de Datos:
Datos Geoespaciales:

Uso de sistemas de información geográfica (SIG) para obtener mapas topográficos y geográficos de las áreas de Tonila y Quesería.
Datos de infraestructuras (vías de comunicación, hospitales, escuelas, etc.).
Uso de plataformas como Google Earth Engine o QGIS para visualizar áreas de riesgo.
## Manejo de Datos
Estos son algunos codigos que nos podran ayudar con nuestro proyecto:

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

ademas del siguiente:
Este código carga un archivo shapefile que contiene las zonas geográficas de Tonila y Quesería y traza un mapa con la ubicación del volcán de Colima.
import geopandas as gpd
import matplotlib.pyplot as plt

# Cargar los datos geoespaciales
# Suponemos que tienes un archivo shapefile con las fronteras geográficas de Tonila y Quesería
zona = gpd.read_file('zonas.shp')

# Mostrar el mapa con la ubicación de Tonila y Quesería
fig, ax = plt.subplots(figsize=(10, 10))
zona.plot(ax=ax, color='lightblue')

# Agregar la ubicación del Volcán de Colima
volcan = {'type': 'Point', 'coordinates': [-103.724, 19.514]}  # Coordenadas aproximadas
gdf_volcan = gpd.GeoDataFrame([volcan], crs="EPSG:4326")

# Plot
gdf_volcan.plot(ax=ax, color='red', marker='o', markersize=100)

# Mostrar el mapa
plt.title('Ubicación del Volcán de Colima y Zonas de Riesgo (Tonila y Quesería)')
plt.show()


## Resultados
De acuerdo con los datos propuestos podemos obtener algunos resultados que nos seran muy utiles para nuestro proyecto como por ejemplo, saber la ubicacion entre cada unas de las comunidades como Tonila y Queseria respecto al volcan de Colima y de esta manera identificar su grado de vulnerabilidad ante un acontecimiento volcanico como lo es una erupcion volcanica o incluso la caida de ceniza que es un evento muy frecuente debido a la actividad volcanica de tal volcan. 
De la misma manera con algunas librerias podemos obtener un mapa que nos permita tener un elemento visual que nos ayude a realizar esta analisis de vulnerabilidad, esto de acuerdo con el codigo que hayamos implementado para lograr tal fin.
import numpy as np
import matplotlib.pyplot as plt

# Parámetros de simulación (esto es un ejemplo básico)
# Asumimos que el flujo del lahar sigue una forma simplificada
# El volcán se encuentra en (0, 0) y se simula su propagación a través de un valle
area = np.zeros((100, 100))  # Una malla de 100x100
volcan_pos = (50, 50)  # Ubicación del volcán

# Establecemos una simple simulación de propagación con caída de material
for i in range(50, 100):  # Simulamos un flujo hacia abajo
    for j in range(50, 100):
        area[i, j] = np.exp(-((i - volcan_pos[0])**2 + (j - volcan_pos[1])**2)/100)  # Exponencial para simular la propagación

# Mostrar el mapa del lahar simulado
plt.imshow(area, cmap='hot', interpolation='nearest')
plt.colorbar(label='Intensidad del lahar')
plt.title('Simulación de Propagación del Lahar')
plt.show()



## Conclusiones
Los codigos que implementamos son algunas herramientas que nos ayudaron con el procesamiento de datos espaciales, y con ello realizar un analisis mas completo para la realizacion de nuestro proyecto. Esto codigos lo modificamos de acuerdo a nuestro objetivo y nuestro proyecto con la finalidad de elaborar un analisis mas exhaustivo respto a la actividad volcanica del Volcan de Colima especialmente en las zonas geograficas de Tonila y Quesería.
Sin duda alguna este proyecto nos permitira tener informacion confiable y accessibles para poder afrentar un acontecimiento volcanico, ademas contribuira a las autoridades a la toma de decisiones en situaciones de emergencia de manera preventiva.

