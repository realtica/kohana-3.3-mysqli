kohana-3.3-mysqli
=================

Kohana 3.3 MySQLi driver

A simple substitution for the original MySQL driver. Just add as a module and set database driver to 'MySQLi'. 
Supports same functionality as the original driver. 

http://tomlankhorst.nl/mysqli-database-driver-for-kohana-3-3/

**Composer**
```
"require": {
    "tomlankhorst/kohana-3.3-mysqli": "dev-master",
}
```
tested over kohana 3.0.x too
============================
To working over kohana 3.0.x just change this code line #569 in:
```
database/classes/kohana/database.php
return preg_replace('/"(.+?)"/e', '$this->quote_identifier("$1")', $value);
by
return preg_replace_callback('/"(.+?)"/',
    function($matches) { return $this->quote_identifier($matches[1]); },
    $value);
```

https://github.com/kohana/database/blob/c04fa20ac54ecee6435273df2067bd76c791cab9/classes/kohana/database.php