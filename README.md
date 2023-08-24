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

## SQL Ödev 02 |BETWEEN - AND Yapısı ve In Operatörü
 
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
 
SELECT rental_rate,replacement_cost FROM film
WHERE rental_rate IN (0.99, 2.99, 4.99) AND replacement_cost in (12.99, 15.99, 28.99)
 
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
 
SELECT * FROM film WHERE title like 'C%' AND length>90  AND rental_rate = 2.99
 
```

## SQL Ödev 04 |DISTINCT ve COUNT
 
<br>
 
1-) <strong>film </strong>tablosunda bulunan <strong>replacement_cost  </strong> sütununda bulunan birbirinden farklı değerleri sıralayınız.
 
```
 
SELECT DISTINCT replacement_cost  FROM film 
 
```

<br>

2-) <strong>film </strong>tablosunda bulunan <strong>replacement_cost  </strong> sütununda birbirinden farklı kaç tane veri vardır?
 
```
 
SELECT COUNT (DISTINCT replacement_cost) FROM film 
 
```

<br>

3-) <strong>film </strong>tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?
 
```
 
SELECT COUNT(*) FROM film WHERE title LIKE 'T%' AND rating = 'G'
 
```

<br>

4-) <strong>country </strong>tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?
 
```
 
SELECT COUNT (country) FROM country WHERE country like '_____''
 
```

<br>

5-) <strong>city </strong>tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?
 
```
 
SELECT COUNT (DISTINCT city) FROM city WHERE city ILIKE '%r'
 
```
## SQL Ödev 05 |LIMIT OFFSET ve ORDER BY
 
<br>
 
1-) <strong>film </strong>tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.
 
```
 
SELECT title, length FROM film WHERE title LIKE '%n' ORDER BY length DESC LIMIT 5;
 
```
<br>
 
2-) <strong>film </strong>tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.
 
```
 
SELECT title FROM film WHERE title LIKE '%n' ORDER BY length DESC OFFSET 2 LIMIT 5 ;
 
```
<br>
 
3-) <strong>customer </strong>tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.
 
```
 
SELECT * FROM customer WHERE store_id = 1 ORDER by last_name DESC LIMIT 4;

```
## SQL Ödev 06 |AGGREGATE Fonksiyonlar
 
<br>
 
1-) <strong>film </strong>tablosunda bulunan <strong>rental_rate </strong> sütunundaki değerlerin ortalaması nedir?

```

SELECT ROUND(AVG(rental_rate), 3) FROM film
 
```
<br>
 
2-) <strong>film </strong>tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?

```

SELECT COUNT (*) FROM film WHERE title LIKE 'C%'
 
```
<br>

3-) <strong>film </strong>tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

```

SELECT MAX (length) FROM film WHERE rental_rate = 0.99
 
```
<br>

4-) <strong>film </strong>tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?

```

SELECT COUNT (DISTINCT replacement_cost) FROM film WHERE length > 150
 
```
<br>

## SQL Ödev 07 |GROUP BY VE HAVING 
 
<br>
 
1-) <strong>film </strong>tablosunda bulunan filmleri <strong>rating </strong>değerlerine göre gruplayınız.
 
```
 
SELECT rating from film GROUP BY rating
 
```
<br>
 
2-) <strong>film </strong>tablosunda bulunan filmleri  <strong>replacement_cost </strong> sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık 
gelen film sayısını sıralayınız.
 
```
 
SELECT replacement_cost, COUNT (*) FROM film GROUP BY replacement_cost HAVING COUNT (*) > 50
 
```
<br>
 
3-) <strong>customer </strong> tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?
 
```
 
SELECT store_id, COUNT(*) FROM customer GROUP BY store_id
 
```
<br>
 
4-) <strong>city </strong> tablosunda bulunan şehir verilerini  <strong> country_id </strong>sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id 
bilgisini ve şehir sayısını paylaşınız.

```
 
SELECT country_id, COUNT (city) FROM city
GROUP BY country_id
ORDER BY COUNT(city)  DESC
LIMIT 1
 
```
## SQL Ödev 08 |Tablo Oluşturma, Veri Ekleme, Silme ve Güncelleme
 
<br>
 
1-) <strong>test  </strong>veritabanınızda <strong> employee </strong>isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.

```

CREATE TABLE employee(
    id INTEGER PRIMARY KEY GENERATED ALWAYS AS IDENTITY,
    name VARCHAR(50) NOT NULL,
	email VARCHAR(100),
    birthday DATE
    
);
 
```
<br>
 
2-) Oluşturduğumuz <strong>employee </strong> tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim

```

