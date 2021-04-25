# CRUD API POST BLOG

API RESTful CRUD post para blog, usando [Slim PHP micro framework](https://www.slimframework.com) e [MongoDB](https://mongodb.com)

Used technologies: `PHP 7, Slim 4, MongoDB, PHPUnit, dotenv`.

## INSTALAÇÃO:

### Requisitos:

- Composer.
- PHP 7.4+.
- mongoDB.


### Composer:

Baixe o repositório ou clone ele:
Dependencias
```bash
$ composer require slim/slim:"^4.5"
$ composer require mongodb/mongodb
$ composer require slim/psr7
$ composer require vlucas/phpdotenv
$ composer require pimple/pimple
$ composer require phpunit/phpunit --dev
```
- [slim/slim](https://github.com/slimphp/Slim): Slim Framework utilizado para a construção da API.
- [mongodb/mongo-php-library](https://github.com/mongodb/mongo-php-library): MongoDB Utilizado como Banco de Dados.
- [slim/psr7](https://github.com/slimphp/Slim-Psr7): PSR-7 implementação para utilizar com o Slim 4.
- [vlucas/phpdotenv](https://github.com/vlucas/phpdotenv): Ler o arquivo `.env` para `getenv()`, `$_ENV` e `$_SERVER` automaticamente.
- [pimple/pimple](https://github.com/silexphp/Pimple): Injeção de dependência php.

#### Configure a conexão com o MongoDB:

Api utiliza por padrão o MongoDB

Você deve configurar corretamente o arquivo `.env` conforme abaixo:
Você pode utilizar o https://mlab.com/plans/pricing/#plan-type=sandbox como banco de dados, versão gratuita.

```
mongodb+srv://<NameUser>:<password>@cluster0.ng1wy.mongodb.net/<COLLATION>?retryWrites=<TRUE/FALSE>&w=majority
MongoDB_HOST = '<NameUser>:<password>@cluster0.ng1wy.mongodb.net/'
MongoDB_COLLATION = <COLLATION>
MongoDB_RETRY_WRITES = '<TRUE/FALSE>'
MongoDB_W = 'majority'

DISPLAY_ERROR_DETAILS=true
SLIM_BASE_PATH=''
```
`DISPLAY_ERROR_DETAILS` deve ser `false` em produção, true somente em desenvolvimento.

## Rotas:

### PADRÃO:

- `GET /` Verifica a o estado da API e sua versão

- `GET /status` Verifica a o status da API e sua versão

### CRUD:

- `GET /posts` Busca todos os posts e retorna um `array`
- `POST /posts` Cria um post e retorna `array` contendo o STATUS e o ID
- `GET /posts/{id}` Busca o post pelo `{id}` e retorna um `objeto`
- `PUT /posts/{id}` Busca o post pelo `{id}` atualiza o post e retorna um `objeto`
- `DELETE /posts/{id}` Busca o post pelo `{id}` deleta o post e retorna um `objeto`

### DOCUMENTAÇÃO OFICIAL
- [MongoDB](https://docs.mongodb.com/php-library/v1.8/)
- [Slim Framework](https://www.slimframework.com/docs/v4/)
