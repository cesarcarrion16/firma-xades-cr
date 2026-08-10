# firma-xades-cr

Adaptación del proyecto [hacienda-firmador-php](https://github.com/enzojimenez/hacienda-firmador-php) de [enzojimenez](https://github.com/enzojimenez) para instalarse mediante composer

### Instalación

```bash
composer require stibenamm/firma-xades-cr:dev-master
```

### Ejemplo rápido laravel
```php
//routes/web.php
Route::get('/', function(){
	$firmador = new Stibenamm\FirmaXadesCR\Firmador();
  	$xml = '/ruta/archivoXml';
  	$pfx = '/ruta/llaveCriptografica';
  	$pin = '0000';
  	$archivo = $firmador->firmarXml($pfx,$pin,$xml,$firmador::TO_XML_STRING);
  	return response($archivo, '200')->header('Content-Type', 'text/xml');
});
```
# Política FE 4.4

Para namespaces de comprobantes electrónicos Costa Rica v4.4, el paquete usa
la política XAdES-EPES del Anexo 2 oficial de Hacienda:

- URI: `https://cdn.comprobanteselectronicos.go.cr/xml-schemas/Resoluci%C3%B3n_General_sobre_disposiciones_t%C3%A9cnicas_comprobantes_electr%C3%B3nicos_para_efectos_tributarios.pdf`
- Digest: SHA-256, `DWxin1xWOeI8OuWQXazh4VjLWAaCLAA954em7DMh0h8=`

Fuente: https://www.hacienda.go.cr/docs/ANEXOS_Y_ESTRUCTURAS_V4.4.pdf
