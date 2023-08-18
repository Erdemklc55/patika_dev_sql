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
 
SELECT * FROM film WHERE length <75 AND length >60
 
```
3-) <strong>film </strong> tablosunda bulunan  tüm sütunlardaki verileri rental_rate 0.99 <strong>ve </strong> replacement_cost 12.99 <strong>veya </strong> 28.99 olma koşullarıyla sıralayınız.

```
 
SELECT * FROM film WHERE rental_rate = 0.99 AND  replacement_cost = 12.99 OR replacement_cost = 28.99
 
```
4-) <strong>customer </strong> tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?

```
 
SELECT last_name FROM customer WHERE first_name = 'Mary'
 
```

5-) <strong>film </strong> tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

```
 
SELECT * FROM film WHERE length <= 50 AND NOT (rental_rate = 2.99 OR rental_rate = 4.99)
 
```

## SQL Ödev 02 
 
<br>
 
1-) <strong>film </strong> tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)
 
```
 
SELECT * FROM film WHERE replacement_cost BETWEEN 12.99 AND 16.99
 
```
<br>
 
2-) <strong>actor </strong> tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)
 
```
 
SELECT first_name, last_name FROM actor WHERE first_name IN ('Penelope' , 'Nick' , 'Ed')
 
```
<br>
 
3-) <strong>film </strong> tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99  <strong>ve </strong> replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız.
( IN operatörünü kullanınız.)
 
```
 
SELECT rental_rate,replacement_cost FROM film WHERE rental_rate IN (0.99, 2.99, 4.99) AND replacement_cost in (12.99, 15.99, 28.99)
 
```
## SQL Ödev 03 |LIKE ve ILIKE 
 
<br>
 
1-) <strong>country </strong>tablosunda bulunan <strong>country </strong> sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.
 
```
 
SELECT * FROM country WHERE country LIKE 'A%a'
 
```
<br>
 
2-) <strong>country </strong>tablosunda bulunan <strong>country </strong> sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.
 
```
 
SELECT country FROM country WHERE country LIKE '_____n'
 
```
<br>
 
3-) <strong>film </strong>tablosunda bulunan <strong>title </strong>  sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.
 
```
 
SELECT title FROM film WHERE title ILIKE '%t%t%t%t'
 
```
<br>
 
4-) <strong>film </strong>tablosunda bulunan tüm sütunlardaki verilerden <strong>title </strong> 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.
 
```
 
SELECT * FROM film WHERE title like 'C%' AND length>90  and rental_rate = 2.99
 
```

