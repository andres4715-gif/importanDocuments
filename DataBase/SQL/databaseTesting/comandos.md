# _Comandos_

- Para usar la db:

```shell
$ use <Nombre de la base de datos>
$ use classicModels;
```

- Para consultar toda la data de una tabla especifica:

```shell
$ select * from <Nombre de la tabla>
$ select * from employees;
```

- Para consultar las tablas que tiene la base de datos:

```shell
$ show tables;

- Results:
`customers`,
`employees`,
`offices`,
`orderdetails`,
`orders`,
`payments`,
`productlines`,
`products`
```

- Para obtener toda la información de la meta data de la base de datos:

```shell
$ describe information_schema.columns;
```

- Para obtener el numero de las columnas de una tabla en especifico,
  notar que se esta renombrando el nombre de la columna como: numberOfColumns

```shell
SELECT count(*) AS numberOfColumns FROM information_schema.columns WHERE table_name = 'customers';

Query result:
numberOfColumns: 13
```

- Para obtener el nombre de las columnas de una tabla en especifico,
  notar que se esta renombrando el nombre de la columna como: nameOfColumns

```shell
SELECT column_name AS nameOfColumns FROM information_schema.columns WHERE table_name = 'customers';

Query result:
# nameOfColumns
'addressLine1'
'addressLine2'
'city'
'contactFirstName'
'contactLastName'
'country'
'creditLimit'
'customerName'
'customerNumber'
'phone'
'postalCode'
'salesRepEmployeeNumber'
'state'
```

- Para obtener el tipo de dato de las columnas de una tabla en especifico,
  notar que se esta renombrando el nombre de la columna como: nameOfColumns

```shell
SELECT column_name AS nameOfColumns FROM information_schema.columns WHERE table_name = 'customers';

Query result:
# nameOfColumns, DATA_TYPE
'addressLine1', 'varchar'
'addressLine2', 'varchar'
'city', 'varchar'
'contactFirstName', 'varchar'
'contactLastName', 'varchar'
'country', 'varchar'
'creditLimit', 'decimal'
'customerName', 'varchar'
'customerNumber', 'int'
'phone', 'varchar'
'postalCode', 'varchar'
'salesRepEmployeeNumber', 'int'
'state', 'varchar'
```

- Para obtener el column type de las columnas de una tabla en especifico,
  notar que se esta renombrando el nombre de la columna como: nameOfColumns

```shell
SELECT column_name AS nameOfColumns, column_type FROM information_schema.columns WHERE table_name = 'customers';

Query result:
# nameOfColumns, COLUMN_TYPE
'addressLine1', 'varchar(50)'
'addressLine2', 'varchar(50)'
'city', 'varchar(50)'
'contactFirstName', 'varchar(50)'
'contactLastName', 'varchar(50)'
'country', 'varchar(50)'
'creditLimit', 'decimal(10,2)'
'customerName', 'varchar(50)'
'customerNumber', 'int'
'phone', 'varchar(50)'
'postalCode', 'varchar(15)'
'salesRepEmployeeNumber', 'int'
'state', 'varchar(50)'
```
