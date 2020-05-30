# Replace "file_get_contents" function with Curl

[EN]

Replaces "file_get_contents" function with a Curl function called "file_get_contents_curl", this is useful when your webserver doesn't have "allow_url_fopen" enabled.

[PT]

Substitui a função "fie_get_contents" com uma função de Curl chamada "file_get_contents_curl", é util caso o teu servidor web não tenha "allow_url_fopen" ativo.

# Requirements:
- [PHP](https://php.net/) (Version 5.6.0 or newer)
- Curl installed.

# Script
functions.php
```php
<?php
function file_get_contents_curl($url) {
    $ch = curl_init();

    curl_setopt($ch, CURLOPT_AUTOREFERER, TRUE);
    curl_setopt($ch, CURLOPT_HEADER, 0);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($ch, CURLOPT_URL, $url);
    curl_setopt($ch, CURLOPT_FOLLOWLOCATION, TRUE);       

    $data = curl_exec($ch);
    curl_close($ch);

    return $data;
}
?>
```

# Contact me
- [My Steam](https://steamcommunity.com/id/DikaN1337)
- My Discord: " DikaN'#0001
