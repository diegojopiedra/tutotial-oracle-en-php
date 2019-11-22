# Tutorial Oracle en PHP

A continuación se muestran los pasos para poder utilizar una base de datos Oracle en un ambiente PHP.
Independientemente del sistema operativo se requieren 2 componentes

1. El cliente de Oracle para el sistema operativo
2. La extención OCI8 para comunicar el cliente de Oracle con PHP

## En Windows

### Cliente Oracle

> Es importante **descargar la versión 12** del Instant Cliente para poder asegurar la compatiblidad, ya que otras versiónes pueden no estar soportadas como por ejemplo la **19**

1. Descarga el Instant Cliente desde <https://www.oracle.com/database/technologies/instant-client/downloads.html>. Buscar exactamente `instantclient-basic-windows.x64-12.2.0.1.0.zip`
2. Se puede utilizar en cualquier ubicación para descomprimir, sin embargo se suguiere `C:\Oracle\instantclient_12_1`.
3. Copie los siguientes archivos de `instantclient_12_1` a `apache\bin`.
   1. `oci.dll`
   2. `oraociei12.dll`
   3. `oraons.dll`

> **OPCIONAL:** Se puede agregar al PATH de windows esta la ruta del Instant Cliente, en este caso `C:\Oracle\instantclient_12_1`. El PATH se encuenta en `This PC>Properties>Advanced system settings>Enviroment Variable ...`
> Debe colocarse sobre la variable Path y hacer click en Edit

### Extención OCI8

1. Descargar el DLL más reciente del sitio <https://pecl.php.net/package/oci8>. En este caso usamos PHP 7.3 y escogemos la opción Thread Safe, esto varía según su versión de PHP y bits del OS.
   1. `Available Releases > Downloads > DLL`
   2. `DLL List > 7.3 Thread Safe (TS) x64`
2. Descomprimir `php_oci8-2.2.0-7.3-ts-vc15-x64.zip`
3. Copiar el archivo `php_oci8_12c.dll` de la carpeta descomprimida a `php\ext`
4. Modificar el archivo `php.ini` descomentado la linea `extension=oci8_12c`
