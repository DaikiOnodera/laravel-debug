# Laravel how to debug on VSCode

This project is based on template from `composer create-project laravel/laravel example-app` .

1. Install PHP Debug for VSCode

https://marketplace.visualstudio.com/items?itemName=xdebug.php-debug

2. Edit php.ini

Your php.ini file's location `php -r 'phpinfo();' | grep php.ini '   
Add following lines to your php.ini   

```
[xdebug]
xdebug.mode = debug
xdebug.start_with_request = yes
xdebug.client_host = 0.0.0.0
xdebug.client_port = 9012
xdebug.log = "/var/log/xdebug.log"
```

3. Write launch.json

Port must correspond to xdebug.client_port in php.ini   
pathMappings must correspond to app directory.   
` ${userHome}/Playground/php_test/example-app ` in my case   

4. Launch Program

` php artisan serve --host 0.0.0.0 `   
Run->Start Debugging