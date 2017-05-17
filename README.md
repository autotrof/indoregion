# azishapidin/indoregion
Package containing region of Indonesia (provinces, regencies, districts, and villages) for Laravel

> This package is still in development stage and still not running well

## How to Use => This is just instructions for me (Azis Hapidin) :smile: hehe

### Clone this Package to Laravel Project
### Load Package via Main composer.json and PSR-4
Just add this in composer.json
```
...
"psr-4": {
    ...
    "Azishapidin\\IndoRegion\\": "packages/azishapidin/indoregion/src"
    ...
}
...
```
Next run this command on main Laravel Project:
```
composer dump-autoload
```
### Register Service Provider in config/app.php
Open config/app.php and add IndoRegion Service Provider to the Array of Service Providers:
```
// ... other providers
Illuminate\View\ViewServiceProvider::class,
Azishapidin\IndoRegion\IndoRegionServiceProvider::class,
```

### Publish our 'senjata'
Go to Command Line and run this command:
```
php artisan vendor:publish
```
This command will copy these directories to our Project:
* Migration files from [/packages/azishapidin/indoregion/src/database/migrations] To [/database/migrations]
* Seeder files from [/packages/azishapidin/indoregion/src/database/seeds] To [/database/seeds]
* Model files [/packages/azishapidin/indoregion/src/database/model] To [/app/Model]

### Running Migration and Seeder
Now, we must running migrations for create table in our database and run Seeder for fill it. Just run these in Command Line:
```
composer dump-autoload
php artisan migrate
php artisan db:seed --class=IndoRegionProvinceSeeder
php artisan db:seed --class=IndoRegionRegencySeeder
php artisan db:seed --class=IndoRegionDistrictSeeder
php artisan db:seed --class=IndoRegionVillageSeeder
```
