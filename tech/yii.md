composer global require "fxp/composer-asset-plugin"
composer create-project --prefer-dist yiisoft/yii2-app-basic basic
#https://github.com/yiisoft/yii2-app-advanced/blob/master/docs/guide/start-installation.md
composer create-project --prefer-dist yiisoft/yii2-app-advanced yii-application
#https://github.com/sizeg/yii2-jwt
composer require sizeg/yii2-jwt

http://www.manks.top/yii2-frame-rbac-template.html
composer require dmstr/yii2-adminlte-asset "2.*"


Generating Migrations ¶

    php yii migrate/create create_post --fields="title:string,body:text"
