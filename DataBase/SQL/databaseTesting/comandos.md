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

- Para hacer queryes mas avanzados se puede utilizar uniones como lo son: (where, and)
  Un ejemplo para esto es el siguiente comando:

```shell
select * from customers where city = "NYC" and postalCode = "10022";

Query result:
# customerNumber, customerName, contactLastName, contactFirstName, phone, addressLine1, addressLine2, city, state, postalCode, country, salesRepEmployeeNumber, creditLimit
'131', 'Land of Toys Inc.', 'Lee', 'Kwai', '2125557818', '897 Long Airport Avenue', NULL, 'NYC', 'NY', '10022', 'USA', '1323', '114900.00'
'151', 'Muscle Machine Inc', 'Young', 'Jeff', '2125557413', '4092 Furth Circle', 'Suite 400', 'NYC', 'NY', '10022', 'USA', '1286', '138500.00'
'181', 'Vitachrome Inc.', 'Frick', 'Michael', '2125551500', '2678 Kingston Rd.', 'Suite 101', 'NYC', 'NY', '10022', 'USA', '1286', '76400.00'
'424', 'Classic Legends Inc.', 'Hernandez', 'Maria', '2125558493', '5905 Pompton St.', 'Suite 750', 'NYC', 'NY', '10022', 'USA', '1286', '67500.00'
'456', 'Microscale Inc.', 'Choi', 'Yu', '2125551957', '5290 North Pendale Street', 'Suite 200', 'NYC', 'NY', '10022', 'USA', '1286', '39800.00'

```
