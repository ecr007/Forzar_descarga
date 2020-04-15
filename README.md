Forzar_descarga
===============

Este codigo es para forzar descarga. De forma segura


## Forzar descarga en wordpress

```php
add_action('template_redirect','yoursite_template_redirect');
function yoursite_template_redirect() {
  if ($_SERVER['REQUEST_URI']=='/downloads/data.csv') {
    header("Content-type: application/x-msdownload",true,200);
    header("Content-Disposition: attachment; filename=data.csv");
    header("Pragma: no-cache");
    header("Expires: 0");
    echo 'data';
    exit();
  }
}
```
