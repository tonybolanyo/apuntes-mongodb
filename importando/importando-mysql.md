## Importando datos desde MySQL

MongoDb soporta la importación de datos desde diferentes formatos de archivo. Muchos de nosotros hemos manejado diferentes bases de datos, pero todos los que hemos realizado aplicaciones web seguro que, antes o después, necesitamos pasar datos desde una instalación de MySQL a nuestro nuevo MongoDb.

El primer paso será exportar los datos desde MySQL. Para ello yo utilizaría la opción de exportación de datos desde phpMyAdmin, sin el que yo no podría vivir.

Una vez exportados los datos en formato json, debemos tener en cuenta que en el fichero resultante no aparezcam comentarios al pricipio, ya que generarán errores en el proceso de importación a MongoDb. Suponiendo que el servicio de MongoDb está activo, en la línea de comandos basta con usar el comando estándar de importación ```mongoimport``` según veis a continuación

```bash
mongoimport --type json --file mis_datos.json --collection micolección --db mibasededatos --jsonArray
```


