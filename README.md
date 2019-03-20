# Detect-browser-language

### About ###
When developing multilingual website and like to retrieve the browser language and use this language as the default language
for my website. 
Here’s how I get the language used by the client browser:

### Usage ###

See the `index.php` file, or use this below:

```php
<?php
function get_client_language($availableLanguages, $default='en'){
    if (isset($_SERVER['HTTP_ACCEPT_LANGUAGE'])) {
        $langs=explode(',',$_SERVER['HTTP_ACCEPT_LANGUAGE']);

        foreach ($langs as $value){
            $choice=substr($value,0,2);
            if(in_array($choice, $availableLanguages)){
                return $choice;
            }
        }
    } 
    return $default;
}
```
