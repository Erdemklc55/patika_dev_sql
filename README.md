## SQL Ödev 01 | WHERE ve Karşılaştırma & Mantıksal Operatörler 
 
<br>
 
1-) <strong>film </strong>tablosunda bulunan <strong>title</strong> ve <strong>description</strong> 
sütunlarındaki verileri sıralayınız.
 
```
 
SELECT title, description FROM film;
 
```

<br>

2-) <strong>film </strong> tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük <strong>ve  </strong> 75 ten küçük olma koşullarıyla sıralayınız.

```
 
select * from film where length <75 and length >60
 
```
3-) <strong>film </strong> tablosunda bulunan  tüm sütunlardaki verileri rental_rate 0.99 <strong>ve </strong> replacement_cost 12.99 <strong>veya </strong> 28.99 olma koşullarıyla sıralayınız.

```
 
select * from film where rental_rate = 0.99 and  replacement_cost = 12.99 or  replacement_cost = 28.99
 
```
4-) <strong>customer </strong> tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?

```
 
SELECT last_name FROM customer WHERE first_name = 'Mary'
 
```

5-) <strong>film </strong> tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

```
 
SELECT * FROM film WHERE length <= 50 AND NOT (rental_rate = 2.99 OR rental_rate = 4.99)
 
```

