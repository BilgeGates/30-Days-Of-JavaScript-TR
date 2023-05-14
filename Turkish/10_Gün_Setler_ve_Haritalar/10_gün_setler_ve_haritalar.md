<div align="center">
<h1> 30 Günde JavaScript: Setler ve Haritalar</h1>
<a class="header-badge" target="_blank" href="https://twitter.com/developerkhatai">
<img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/developerkhatai?style=social">
</a><br>

<sub>Yazar:
<a href="https://github.com/BilgeGates">Khatai Huseynzade</a><br>
<small> Mayıs, 2023</small>
</sub>

</div>

[<< Gün 9](..09_Gün_Üst_Düzey_Fonksiyonlar/09_gün_üst_düzey_fonksiyonlar.md) | [>> Gün 11 ](..11_Gün_Yıkıcılar_ve_Yapıcılar/11_gün_yıkıcılar_ve_yapıcılar.md)

- [📔 Gün 10](#📔Gün-10)
  - [Set](#Set)
    - [Boş bir set oluşturma](#Boş-Bir-Set-Oluşturma)
    - [Diziden set oluşturma](#diziden-set-oluşturma)
    - [Bir sete eleman ekleme](#bir-sete-eleman-ekleme)
    - [Bir elemanı setden silme](#bir-elemanı-setden-silme)
    - [Setdeki bir elemanı kontrol etme](#setdeki-bir-elemanı-kontrol-etme)
    - [Seti temizleme](#seti-temizleme)
    - [Setlerin birleşimi](#setlerin-birleşimi)
    - [Setlerin kesişimi](#setlerin-kesişimi)
    - [setlerin farkı](#setlerin-farkı)
  - [Map](#map)
    - [Boş map oluşturma](#boş-map-oluşturma)
    - [Bir diziden map oluşturma](#bir-diziden-map-oluşturma)
    - [Mape değerler ekleme](#mape-değerler-ekleme)
    - [Mapten değerler alma](#mapten-değerler-alma)
    - [Map içindeki anahtarları kontrol etme](#map-içindeki-anahtarları-kontrol-etme)
  - [💻 Gün 10: Egzersizleri](#💻Gün-10-Egzersizleri)
    - [Egzersiz: Seviye 1](#egzersiz-seviye-1)
    - [Egzersiz: Seviye 2](#egzersiz-seviye-2)
    - [Egzersiz: Seviye 3](#egzersiz-seviye-3)

# 📔 Gün 10

## Set

Set, elemanlar topluluğudur. Set yalnızca benzersiz öğeler içerebilir. Aşağıdaki bölümde bir setin nasıl oluşturulacağını görelim.

### Boş bir set oluşturma

```js
const companies = new Set();
console.log(companies);
```

```sh
Set(0) {}
```

### Diziden set oluşturma

```js
const languages = [
  "English",
  "Finnish",
  "English",
  "French",
  "Spanish",
  "English",
  "French",
];

const setOfLanguages = new Set(languages);
console.log(setOfLanguages);
```

```sh
Set(4) {English, Finnish, French, Spanish}
```

Set iterable bir nesnedir ve her öğeye iterable işlemi uygulanabilir

```js
const languages = [
  "English",
  "Finnish",
  "English",
  "French",
  "Spanish",
  "English",
  "French",
];

const setOfLanguages = new Set(languages);

for (const language of setOfLanguages) {
  console.log(language);
}
```

```sh
  English
  Finnish
  French
  Spanish
```

### Bir sete eleman ekleme

```js
const companies = new Set()  boş bir set oluşturuyoruz
console.log(companies.size)  0

companies.add('Google')  set'e eleman ekliyoruz
companies.add('Facebook')
companies.add('Amazon')
companies.add('Oracle')
companies.add('Microsoft')
console.log(companies.size)  set'in içinde 5 eleman var
console.log(companies)
```

```sh
Set(5) {Google, Facebook, Amazon, Oracle, Microsoft}
```

Bir set'e eleman eklemek için döngülerde kullanabiliriz.

```js
const companies = ["Google", "Facebook", "Amazon", "Oracle", "Microsoft"];
setOfCompanies = new Set();
for (const company of companies) {
  setOfCompanies.add(company);
}
```

```sh
Set(5) {Google, Facebook, Amazon, Oracle, Microsoft}

```

### Bir elemanı setden silme

Set'den delete methodunu kullanrak bir eleman silebiliriz.

```js
console.log(companies.delete('Google'))
console.log(companies.size)  Set'de 4 eleman kaldı
```

### Setdeki bir elemanı kontrol etme

Has methodu bir set'de belirli bir elemanı olup olmadığını kontrol eder true veya false döndürür.

```js
console.log(companies.has('Apple'))  false
console.log(companies.has('Facebook'))  true
```

### Seti temizleme

Clear methodu set'deki bütün elemanları temizler.

```js
companies.clear();
console.log(companies);
```

```sh
Set(0) {}
```

Set'in nasıl kullanılacağını aşağıdaki örnekte görebilirsiniz.

```js
const languages = [
  'English',
  'Finnish',
  'English',
  'French',
  'Spanish',
  'English',
  'French',
]
const langSet = new Set(languages)
console.log(langSet)  Set(4) {English, Finnish, French, Spanish}
console.log(langSet.size)  4

const counts = []
const count = {}

for (const l of langSet) {
  const filteredLang = languages.filter((lng) = lng === l)
  console.log(filteredLang)  [English, English, English]
  counts.push({ lang l, count filteredLang.length })
}
console.log(counts)
```

```js
[
  { lang 'English', count 3 },
  { lang 'Finnish', count 1 },
  { lang 'French', count 2 },
  { lang 'Spanish', count 1 },
]
```

Set'in farklı bir kullanımı. Örneğin dizideki benzersiz öğeyi saymak için.

```js
const numbers = [5, 3, 2, 5, 5, 9, 4, 5];
const setOfNumbers = new Set(numbers);

console.log(setOfNumbers);
```

```sh
Set(5) {5, 3, 2, 9, 4}
```

### Setlerin birleşimi

iki set nesnesini birleştirmek yayılma operatörü kullanılarak elde edilebilir A ve B set'lerinin birleşimini (A U B) bulmak için aşağıdaki kodlara göz atın

```js
let a = [1, 2, 3, 4, 5];
let b = [3, 4, 5, 6];
let c = [...a, ...b];

let A = new Set(a);
let B = new Set(b);
let C = new Set(c);

console.log(C);
```

```sh
Set(6) {1, 2, 3, 4, 5,6}
```

### Setlerin kesişimi

iki set nesnesinin kesişimini bulmak için filter methodu kullanılması gerekir. A ve B setlerinin kesişimi (A ∩ B) bulmak için aşağıdaki kodlara göz atın

```js
let a = [1, 2, 3, 4, 5];
let b = [3, 4, 5, 6];

let A = new Set(a);
let B = new Set(b);

let c = a.filter((num = B.has(num)));
let C = new Set(c);

console.log(C);
```

```sh
Set(3) {3, 4, 5}
```

### Setlerin farkı

iki set nesnesinin farkını bulmak için filter methodu kullanılması gerekir. A ve B setlerinin farkını (A B) bulmak için aşağıdaki kodlara göz atın

```js
let a = [1, 2, 3, 4, 5];
let b = [3, 4, 5, 6];

let A = new Set(a);
let B = new Set(b);

let c = a.filter((num = !B.has(num)));
let C = new Set(c);

console.log(C);
```

```sh
Set(2) {1, 2}
```

## Map

### Boş map oluşturma

```js
const map = new Map();
console.log(map);
```

```sh
Map(0) {}
```

### Bir diziden map oluşturma

```js
countries = [
  ["Finland", "Helsinki"],
  ["Sweden", "Stockholm"],
  ["Norway", "Oslo"],
];
const map = new Map(countries);
console.log(map);
console.log(map.size);
```

```sh
Map(3) {Finland = Helsinki, Sweden = Stockholm, Norway = Oslo}
3
```

### Mape değerler ekleme

```js
const countriesMap = new Map()
console.log(countriesMap.size)  0
countriesMap.set('Finland', 'Helsinki')
countriesMap.set('Sweden', 'Stockholm')
countriesMap.set('Norway', 'Oslo')
console.log(countriesMap)
console.log(countriesMap.size)
```

```sh
Map(3) {Finland = Helsinki, Sweden = Stockholm, Norway = Oslo}
3
```

### Mapten değer alma

```js
console.log(countriesMap.get("Finland"));
```

```sh
Helsinki
```

### Map içindeki anahtarları kontrol etme

Eğer Map içinde bir anahtarın olup olmadığını kontrol etmek istiyorsak has methodunu kullanabiliriz bu method bize true veya false döndürür.

```js
console.log(countriesMap.has("Finland"));
```

```sh
true
```

Map içindeki bütün değerleri döngü kullanarak almak

```js
for (const country of countriesMap) {
  console.log(country);
}
```

```sh
(2) [Finland, Helsinki]
(2) [Sweden, Stockholm]
(2) [Norway, Oslo]
```

```js
for (const [country, city] of countriesMap) {
  console.log(country, city);
}
```

```sh
Finland Helsinki
Sweden Stockholm
Norway Oslo
```

🌕 Büyük bir ilerleme kateddiniz, durdurulamazsınız. Devam edin! 10.gün zorluklarını yeni tamamladınız ve mükemmeliğe giden yolda 10 adım öndesiniz. Şimdi beyniniz ve kaslarınız için bazı egzersizler yapın.

## 💻 Gün 10: Egzersizleri

### Egzersiz: Seviye 1

```js
const a = [4, 5, 8, 9];
const b = [3, 4, 5, 7];
const countries = ["Finland", "Sweden", "Norway"];
```

1.Boş bir set oluşturun
2.Döngü kullanarak 0 ile 10 aralığını içeren bir set oluşturun
3.Set içinden bir eleman silin
4.Set'i temizleyin
5.5 string eleman içeren bir set oluşturun (dizi ile oluşturulacak) 6. bir ülke map'ı oluşturun ve içindeki ülkelerin karakter sayısını girin

### Egzersiz: Seviye 2

1.A birleşim B'yi bulun
2.A kesişim B'yi bulun 3. A ile B'yi bul

### Egzersiz: Seviye 3

1.Ülkeler nesne dosyasında kaç tane dil var

2.En çok konuşulan 10 dili bulmak için ülke verilerini kullanın

```js
    Çıktınız böyle görünmelidir
   console.log(mostSpokenLanguages(countries, 10))
   [
     { English 91 },
     { French 45 },
     { Arabic 25 },
     { Spanish 24 },
     { Russian 9 },
     { Portuguese 9 },
     { Dutch 8 },
     { German 7 },
     { Chinese 5 },
     { Swahili 4 },
     { Serbian 4 }
   ]

   Çıktınız böyle görünmelidir
  console.log(mostSpokenLanguages(countries, 3))
  [
  {English91},
  {French45},
  {Arabic25}
  ]
```

🎉 TEBRİKLER ! 🎉

[<< Gün 9](..09_Gün_Üst_Düzey_Fonksiyonlar/09_gün_üst_düzey_fonksiyonlar.md) | [>> Gün 11 ](..11_Gün_Yıkıcılar_ve_Yapıcılar/11_gün_yıkıcılar_ve_yapıcılar.md)
