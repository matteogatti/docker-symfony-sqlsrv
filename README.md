# Docker image for Symfony 4.x with SQL Server support

### Doctrine config

`.env` file

```
MSSQL_DATABASE_NAME="DB"
MSSQL_DATABASE_HOST="10.20.30.40\SQLEXPRESS"
MSSQL_DATABASE_USER="user"
MSSQL_DATABASE_PASSWORD="password"
MSSQL_DATABASE_PORT="1433"
```

`doctrine.yml` file

```
doctrine:
  dbal:
    default_connection: default
    connections:
      default:
        driver: 'sqlsrv'
        host: '%env(resolve:ZUCCHETTI_DATABASE_HOST)%'
        dbname: '%env(resolve:ZUCCHETTI_DATABASE_NAME)%'
        user: '%env(resolve:ZUCCHETTI_DATABASE_USER)%'
        password: '%env(resolve:ZUCCHETTI_DATABASE_PASSWORD)%'
        port: '%env(resolve:ZUCCHETTI_DATABASE_PORT)%'
        server_version: '2012'
        charset: 'UTF-8'
```

### SEE ALSO

- Requirements for Running Symfony [link](https://symfony.com/doc/4.2/reference/requirements.html)
- Using the Microsoft SQL Server Driver (SQLSRV) for PHP [link](https://www.phpkb.com/kb/article/using-the-microsoft-sql-server-driver-sqlsrv-for-php-37.html)
