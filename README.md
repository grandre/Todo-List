App de lista de afazeres feito em laravel e vue
Para instalar a app:

- Clone o repo 
```
git clone https://github.com/grandre/Todo-List
```
- Dentro da pasta do projeto instale as dependencias com o composer 
```
composer install
```
- Dentro da pasta do projeto Instale as dependencias do NPM 
```
npm install
```
- Compie o arquivo .env.example e crie o .env e modifique de acordo com suas necessidades
- Gere a key da sua app 
```
php artisan key:generate
```
- Com o banco criado, modifique o .env para conectar com o banco
- Rode as migrations 
```
php artisan migrate
```
- Rode os comandos 
```
php artisan serve 
npm run hot
```
e use o WAMP, XAMPP, LAMP como servidor

Deve funcionar agora!