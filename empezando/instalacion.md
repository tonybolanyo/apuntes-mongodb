## Instalando mongodb en Windows 7

Lo primero es descargar el instalador. En el momento de escribir este documento la versión más actualizada es la 3.0. La descarga  se realiza desde la web oficial [http://www.mongodb.com](http://www.mongodb.com) que detecta automáticamente mi sistema. La versión que vdescargo es ```Windows 64-bit 2008 R2+```

En la carpeta de descargas tengo el archivo del instalador ```mongodb-win32-x86_64-2008plus-ssl-3.0.1-signed.msi```.

Al ser la primera instalación no voy a personalizarla, simplemente sigo el asistente realizando una instalación completa.

Una vez acaba la instalación todavía es necesario realizar algunas acciones extra de configuración.

### Configuración tras la instalación

Lo primero es agregar al PATH la ruta de los ejecutables de mongodb. La instalación se ha realizado en la carpeta por defecto, así que hay que agregar al path la ruta:

```
C:\Program Files\MongoDB\Server\3.0\bin
```

Los pasos necesarios son:

1. Botón inicio
2. Click con el botón derecho sobre <<Equipo>>
3. Propiedades
4. En la ventana del panel de control que se abre, opción _Configuración avanzada del sistema_ en la parte izquierda.
5. Botón _Variables de entorno_
6. En la sección variables del SISTEMA, buscar PATH y al final agregar la ruta separada de la anterior con ";"

Aceptar en todas las ventanas. Para que los cambios se hagan efectivos es necesario reiniciar cualquier ventana de línea de comandos (éstas no se actualizarán solas).

Por último, es necesario crear la carpeta donde se almacenarán los datos. Por defecto mongodb los busca en la carpeta ```/data/db``` del disco donde está instalado el sistema, así que creamos la carpeta en ```C:```

```
mkdir C:\data
mkdir C:\data\db
```

Una vez creadas ya podemos comprobar nuestra instalación usando el comando

```
mongodb
```

Al ser la primera vez que lo arrancamos, el sistema nos alerta de la seguridad si tenemos activado el Firewall del sistema. Evidentemente tendremos que permitir el acceso para poder usar la base de datos.

Acepto la opción de permitirlo en redes privadas.

La consola muestra algunos mensajes al arranque y, al final, nos muestra el puerto en el que el servicio de mongodb es accesible, en el caso por defecto **27017**.

```
2015-03-28T10:54:19.206+0100 I CONTROL  Hotfix KB2731284 or later update is not 
installed, will zero-out data files
2015-03-28T10:54:19.228+0100 I JOURNAL  [initandlisten] journal dir=C:\data\db\j
ournal
2015-03-28T10:54:19.229+0100 I JOURNAL  [initandlisten] recover : no journal fil
es present, no recovery needed
2015-03-28T10:54:19.377+0100 I JOURNAL  [durability] Durability thread started
2015-03-28T10:54:19.378+0100 I JOURNAL  [journal writer] Journal writer thread s
tarted
2015-03-28T10:54:19.398+0100 I CONTROL  [initandlisten] MongoDB starting : pid=8
008 port=27017 dbpath=C:\data\db\ 64-bit host=TONY-PC
2015-03-28T10:54:19.399+0100 I CONTROL  [initandlisten] targetMinOS: Windows 7/W
indows Server 2008 R2
2015-03-28T10:54:19.399+0100 I CONTROL  [initandlisten] db version v3.0.1
2015-03-28T10:54:19.399+0100 I CONTROL  [initandlisten] git version: 534b5a3f9d1
0f00cd27737fbcd951032248b5952
2015-03-28T10:54:19.399+0100 I CONTROL  [initandlisten] OpenSSL version: OpenSSL
 1.0.1j-fips 15 Oct 2014
2015-03-28T10:54:19.400+0100 I CONTROL  [initandlisten] build info: windows sys.
getwindowsversion(major=6, minor=1, build=7601, platform=2, service_pack='Servic
e Pack 1') BOOST_LIB_VERSION=1_49
2015-03-28T10:54:19.400+0100 I CONTROL  [initandlisten] allocator: system
2015-03-28T10:54:19.400+0100 I CONTROL  [initandlisten] options: {}
2015-03-28T10:54:19.403+0100 I INDEX    [initandlisten] allocating new ns file C
:\data\db\local.ns, filling with zeroes...
2015-03-28T10:54:19.750+0100 I STORAGE  [FileAllocator] allocating new datafile
C:\data\db\local.0, filling with zeroes...
2015-03-28T10:54:19.750+0100 I STORAGE  [FileAllocator] creating directory C:\da
ta\db\_tmp
2015-03-28T10:54:19.870+0100 I STORAGE  [FileAllocator] done allocating datafile
 C:\data\db\local.0, size: 64MB,  took 0.119 secs
2015-03-28T10:54:19.876+0100 I NETWORK  [initandlisten] waiting for connections
on port 27017
```
 Ya estamos listos para empezar a usar nuestro servidor de datos con mongodb.
 