insert into employee (name, email, birthday) values ('Jason', 'jpegg0@alibaba.com', '21/11/2022');
insert into employee (name, email, birthday) values ('Corly', 'ctolworth1@dell.com', '24/06/2023');
insert into employee (name, email, birthday) values ('Astrid', 'aworrell2@un.org', null);
insert into employee (name, email, birthday) values ('Rosette', 'rlayne3@topsy.com', '06/03/2023');
insert into employee (name, email, birthday) values ('Marcelo', 'mericssen4@ibm.com', null);
insert into employee (name, email, birthday) values ('Devan', 'ddemorena5@google.com.br', null);
insert into employee (name, email, birthday) values ('Padgett', 'pkeir6@ucsd.edu', '28/05/2023');
insert into employee (name, email, birthday) values ('Homer', 'hmartinson7@cpanel.net', null);
insert into employee (name, email, birthday) values ('Desiri', 'daxcel8@altervista.org', '10/05/2023');
insert into employee (name, email, birthday) values ('Eba', 'eguyon9@discovery.com', '09/08/2023');
insert into employee (name, email, birthday) values ('Cornelle', 'cgreschkea@dedecms.com', '29/08/2022');
insert into employee (name, email, birthday) values ('Andie', 'adudeneyb@geocities.com', '30/08/2022');
insert into employee (name, email, birthday) values ('Hasty', 'hlewsleyc@google.ru', '04/04/2023');
insert into employee (name, email, birthday) values ('Steffane', 'srobotthamd@bizjournals.com', null);
insert into employee (name, email, birthday) values ('Justinian', 'jtowlsone@squidoo.com', null);
insert into employee (name, email, birthday) values ('Vere', 'vsavatierf@goo.ne.jp', '09/03/2023');
insert into employee (name, email, birthday) values ('Ora', 'ostantong@prnewswire.com', '27/05/2023');
insert into employee (name, email, birthday) values ('Shermie', 'shauseh@cam.ac.uk', null);
insert into employee (name, email, birthday) values ('Marjy', 'mnormadelli@github.com', '13/12/2022');
insert into employee (name, email, birthday) values ('Gunilla', 'gvellj@netvibes.com', null);
insert into employee (name, email, birthday) values ('Carol', null, '31/10/2022');
insert into employee (name, email, birthday) values ('Marje', 'mbaddileyl@diigo.com', '05/03/2023');
insert into employee (name, email, birthday) values ('Dee dee', 'decclestonm@tmall.com', null);
insert into employee (name, email, birthday) values ('Hale', 'hedlynn@bravesites.com', '19/07/2023');
insert into employee (name, email, birthday) values ('Grantham', 'gderuggeroo@digg.com', '16/04/2023');
insert into employee (name, email, birthday) values ('Ilaire', 'itoothillp@1688.com', null);
insert into employee (name, email, birthday) values ('Regan', 'rbernardotteq@de.vu', '22/09/2022');
insert into employee (name, email, birthday) values ('Godart', 'gmccowanr@biblegateway.com', '07/12/2022');
insert into employee (name, email, birthday) values ('Marilee', 'mdanielis@bigcartel.com', '13/04/2023');
insert into employee (name, email, birthday) values ('Kaspar', 'kbemwellt@redcross.org', '06/04/2023');
insert into employee (name, email, birthday) values ('Haskel', 'hthorburnu@yahoo.co.jp', '19/12/2022');
insert into employee (name, email, birthday) values ('Ferguson', 'fsnarv@mysql.com', null);
insert into employee (name, email, birthday) values ('Stacy', 'soaksw@miibeian.gov.cn', null);
insert into employee (name, email, birthday) values ('Johnath', 'jcoggerx@xing.com', '20/09/2022');
insert into employee (name, email, birthday) values ('Cristen', 'celgery@photobucket.com', '16/09/2022');
insert into employee (name, email, birthday) values ('Tally', 'tgillivriez@weather.com', null);
insert into employee (name, email, birthday) values ('Corabelle', 'ccowin10@163.com', '16/09/2022');
insert into employee (name, email, birthday) values ('Mara', 'mferson11@jalbum.net', '12/08/2023');
insert into employee (name, email, birthday) values ('Care', 'ckemer12@topsy.com', '07/07/2023');
insert into employee (name, email, birthday) values ('Solly', 'scourcey13@usgs.gov', '08/03/2023');
insert into employee (name, email, birthday) values ('Leyla', 'lcrawforth14@washington.edu', '15/01/2023');
insert into employee (name, email, birthday) values ('Mikael', 'mgatward15@google.cn', '27/05/2023');
insert into employee (name, email, birthday) values ('Kerk', 'kknutton16@biblegateway.com', null);
insert into employee (name, email, birthday) values ('Florence', 'fkittredge17@so-net.ne.jp', null);
insert into employee (name, email, birthday) values ('Rianon', 'rbirk18@quantcast.com', '23/03/2023');
insert into employee (name, email, birthday) values ('Angelia', 'akibbey19@hud.gov', '21/07/2023');
insert into employee (name, email, birthday) values ('Lorelei', 'lselburn1a@toplist.cz', null);
insert into employee (name, email, birthday) values ('Florence', 'fphython1b@istockphoto.com', '29/06/2023');
insert into employee (name, email, birthday) values ('Caz', 'cwestnage1c@patch.com', '14/02/2023');
insert into employee (name, email, birthday) values ('Verene', 'vheinsius1d@apple.com', '21/12/2022');

