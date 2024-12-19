select * from customers;

select distinct city from customers;

select * from products where supplier_id=(
select supplier_id from suppliers where company_name='Tokyo Traders'
);

select * from products where supplier_id IN( select supplier_id from suppliers where country='USA');

select * from categories;

select * from products;

-- in (IN) komutu içindekiler
select * from products where category_id in (select category_id from categories where category_name='Condiments');

select * from employees;

--first name e göre sıralama yapmak için default unda asc dir ve a dan z ye sıralar yada küçükten büyüğe 1-2-3 diye sıralar
select * from employees
order by first_name asc; -- asc yazmasak bile defaultunda asc dir
-- desc yaparsak z den a ya sıralar yada 3-2-1 diye büyükten küçüğe
select * from employees
order by first_name desc;

select *from employees where birth_date>'1955-01-01' order by birth_date desc   ;

-- büyük küçük harf duyarlılığı vardır
select * from customers where contact_name like '%maria%';
-- büyük küçük harf duyarlılığı olmasını istemiyorsak ilike kullanırızz
select * from customers where contact_name ilike '%MARIA%' ;
-- %m% gibi bir ifade m harfini içereceğini söyler çünkü sağında ve solunda yüzde işareti vardır
-- m% gibi bir ifade ise m harfi ile başlayacak demektir
select * from customers where contact_name like '%m';
-- %m ise son harfi m olanları getirmek istediğimizde

select * from customers where contact_name ilike '__m%';
-- 3.sıradaki harfi m olanları getirmek için

select* from customers where contact_name ilike '%m__';
-- sondan 3.harfi m olanları getirmek için 









