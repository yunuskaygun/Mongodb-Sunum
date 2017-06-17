# Mongodb-Sunum
## mongoDB Nedir
 - MongoDB, doküman tabanlı, C++ ile geliştirilen bir NoSql veritabanıdır. Veriler BinaryJson türünde dokümanlarda tutulur.
 - MongoDB’nin en önemli özelliği, ilişkisel modeli (relational model) kullanmamasıdır.
 - Tablo yoktur, tasarım yoktur, ilişki yoktur.
 - Windows, Linux, Mac, Solaris.
 - Açık kaynak kodlu
 - Dinamik veri yapısı
 - Hızlı okuma ve yazma
 - Büyük veri ile çalışabilme 
 
### mongoDB Database Design
Relational database kavramından farklı olarak artık mongoda nesne mantığında tasarım düşünmemiz gerekiyor ve mongodbde denormalize yapılarla çalışmaya alışmamız gerekiyor.
```
{
    name:Yunus,
    addresses : [
        { street: ‘Ümraniye’, city: ‘istanbul’ },
        { street: ‘kızılay’, city: ‘Ankara }
    ]
}
```

Genel Komutlar
```
use db_adi
show dbs        //Mevcut veritabanlarını göster
db.dropDatabase()        //Mevcut veritabanı sil
db.createCollection("pers")        //pers adında bir collection oluştur
db.pers.drop()        //pers collectionu sil
```


Verileri Sorgulamak
```
db.person.find()
db.person.find({"sicil":1234})
db.person.find({"maas":{$lte:4000}})
db.person.find({"ad":{$ne:"yunus kaygun"}})
db.person.find({$and:[{"maas":{$lt:4000}}, {"maas":{$gt:1000}}]})
db.person.find({$or:[{"sicil":"1234"},{"maas":{$gt:3000}}]})
db.person.find({}, {"sicil":1, "maas":1})
db.person.find().limit(2)
db.person.find().sort({"ad":1})
db.person.find().sort({"ad":-1})
```


Dokuman Ekleme (Insert İşlemi)
```
Var kayit = [{
        "sicil": 2345,
        "ad": "ayse okan",
        "maas": 3000
    },
    {
        "sicil": 1234,
        "ad": "mahmut sarı",
        "maas": 5000
    }];
db.person.insert(kayit)
```


Update ve Delete İşlemi
```
db.person.update({"ad":"mahmut sarı"} ,{$set:{‘maas':5500}})
db.person.remove({"sicil":"1234"})
db.person.remove("",0) //Tümünü Sil
```


### Slayttaki Diğer Konular:
- NO SQL (Not Only SQL) Nedir ?
- NO SQL Avantajları ve Dezavantajları Nelerdir
- İlişkisel Veri Modelleri ile Farkları Nelerdir ?
- Performans Karşılaştırmaları
- Hangi Projelerde Kullanılabilir ?
- Kimler Kullanıyor ?
- mongoDB Kurulumu
- Robomongo Kurulumu
- Servisi Çalıştırmak
- mongoDB Dokuman yapısı ve kodlama
- Verileri sorgulamak
- CRUD işlemleri
- Indexler
- Replica Set Kavramı Nedir?
- Sharding Kavramı Nedir ?
- C# ile mongoDB uygulaması

[Power Point Dosyasını İndir](https://github.com/yunuskaygun/Mongodb-Sunum/raw/master/mongoDB%20Sunum.pptx)