```
<br>

3-) Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.

```

UPDATE employee SET name = 'ali ' WHERE email ='jpegg0@alibaba.com'

UPDATE employee SET email = ' asdcxaklc@gmail.com ' WHERE name = 'Corly'

UPDATE employee SET birthday = '2021-02-10' WHERE email = 'aworrell2@un.org'

UPDATE employee SET name ='GÜL' WHERE birthday = '06/03/2023'

UPDATE employee SET name = 'Abdullah' WHERE birthday ='28/05/2023'
 
```
<br>

4-) Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.

```

DELETE FROM employee WHERE name = 'Tally';

DELETE FROM employee WHERE id = 42;

DELETE FROM employee WHERE email ='gderuggeroo@digg.com'

DELETE FROM employee WHERE id = 7;

DELETE FROM employee WHERE email ='scourcey13@usgs.gov'
 
```
<br>

## SQL Ödev 09 | INNER JOIN ile Tablo Birleştirme
 
<br>
 
1-) <strong>city  </strong> tablosu ile <strong>country </strong> tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

```

SELECT city, country FROM city JOIN country ON city.country_id = country.country_id;
 
```

<br>
 
2-) <strong>customer  </strong> tablosu ile <strong>payment </strong> tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz 
INNER JOIN sorgusunu yazınız.

```

SELECT customer.first_name, customer.last_name, payment.payment_id 
FROM customer INNER JOIN payment 
ON customer.customer_id = payment.customer_id;
 
```
<br>
 
3-) <strong>customer  </strong> tablosu ile <strong>rental </strong> tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

```

SELECT rental.rental_id, customer.first_name, customer.last_name
FROM rental INNER JOIN customer
ON rental.customer_id = customer.customer_id;
 
```

<br>

## SQL Ödev 10 |LEFT JOIN, RIGHT JOIN, FULL JOIN ile Tablo Birleştirme
 
<br>
 
1-) <strong>city  </strong> tablosu ile <strong>country </strong> tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.

```

SELECT city, country from city LEFT JOIN country ON city.country_id = country.country_id;
 
```

<br>

2-) <strong>customer  </strong> tablosu ile <strong>payment </strong> tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz 
RIGHT JOIN sorgusunu yazınız.

```

SELECT payment.payment_id, customer.first_name, customer.last_name
FROM customer RIGHT JOIN payment
ON customer.customer_id = payment.customer_id;
 
```

<br>

3-) <strong>customer  </strong> tablosu ile <strong>rental </strong>     tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz 
FULL JOIN sorgusunu yazınız.

```

SELECT rental.rental_id, customer.first_name, customer.last_name
FROM customer FULL JOIN rental
ON customer.customer_id = rental.customer_id;
 
```

<br>

## SQL Ödev 11 |UNION INTERSECT ve EXCEPT
 
<br>
 
1-) <strong>actor  </strong> ve <strong>customer </strong> tablolarında bulunan <strong>first_name </strong> sütunları için tüm verileri sıralayalım.

```

(
SELECT first_name FROM actor
)
UNION
(
SELECT first_name FROM customer
)
 
```

<br>

2-) <strong>actor  </strong> ve <strong>customer </strong> tablolarında bulunan <strong>first_name </strong> sütunları için kesişen verileri sıralayalım.

```

(
SELECT first_name FROM actor
)
INTERSECT
(
SELECT first_name FROM customer
)
 
```

<br>

3-) <strong>actor  </strong> ve <strong>customer </strong> tablolarında bulunan <strong>first_name </strong> sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.

```
(
SELECT first_name FROM actor
)
EXCEPT
(
SELECT first_name FROM customer
)
 
```

<br>

4-) İlk 3 sorguyu tekrar eden veriler için de yapalım.

```
(
SELECT first_name FROM actor
)
UNION ALL
(
SELECT first_name FROM customer
);

(
SELECT first_name FROM actor
)
INTERSECT ALL
(
SELECT first_name FROM custome
);

(
SELECT first_name FROM actor
)
EXCEPT ALL
(
SELECT first_name FROM customer
);
 
```

<br>

## SQL Ödev 11 |UNION INTERSECT ve EXCEPT
 
<br>
 
1-) <strong>film  </strong> tablosunda film uzunluğu <strong> length </strong>  sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?

```

SELECT COUNT (*) FROM film WHERE length > (SELECT AVG(length) FROM film);
 
```

<br>

2-) <strong>film  </strong> tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?

```

SELECT COUNT(*), rental_rate FROM film GROUP BY rental_rate ORDER BY rental_rate DESC  LIMIT 1
 
```

<br>

3-) <strong>film  </strong> tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.

```

SELECT * FROM film WHERE rental_rate =(SELECT MIN( rental_rate) FROM film ) AND replacement_cost= (SELECT MIN (replacement_cost) FROM film)
 
```

<br>

4-) <strong>payment  </strong> tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.

```

SELECT customer_id, count(*) FROM payment GROUP BY customer_id ORDER BY customer_id  asc
 
```

<br>











