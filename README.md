>> Sistem Autentikasi Laravel

Ada 3 cara: 
- Bikin dari nol
- Laravel Fortify (Headless UI) (ini yang akan dipelajari)
- Laravel Jetstream

# Laravel Fortify 

## Installation

1. `composer require laravel/fortify`

2. `php artisan vendor:publish --provider="Laravel\Fortify\FortifyServiceProvider"`

3. `php artisan migrate`

4. Tambahkan di `app.php` bagian `providers`: `App\Providers\FortifyServiceProvider::class,`

5. Atur beberapa fitur yang ingin digunakan. `config/fortify.php`

6. Atur `FortifyServiceProvider.php` sesuai kebutuhan di bagian `boot`:


`Login Function`
        
        Fortify::loginView(function () {
            return view('auth.login');
        });

`Register Function`

        Fortify::registerView(function () {
            return view('auth.register');
        });

`Reset Password Function`

        Fortify::resetPasswordView(function ($request) {
            return view('auth.reset-password', ['request' => $request]);
        });

## Install Laravel UI Bootstrap Auth

1. `composer require laravel/ui`

2. `php artisan ui bootstrap --auth`

3. `npm install && npm run dev`