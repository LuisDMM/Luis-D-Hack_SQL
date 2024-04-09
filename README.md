# Luis-D-Hack_SQL

## 🏆 H-1
![](https://github.com/LuisDMM/Luis-D-Hack_SQL/blob/main/Screenshot/Hack_1.png)

-----------------
⚡ script
```sh
create table countries(
  id_country serial primary key,
  name varchar(100) not null
);

create table users(
  id_user serial primary key,
  id_country int not null,
  email varchar (200) not null,
  name varchar (100) not null,
  foreign key (id_country) references countries (id_country)
);
```

## 🏆 H-2
![](https://github.com/LuisDMM/Luis-D-Hack_SQL/blob/main/Screenshot/Hack_2.png)

-----------------
⚡ script
```sh
create table countries(
  id_country serial primary key,
  name varchar(100) not null
);

create table users(
  id_user serial primary key,
  id_country int not null,
  email varchar (200) not null,
  name varchar (100) not null,
  foreign key (id_country) references countries (id_country)
);

insert into countries (name) 
values
('Colombia'), ('España'), ('United State');
select * from countries;

insert into users (id_country, email, name)
values
(2, 'tito@gmail.com', 'Tito'), (3, 'carla1@hot.com', 'Carla');
select * from users;

--Delete:
delete from users where email = 'carla1@hot.com';

--Update:
update users set email = 'tito04@gmail.com', name = 'Angel' where id_user = 1;
select * from users;

--select:
select * from users inner join  countries on users.id_country = countries.id_country;

select u.id_user as id, u.email, u.name as fullname, c.name 
from users u inner join  countries c on u.id_country = c.id_country;
```

## 🏆 H-3
![](https://github.com/LuisDMM/Luis-D-Hack_SQL/blob/main/Screenshot/Hack_3.png)

-----------------
⚡ script
```sh
create table countries (
  id_country serial primary key,
  name varchar(50) not null
);

create table priorities (
  id_priority serial primary key,
  type_name varchar(200) not null
);

create table contact_request (
  id_email serial primary key,
  id_country int not null,
  id_priority int not null,
  name varchar(100) not null,
  detail text not null,
  physical_address text not null,
  foreign key (id_country) references countries (id_country),
  foreign key (id_priority) references priorities (id_priority)
);
```

## 🏆 H-4
![](https://github.com/LuisDMM/Luis-D-Hack_SQL/blob/main/Screenshot/Hack_4.png)

-----------------
⚡ script
```sh
create table countries (
  id_country serial primary key,
  name varchar(50) not null
);

create table priorities (
  id_priority serial primary key,
  type_name varchar(200) not null
);

create table contact_request (
  id_email varchar(100) primary key,
  id_country int not null,
  id_priority int not null,
  name varchar(100) not null,
  detail text not null,
  physical_address text not null,
  foreign key (id_country) references countries (id_country),
  foreign key (id_priority) references priorities (id_priority)
);

--Records in countries:
insert into countries(name) 
values
('Portugal'), ('España'), ('Chile'), ('Puerto Rico'), ('Suecia');
select * from countries;

--Records in priorities:
insert into priorities(type_name)
values
('Alta'), ('Media'), ('Baja');
select * from priorities;

--Records in contact_request:
insert into contact_request(id_email, id_country, id_priority, name, detail, physical_address)
values
('recursos@out.com', 1, 1, 'Juan', 'viaje', 'Chacao'), 
('mividabella@email.com', 2, 2, 'Kreixy', 'Viaje espiritual', 'Falcon'),
('fire_and_ice@gmail.com', 3, 3, 'Jhon', 'Trabajo', 'Poniente');
select * from contact_request;

--Delete:
delete from contact_request where id_email = 'recursos@out.com';

--Update:
update contact_request set name = 'Dany', detail = 'reclamo', physical_address = 'westeros' where id_email = 'fire_and_ice@gmail.com';
select * from contact_request;
```

## 🏆 H-5
![](https://github.com/LuisDMM/Luis-D-Hack_SQL/blob/main/Screenshot/Hack_5.png)

-----------------
⚡ script
```sh
create table countries(
  id_country serial primary key,
  name varchar(200) not null
); 

create table roles(
  id_role serial primary key,
  name varchar(200) not null
);

create table customers(
  email varchar(100) primary key,
  id_country int not null,
  id_role int not null,
  name varchar(200) not null,
  age integer not null,
  password varchar(20) not null,
  physical_address text not null,
  foreign key (id_country) references countries (id_country),
  foreign key (id_role) references roles (id_role)
);

create table discounts(
  id_discount serial primary key,
  status text not null,
  percentage int not null
);

create table offers(
  id_offer serial primary key,
  status text not null
);

create table taxes(
  id_tax serial primary key,
  percentage int not null
);

create table products(
  id_product serial primary key,
  id_discount int not null,
  id_offer int not null,
  id_tax int not null,
  name varchar(100) not null,
  details text not null,
  minimum_stock varchar(200) not null,
  maximum_stock varchar(200) not null,
  current_stock varchar(200) not null,
  price float not null,
  price_with_tax float not null,
  foreign key (id_discount) references discounts (id_discount),
  foreign key (id_offer) references offers (id_offer),
  foreign key (id_tax) references taxes (id_tax)
);

create table products_customers(
  id_product int not null,
  email varchar(100) not null,
  foreign key (id_product) references products (id_product),
  foreign key (email) references customers (email),
  primary key (id_product, email)
);

create table payments(
  id_payment serial primary key,
  type text not null
);

create table invoice_status(
  id_invoice_status serial primary key,
  status text not null
);

create table invoice(
  id_invoice serial primary key,
  email varchar (100) not null,
  id_payment int not null,
  id_invoice_status int not null,
  fecha date not null,
  total_to_pay float not null,
  foreign key (email) references customers (email),
  foreign key (id_payment) references payments (id_payment),
  foreign key (id_invoice_status) references invoice_status (id_invoice_status)
);

create table orders(
  id_order serial primary key,
  id_invoice int not null,
  id_product int not null,
  details text not null,
  amount varchar (100) not null,
  price float not null,
  foreign key (id_product) references products (id_product),
  foreign key (id_invoice) references invoice (id_invoice)
);
```

## 🏆 H-6
![](https://github.com/LuisDMM/Luis-D-Hack_SQL/blob/main/Screenshot/Hack_6.png)

-----------------
⚡ script
```sh
create table countries(
  id_country serial primary key,
  name varchar(200) not null
); 

create table roles(
  id_role serial primary key,
  name varchar(200) not null
);

create table customers(
  email varchar(100) primary key,
  id_country int not null,
  id_role int not null,
  name varchar(200) not null,
  age integer not null,
  password varchar(20) not null,
  physical_address text not null,
  foreign key (id_country) references countries (id_country),
  foreign key (id_role) references roles (id_role)
);

create table discounts(
  id_discount serial primary key,
  status text not null,
  percentage int not null
);

create table offers(
  id_offer serial primary key,
  status text not null
);

create table taxes(
  id_tax serial primary key,
  percentage int not null
);

create table products(
  id_product serial primary key,
  id_discount int not null,
  id_offer int not null,
  id_tax int not null,
  name varchar(100) not null,
  details text not null,
  minimum_stock varchar(200) not null,
  maximum_stock varchar(200) not null,
  current_stock varchar(200) not null,
  price float not null,
  price_with_tax float not null,
  foreign key (id_discount) references discounts (id_discount),
  foreign key (id_offer) references offers (id_offer),
  foreign key (id_tax) references taxes (id_tax)
);

create table products_customers(
  id_product int not null,
  email varchar(100) not null,
  foreign key (id_product) references products (id_product),
  foreign key (email) references customers (email),
  primary key (id_product, email)
);

create table payments(
  id_payment serial primary key,
  type text not null
);

create table invoice_status(
  id_invoice_status serial primary key,
  status text not null
);

create table invoice(
  id_invoice serial primary key,
  email varchar (100) not null,
  id_payment int not null,
  id_invoice_status int not null,
  fecha date not null,
  total_to_pay float not null,
  foreign key (email) references customers (email),
  foreign key (id_payment) references payments (id_payment),
  foreign key (id_invoice_status) references invoice_status (id_invoice_status)
);

create table orders(
  id_order serial primary key,
  id_invoice int not null,
  id_product int not null,
  details text not null,
  amount varchar (100) not null,
  price float not null,
  foreign key (id_product) references products (id_product),
  foreign key (id_invoice) references invoice (id_invoice)
);

--Records in countries:
insert into countries (id_country, name) values (1, 'Mexico'), (2, 'Salvador'), (3, 'Venezuela');
select * from countries;

--Records in roles:
insert into roles(id_role, name) values (1, 'Comprador'), (2, 'Influencer'), (3, 'Entrevistador');
select * from roles;

--Records in customers:
insert into customers(email, id_country, id_role, name, age, password, physical_address)
values
('chanchito_feliz@email.com', 1, 1, 'Felix', 30, 'chanchito1', 'Cancún'),
('chorizo92@email.com', 2, 2, 'Fernan', 25, 'carajo123', 'Salvador de Bahía'),
('Simon.15@email.com', 3, 3, 'Simon', 38, 'Arepita.feliz', 'Altamira');
select * from customers;

--Records in discounts:
insert into discounts(id_discount, status, percentage) 
values (1, 'activo', 10), (2, 'activo', 25), (3, 'inactivo', 20);
select * from discounts;

--Records in offers:
insert into offers(id_offer, status) values (1, 'activo'), (2, 'activo'), (3, 'inactivo');

--Records in taxes:
insert into taxes(id_tax, percentage) values (1, 5), (2, 10), (3, 35);

--Records in products:
insert into products (id_product, id_discount, id_offer, id_tax, name, details, minimum_stock, maximum_stock, current_stock, price, price_with_tax)
values
(1, 1, 1, 1, 'Producto 1', 'Detalles del producto 1', 10, 100, 50, 50.00, 52.50),
(2, 2, 2, 2, 'Producto 2', 'Detalles del producto 2', 5, 50, 20, 30.00, 33.00),
(3, 3, 3, 3, 'Producto 3', 'Detalles del producto 3', 20, 200, 150, 125.00, 168.75);
select * from products;

--Records in products_customers:
insert into products_customers(id_product, email) 
values
(1, 'chanchito_feliz@email.com'), (2, 'chorizo92@email.com'), (3, 'Simon.15@email.com');
select * from products_customers;

--Records in payments:
insert into payments(id_payment, type) values (1, 'Bitcoin'), (2, 'Efectivo'), (3, 'Tarjeta');
select * from payments;

--Records in invoice_status:
insert into invoice_status(id_invoice_status, status) values (1, 'activo'), (2, 'activo'), (3, 'inactivo');
select * from invoice_status;

--Records in invoice:
insert into invoice (id_invoice, email, id_payment, id_invoice_status, fecha, total_to_pay)
values 
(1, 'chanchito_feliz@email.com', 1, 1, '2024-03-15', 52.50),
(2, 'chorizo92@email.com', 2, 2, '2024-02-12', 33.00),
(3, 'Simon.15@email.com', 3, 3, '2024-04-01', 168.75);
select * from invoice;

--Records in orders:
insert into orders(id_order, id_invoice, id_product, details, amount, price)
values
(1, 1, 1, 'Detalles 1', '1 caja sellada', 52.50),
(2, 2, 2, 'Detalles 2', '10 paquetes', 33.00),
(3, 3, 3, 'Detalles 3', '3 cajas', 168.75);
select * from orders;

--Delete:
delete from orders where id_invoice = 3;
delete from invoice where email = 'Simon.15@email.com';
delete from products_customers where email = 'Simon.15@email.com';
delete from customers where email = 'Simon.15@email.com';
select * from customers;

--Update
update customers set name = 'Fernado', age = 26, password = 'Gaming-life', physical_address = 'La Libertad' where email = 'chorizo92@email.com';
select * from customers;

update taxes set percentage = 8 where id_tax = 1;
update taxes set percentage = 12 where id_tax = 2;
update taxes set percentage = 30 where id_tax = 3;
select * from taxes;

update products set price = 52.00 where id_product = 1;
update products set price = 35.00 where id_product = 2;
update products set price = 150.00 where id_product = 3;
update products set price_with_tax = 56.16 where id_product = 1;
update products set price_with_tax = 39.2 where id_product = 2;
update products set price_with_tax = 195.00 where id_product = 3;
select * from products;

update invoice set total_to_pay = 56.16 where id_invoice = 1;
update invoice set total_to_pay = 39.2 where id_invoice = 2;
update invoice set total_to_pay = 195.00 where id_invoice = 3;
select * from invoice;

update orders set price = 56.16 where id_order = 1;
update orders set price = 39.2 where id_order = 2;
update orders set price = 195.00 where id_order = 3;
select * from orders;
```
