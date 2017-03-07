# Laravel on Bluemix

[![forthebadge](http://forthebadge.com/images/badges/built-with-love.svg)](http://laravel-on-bluemix.mybluemix.net/)

This is boilerplate for working with Laravel on Bluemix.
You can fork it for your own purpose.

## Things I change
### manifest.yml

```sh
  env:
    APP_ENV: production
    APP_DEBUG: false
    APP_KEY: SomeRandomString
```

### .bp-config/options.json
```sh
  "PHP_VERSION": "{PHP_56_LATEST}",
  "COMPOSER_VENDOR_DIR": "vendor",
  "COMPOSER_VERSION": "latest",
  "WEBDIR": "public",
  "PHP_EXTENSIONS": [
    "mcrypt",
    "mbstring",
    "mysqli",
    "openssl",
    "pdo",
    "pdo_mysql",
    "tokenizer",
    "fileinfo"
```

### .cfignore
```sh
  composer.lock
  vendor/
```

### composer.json
```sh
  "post-install-cmd": [
    ........
    "mkdir -p /tmp/app/bootstrap/cache",
    "mkdir -p /tmp/app/storage/framework/sessions",
    "mkdir -p /tmp/app/storage/framework/views",
    "mkdir -p /tmp/app/storage/framework/cache",
    ........
  ],
  "post-update-cmd": [
    ........
    "mkdir -p /tmp/app/bootstrap/cache",
    "mkdir -p /tmp/app/storage/framework/sessions",
    "mkdir -p /tmp/app/storage/framework/views",
    "mkdir -p /tmp/app/storage/framework/cache",
    ........
  ]
```

### Feedback
If you like what you see, then please send me a tweet @tarikgan;

If you've any better idea to implement and deploy Laravel on Bluemix, then please post an issue of create a pull request.

Have an awesome day!
