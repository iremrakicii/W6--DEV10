# SQL JOIN Sorguları - README

Bu dosya, SQL veritabanı üzerinde JOIN işlemlerini gerçekleştiren üç farklı sorgunun açıklamasını içermektedir.

## Sorgular ve Açıklamaları

### 1. Soru
```sql
SELECT city.city, country.country FROM city
LEFT JOIN country ON city.country_id=country.country_id;
```
Açıklama: Bu sorguda, city ve country tabloları arasındaki ilişkiyi LEFT JOIN kullanarak sorguluyoruz. LEFT JOIN, sol tablodaki (city) tüm kayıtları döndürür ve sağ tablo (country) ile eşleşen kayıtlar varsa, bunları da ekler. Eğer sağ tabloda eşleşmeyen kayıtlar varsa, bu alanlar NULL olarak gösterilir. Bu sorgu sonucunda city ve country sütunlarını alırız.

### 2. Soru
```sql
SELECT payment.payment_id, customer.first_name, customer.last_name FROM customer
RIGHT JOIN payment ON customer.customer_id = payment.customer_id;
```
Açıklama: Bu sorguda customer ve payment tablolarını RIGHT JOIN ile birleştiriyoruz. RIGHT JOIN, sağ tablodaki (payment) tüm kayıtları döndürür ve sol tablo (customer) ile eşleşen kayıtlar varsa, bunları ekler. Sol tabloda eşleşmeyen kayıtlar için NULL döner. Bu sorgu, ödeme bilgilerini (payment_id) ve varsa müşterinin ad ve soyad bilgilerini döndürür.

### 3. Soru
```sql
SELECT rental.rental_id, customer.first_name, customer.last_name FROM rental
FULL JOIN customer ON rental.customer_id=customer.customer_id;
```
Açıklama: Bu sorguda rental ve customer tablolarını FULL JOIN ile birleştiriyoruz. FULL JOIN, hem sol tablo (rental) hem de sağ tablodaki (customer) tüm kayıtları döndürür. Eğer herhangi bir tablo diğer tablo ile eşleşmezse, ilgili sütunlar NULL olarak döner. Bu sorgu, kiralama bilgileri (rental_id) ile birlikte müşteri ad ve soyad bilgilerini içeren tüm kayıtları döndürür.
