# SafePHP
A Simple PHP FrameWork.

# Projeye dahil etmek
```php
<?php include("safephp.php"); ?>
```

# Veri tabanına bağlanmak
- Bağlantı kurmak istediğiniz dosyanın üstüne değişkenleri tanımlayın.
```php
<?php
 $sunucu = "localhost";
 $kullanici = "root";
 $parola = "";
 $veritabani = "";
 ?>
```

# Bir tabloya veri eklemek için

```php
 <?php
 dEkle(tablo, bilgiler);
 ?>
```
```php
 <?php
 dEkle("kisiler", array(
 "ad" => "Alper",
 "soyad" => "Dursun",
 "mail" => "dursunalper1@gmail.com"
 ));
 ?>
```

# Bir tablodan veri silmek için
- Birinci veri silme yolu

```php
 <?php
 Sil(tablo, kriter);
 ?>
```
```php
 <?php
 Sil("kisiler", "id=5");
 Sil("kisiler", "id=5 AND ad="Alper" OR soyad="Dursun"");
 ?>
```

- İkinci veri silme yolu

```php
 <?php
 idSil(tablo, id değeri);
 ?>
```
```php
 <?php
 idSil("kisiler", "5");
 ?>
```

# Bir tabloda veri güncellemek için

```php
 <?php
 dGuncelle(tablo, bilgi, kriter);
 ?>
```
```php
 <?php
 dGuncelle("kisiler", array(
 "ad" => "Alper",
 "soyad" => "Dursun",
 "mail" => "dursunalper1@gmail.com"
 ), "id<10 AND id>5");
 ?>
```

# Manüel sorgu oluşturma

```php
 <?php
 Sorgu(SQL sorgusu);
 ?>
```
```php
 <?php
 Sorgu("SELECT * FROM kisiler WHERE id=5");
 ?>
```

# Form değişkenleri

- Get ve Post metodu
```php
 <?php
 Get(değişken);
 
 //Get ile gelen değişkeni okur
 echo get("adi");
 Getisset(değişken);
 
 //Get ile gelen değişken tanımlımı bakar, tanımlı ise 1 değilse 0 döner
 if(getisset("adi")){
 echo "Adı isimli değişken get geldi";
 }
 Post(değişken);
 
 //Post ile gelen değişkeni okur. Eğer tanımlıysa tanımı değilse boş döner
 echo post("adi");
 Postisset(değişken);
 
 //Post ile gelen değişken tanımlımı bakar, tanımlı ise 1 değilse 0 döner
 if(postisset("adi")){
 echo "Adı isimli değişken get geldi";
 }
 Veri(değer, tür);
 
 //SQL injection korumalı dosya yükleme
 Yukle(dosya, url, isim, tur, resim=1024);
 
 Yukle("dosya", "dosyalar/");
 
 Yukle("resim", "resimler/jpg/", "portre", "resim", 768);
 ?>
```

# SafePHP de işlevlerin büyük küçük harf duyarı yoktur.
