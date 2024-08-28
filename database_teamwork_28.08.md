```sql
CREATE TABLE products

(id INTEGER PRIMARY KEY AUTOINCREMENT, 
 
ProductName varchar,
Quantity int,
Price float);
```
```sql
INSERT INTO products (ProductName, quantity, price) 
VALUES 
('Chocolate','10','2.99'),
('Cookies','100','5.00'),
('Apples','25','1.50'),
('Coca Cola','50','1.99');
```
```sql
Select * from products
```

```sql
CREATE TABLE auto

(id INTEGER PRIMARY KEY AUTOINCREMENT, 
 
Brand varchar,
Model varchar,
ModelYear int,
BodyType varchar);
```
```sql
INSERT INTO auto (Brand, Model, ModelYear, BodyType) 
VALUES 
('BMW','X3','2014','5-doors, suv/crossover'),
('Audi','S7 Sportback','2012', '5-doors, hatchback'),
('Volvo','XC60','2008', '5-doors, suv/crossover'),
('Bentley','Azure','1997', '2-doors, convertible');

```sql
Select * from auto
```

```sql
CREATE TABLE flowers

(id INTEGER PRIMARY KEY AUTOINCREMENT, 
 
Name varchar,
PlantType varchar,
Zone varchar,
Maintenance varchar);
```
```sql
INSERT INTO flowers (Name, PlantType, Zone, Maintenance) 
VALUES 
('Violet','Annuals, Perennials, Shrubs','3-9','low'),
('Zinnia','Annuals, Perennials, Shrubs', '2-11', 'low'),
('Dahlia','Bulbs, Perennials','3-11', 'medium'),
('Rose','Climbers, Roses, Shrubs','2-10', 'medium'),
('Anemone','Perennials','4-11', 'low');
```
```sql
Select * from flowers
```
