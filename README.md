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


## Resultados
De acuerdo con los datos propuestos podemos obtener algunos resultados que nos seran muy utiles para nuestro proyecto como por ejemplo, saber la ubicacion entre cada unas de las comunidades como Tonila y Queseria respecto al volcan de Colima y de esta manera identificar su grado de vulnerabilidad ante un acontecimiento volcanico como lo es una erupcion volcanica o incluso la caida de ceniza que es un evento muy frecuente debido a la actividad volcanica de tal volcan. 
De la misma manera con algunas librerias podemos obtener un mapa que nos permita tener un elemento visual que nos ayude a realizar esta analisis de vulnerabilidad, esto de acuerdo con el codigo que hayamos implementado para lograr tal fin.



## Conclusiones
Los codigos que implementamos son algunas herramientas que nos ayudaron con el procesamiento de datos espaciales, y con ello realizar un analisis mas completo para la realizacion de nuestro proyecto. Esto codigos lo modificamos de acuerdo a nuestro objetivo y nuestro proyecto con la finalidad de elaborar un analisis mas exhaustivo respto a la actividad volcanica del Volcan de Colima especialmente en las zonas geograficas de Tonila y Quesería.
Sin duda alguna este proyecto nos permitira tener informacion confiable y accessibles para poder afrentar un acontecimiento volcanico, ademas contribuira a las autoridades a la toma de decisiones en situaciones de emergencia de manera preventiva.

