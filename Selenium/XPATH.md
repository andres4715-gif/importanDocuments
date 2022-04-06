# _Manejo de xpath_

[Video Tutorial 1](https://www.youtube.com/watch?v=U0WMFjnbb4I&list=PLL34mf651faPB-LyEP0-a7Avp_RHO0Lsm&index=122)

[Video Tutorial 2](https://www.youtube.com/watch?v=NhG__BL8zFo)

### Page to practice XPath
- [The automation zone](https://theautomationzone.blogspot.com/2020/07/xpath-practice.html)

## Basic format of XPath

```shell
XPath: //tagname[@Atribute= 'value']

Examples

XPath: //input[@id='login']
XPath: (//div[@class="content-events py-4"])[2]
XPath: //*[@id="a"][1]
XPath: //div[contains(@class, 'col col-10')]
```

## Positions
Se utiliza para trabajar con las tablas: 
```shell
Examples

XPath: //table[@id='table1']//tr   ---> Retorna todos los elementos de la tabla
XPath: //table[@id='table1']//tr [1]   ---> Retorna el elemento que se quiera de la tabla
XPath: //table[@id='table1']//tr [position() = 1]   ---> Retorna el elemento que se quiera de la tabla
XPath: //table[@id='table1']//tr [last()]   ---> Retorna el ultimo elemento de la tabla
XPath: //table[@id='table1']//tr [last()]/td/input   ---> En caso que tenga mas hijos y los necesitemos
XPath: //table[@id='table1']//tr [last() - 1]   ---> En caso de necesitar ir de abajo para arriba validando algo
```

## Normalize Spaces
Remover espacios en los textos
```shell
Examples

XPath: //p[normalize-space(text()) = 'Tommy']     ----> Remover espacios al inicio o al final de un texto
XPath: //p[normalize-space(@name) = 'aa']     ----> Remover espacios al inicio o al final de un texto

```
## Start with

```shell
XPath: //tagname[starts.vith(@Attibute, 'value')]

Examples

XPath: //div[starts-with(@class, 'col-sm')]
XPath: //iframe[starts-with(@name, 'google_esf')]
XPath: //h3[starts-with(@class, 'text-center py')]
```

## Contains
```shell
XPath: //tagname[contains(@Attibute, 'value')]

Examples

XPath: //div[contains(@class, 'col col-8')]
XPath: //h3[contains(text(), 'GASOLINA')]
XPath: //h3[contains(text(), 'SMILEY')]
XPath: //div[contains(@class, 'slider')]
```

## Text()
```shell
XPath: //tagname[text()= 'ActualText']

Examples

XPath: //h3[text()= 'Redes sociales']
XPath: //h1[text()='Destacados']
XPath: //a[text()='Ver más eventos']
XPath: //h3[text()='MALOKA']
```

## AND & OR
```shell
XPath: //tagname[@Attribute='value' or Attribute='value']
XPath: //tagname[@Attribute='value' and Attribute='value']
XPath: //tagname[(@Attribute='value' or Attribute='value') and Attribute='value']

Examples

XPath: //input[@class="gLFyf gsfi" and @name="q"]
XPath: //div[@class="UUbT9" and @jsname="UUbT9"]
XPath: //input[@class="gLFyf gsfi" or @name="q"]
XPath: //input[@class="gNO89b" or @name="btnK"]
XPath: //p[@name='a' and @id='a']
```

## Parent, Child, Self
```shell
XPath Parent: //tagname[@Attribute= 'Value']//parent::tagname
XPath Child:  //tagname[@Attribute= 'Value']//child::tagname
XPath Self:   //tagname[@Attribute= 'Value']//self::tagname

Examples

XPath: //a[@class="gb_d"]/input       --->  Getting children 
XPath: //a[@class="gb_d"]//parent::a
XPath: //img[@class="logo img-responsive"]//parent::a//parent::div
XPath: //div[@class="category_footer toggle-footer"]//parent::section
XPath: //div[@class="shopping_cart"]//child::a//child::b
XPath: //div[@id="block_top_menu"]//child::div
XPath: //div[@class="col-xs-12 col-sm-6"]//child::form//child::h3
XPath: //li[@class="clearfix"]//child::div//child::span[1]
```

## Descendant & Descendant-or-self
- Children
```shell
XPath: //tagname[Attribute= 'value']//descendant::tagname
XPath: //tagname[Attribute= 'value']//descendant-or-self::tagname

Examples

XPath: //div[@id='divC']/span/imput  or it is posible too: //div[@id='divC']//imput 
XPath: //li[@class="clearfix"]//descendant::a
XPath: //button[@name="submitNewsletter"]//descendant::span
```

## Ancestor and Ancestor-or-self
- Parent and grand parent
```shell
XPath: //tagname[Attribute= 'value']//ancestor::tagname
XPath: //tagname[Attribute= 'value']//ancestor-or-self::tagname

Examples

XPath: //li[@class="clearfix"]//ancestor::a
XPath: //button[@name="submitNewsletter"]//ancestor::span
```

## Following and following-sibling
```shell
XPath: //tagname[Attribute= 'value']//following::tagname
XPath: //tagname[Attribute= 'value']//following-sibling::tagname

Examples

XPath: //div[@class="cat-title active"]//following-sibling::ul//child::li[1]//following-sibling::a
```

## Preceding and preceding-sibling
```shell
XPath: //tagname[Attribute= 'value']//preceding::tagname
XPath: //tagname[Attribute= 'value']//preceding-sibling::tagname

Examples

XPath: //div[@class="cat-title active"]//preceding::ul//child::li
XPath: //div[@class="cat-title active"]//preceding-sibling::ul//child::li
```



