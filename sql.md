Первое задание второй части

scooter_rent=# 

select c.login, count(*) from "Couriers" c join "Orders" o on o."courierId"=c.id where o."inDelivery"='t' group by c.login;

--------------------------------------------- 
 Результат:
 login | count
-------+-------
 nina  |     4
(1 row)



Второе задание:

scooter_rent=# 

select o.track, case when o.finished='t' then 2 when o.cancelled='t' then -1 when o."inDelivery"='t' then 1 else 0 end from "Orders" o;
-----------------------


Результат:

 track  | case
--------+------
 844247 |    0
 249552 |    0
  42329 |    0
 668184 |    0
 206902 |    1
 206902 |    1
 268404 |    1
 268404 |    1
 154479 |    0
 132451 |    0
(10 rows)
