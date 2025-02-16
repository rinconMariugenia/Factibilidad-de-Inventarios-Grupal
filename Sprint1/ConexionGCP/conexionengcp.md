# Guía para Configuración en Google Cloud Platform (GCP)

Esta guía explica los pasos necesarios para configurar el almacenamiento en la nube y la integración con BigQuery en Google Cloud Platform (GCP), así como la creación de un Service Account y su conexión mediante Python.

## 1. Crear un Bucket en Google Cloud Storage
- **Accede a Google Cloud Console** y ve a la sección de **Cloud Storage**.
- Haz clic en **Crear Bucket**.
- Asigna un **nombre único** para el bucket y selecciona la región donde deseas almacenar tus archivos.
- Configura las opciones de almacenamiento según tus necesidades y haz clic en **Crear**.

## 2. Crear una Carpeta en el Bucket
- Después de haber creado el bucket, selecciona el **bucket** en el que deseas agregar la carpeta.
- Haz clic en **Crear carpeta**.
- Asigna un nombre a la carpeta y haz clic en **Crear**.

## 3. Ir a BigQuery y Agregar una Nueva Tabla
- Accede a **BigQuery** desde la consola de Google Cloud.
- Haz clic en el botón **Agregar** en la parte superior izquierda.
- Selecciona la opción **Google Cloud Storage** como fuente de datos.

## 4. Seleccionar la Tabla a Importar
- Selecciona el archivo que deseas importar desde el **Bucket** que creaste en Google Cloud Storage.
- Puedes elegir un archivo de tipo CSV, JSON o Avro según el formato de tus datos.

## 5. Seleccionar la Base de Datos
- En la sección de **Destino**, selecciona la base de datos donde deseas almacenar la tabla.
- Si no existe ninguna base de datos, haz clic en **Crear conjunto de datos nuevo**.
- Asigna un nombre adecuado para el conjunto de datos y selecciona una ubicación para el mismo.

## 6. Asignar Permisos de Editor a las Personas que Necesitan Acceder a GCP
- Dirígete a la sección de **IAM** en Google Cloud Platform.
- Haz clic en **Agregar** para añadir usuarios.
- Ingresa el **correo electrónico** de las personas a las que deseas otorgar acceso.
- Asigna el **Rol** de **Administrador de BigQuery - Editor** a las personas que deben tener permisos para editar y gestionar BigQuery.

## 7. Crear un Service Account
- Dirígete a la sección de **Service Accounts** en Google Cloud.
- Haz clic en **Crear cuenta de servicio**.
- Asigna un nombre y una descripción a la cuenta de servicio.
- En la sección de permisos, asigna los roles necesarios para interactuar con los recursos de Google Cloud (por ejemplo, **Editor** o roles específicos para BigQuery y Cloud Storage).

## 8. Generar la Clave del Service Account
- Después de crear el Service Account, selecciona la cuenta creada en el panel.
- Haz clic en **Crear clave** para generar una nueva clave de tipo **JSON**.
- Guarda el archivo `.JSON` en un lugar seguro, ya que será necesario para conectar tu código de Python con GCP.

## Conectar el Código de Python con GCP
Una vez que tengas el archivo `.JSON` de la clave del Service Account, puedes usar la librería `google-auth` en Python para autenticar tu aplicación y acceder a los servicios de GCP, como BigQuery y Google Cloud Storage.

```python
from google.cloud import bigquery
from google.oauth2 import service_account

# Ruta al archivo .JSON
key_path = 'ruta/a/tu/archivo.json'

# Autenticación usando el archivo de clave
credentials = service_account.Credentials.from_service_account_file(key_path)

# Crear un cliente de BigQuery
client = bigquery.Client(credentials=credentials, project=credentials.project_id)