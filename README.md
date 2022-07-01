docker-compose build
docker-compose up -d
docker exec -it app bash
    composer install && composer require jenssegers/mongodb
    ### change config/database.php
                    //    'default' => env('DB_CONNECTION', 'mysql'),
            //'default' => env('DB_CONNECTION', 'mongodb'),
            ....
            ....
            'connections' => [
            ....
            ....
            'mongodb' => [
            'driver'   => 'mongodb',
            'host'     => env('MONGO_HOST'),
            'port'     => env('MONGO_PORT'),
            'database' => env('MONGO_DATABASE'),
            'username' => env('MONGO_USERNAME'),
            'password' => env('MONGO_PASSWORD'),
            'options'  => [
            'database' => env('MONGO_DATABASE')
            ]
            ],
        Add proveder 		
            Jenssegers\Mongodb\MongodbServiceProvider::class
    php artisan migrate --seed

