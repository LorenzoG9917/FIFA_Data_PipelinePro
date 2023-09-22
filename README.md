# FIFA_Data_PipelinePro

## Objetivo
El objetivo principal de este proyecto es realizar un análisis exhaustivo de datos históricos de la Copa del Mundo de la FIFA, utilizando técnicas de ingeniería de datos y herramientas de Google Cloud Platform. Esto incluye la exploración, transformación y enriquecimiento de datos, así como su almacenamiento en BigQuery para su posterior análisis y visualización. Este proyecto simula un entorno de Data Lake con sus capas correspondientes, permitiendo una gestión eficiente de los datos.
## Arquitectura
![FIFA_Data_PipelinePro](https://github.com/LorenzoG9917/FIFA_Data_PipelinePro/assets/121797266/e128c8a7-1c31-42c6-ac48-ba0c158fe70a)


## Descripción
Este proyecto de ingeniería de datos se centra en el análisis exhaustivo de los datos históricos de la Copa del Mundo de la FIFA. A lo largo de su ejecución, se divide en varias etapas clave:

1. **Exploración y Análisis Inicial (EDA)**: En esta fase inicial, se realiza un Análisis Exploratorio de Datos para comprender la estructura y la calidad de los datos de la Copa del Mundo de la FIFA.
2. **Carga de Datos en la Nube**: Los datos se cargan desde archivos locales al entorno de Google Colab y luego se transfieren a Google Cloud Storage (GCS), creando así la capa raw del Data Lake.
3. **Transformación de Datos (ETL)**: Se lleva a cabo la transformación de los datos crudos para corregir problemas de calidad, como valores nulos y duplicados. Se crean nuevas tablas y se ajustan los tipos de datos.
4. **Almacenamiento en Capa Gold**: Los datos transformados se almacenan en una capa Gold en GCS, que representa la zona de datos limpios y listos para el análisis.
5. **Carga datos transformados en BigQuery**: Los datos transformados se cargan en BigQuery, donde se pueden realizar análisis avanzados y consultas complejas.
6. **Carga de Datos Enriquecidos**: Además de los datos principales, se cargan datos enriquecidos, como estadísticas de jugadores y equipos, para un análisis más profundo.

## Conjunto de Datos Utilizado
El [conjunto de datos](https://www.kaggle.com/datasets/abecklas/fifa-world-cup) utilizado en este proyecto comprende un amplio archivo de información histórica sobre la Copa del Mundo de la FIFA, abarcando desde sus inicios hasta el año 2014. Estos datos ofrecen una visión completa y detallada de los torneos de la Copa del Mundo, incluyendo detalles sobre partidos, equipos, jugadores, estadios, goles y asistencias.

 

## Contenido
El proyecto incluye los siguientes archivos:

- **fifaEda.ipynb**: Un jupyter notebook que realiza un Análisis Exploratorio de Datos (EDA) sobre conjuntos de datos relacionados con la Copa del Mundo de la FIFA. Este archivo incluye el proceso de exploración, transformación y generación de varios dataframes para obtener insights valiosos sobre los datos.

- **upload_files.ipynb**: Un script Python que carga archivos desde tu sistema local o Drive a Google Cloud Storage. Estos archivos se almacenan en un Bucket específico para su posterior procesamiento en la nube.

- **transformLoad_files.ipynb**: Un script Python que transforma los datos de la capa raw de Cloud Storage y los carga en la capa gold. Este archivo también carga datos enriquecidos a BigQuery para su análisis posterior.

## Paso a Paso
1. **Creación de Servicios**: Inicie un servicio  de Cloud Storage y BigQuery en Google Cloud Platform (GCP).
2. **Bucket de Almacenamiento**: Cree un bucket llamado "fifa_project" en Cloud Storage.
3. **Organización de Datos**: Dentro del bucket, cree dos directorios: "raw_data" y "gold_data".
4. **Cuenta de Servicio**: Cree una cuenta de servicio llamada "fifa-project" con roles específicos. 
   - Administrador de almacenamiento en Cloud Storage (Storage Admin)
   - Administrador de objetos de Storage (Storage Object Admin)
   - Editor de datos de BigQuery (BigQuery Data Editor)
   - Usuario de BigQuery (BigQuery User)
   - Visualizador de datos de BigQuery (BigQuery Data Viewer)

5. **Descarga de Credenciales**: Descargue un archivo JSON de credenciales para acceder a BigQuery y Cloud Storage.
6. **Configurar Credenciales en los notebooks**: Especificar en los notebooks la ruta de las credenciales descargadas en el paso anterior.
     ```
    os.environ['GOOGLE_APPLICATION_CREDENTIALS'] = '[path/credentials/service-fifa-lg.json]'
     ```
6. **Ejecución de Notebooks**: Utilice los notebooks "upload_files.ipynb" y "transformLoad_files.ipynb" para cargar y transformar datos.
7. **Verificación en BigQuery**: Verifique visualmente la carga exitosa de datos en BigQuery.
![BigQuery](https://github.com/LorenzoG9917/FIFA_Data_PipelinePro/assets/121797266/457514a5-0f87-45de-911a-112614b8b486)
## Autor
Este proyecto ha sido desarrollado por [Lorenzo Guerrero](https://www.linkedin.com/feed/) con fines educativos.

---

**Nota:** Este proyecto es un ejemplo educativo y puede requerir adaptaciones para su uso en un entorno de producción. Los datos utilizados aquí son ficticios y se proporcionan solo con fines de demostración.
