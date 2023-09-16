# Upload SVG files

You have to go to the path `public_html/wp-includes/functions.php`. And add the following code at the end of the file:

```php
function add_file_types_to_uploads( $file_types ) {
    $new_filetypes = array();
    $new_filetypes['svg'] = 'image/svg+xml';
    $file_types = array_merge($file_types, $new_filetypes );
    
    return $file_types;
}

add_filter('upload_mimes', 'add_file_types_to_uploads');
```

> Note: this code was taked from [Cómo subir a WordPress archivos SVG: 2 métodos seguros](https://www.hostinger.co/tutoriales/cargar-en-wordpress-svg)
