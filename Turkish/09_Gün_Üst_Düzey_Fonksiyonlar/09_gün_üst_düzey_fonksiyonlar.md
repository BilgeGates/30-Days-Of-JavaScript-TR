<div align="center">
<h1> 30 Günde Javascript: Üst Düzey Fonksiyonlar</h1>

[![GitHub](https://img.shields.io/badge/Follow-0a4d0a?style=for-the-badge&logo=github&logoColor=white)](https://github.com/BilgeGates)<br>

<sub>Çevirmen:
<a href="https://github.com/BilgeGates">Khatai Huseynzada</a><br>
<small> Mayıs, 2023</small>
</sub>

</div>

[<< Gün 8](../08_Gün_Nesneler/08_gün_nesneler.md) | [Gün 10 >>](../10_Gün_Setler_ve_Haritalar/10_gün_setler_ve_haritalar.md)

- [📔 Gün 9](#-Gün-9)
  - [Üst Düzey Fonksiyonlar](#Üst-Düzey-Fonksiyonlar)
    - [Geri Çağırmak](#Geri-Çağırmak)
    - [Dönen İşlev](#Dönen-İşlev)
    - [Ayar Süresi](#Ayar-Süresi)
      - [Bir setInterval İşlevi Kullanarak Aralık Ayarlama](#Bir-setInterval-işlevi-kullanarak-Aralık-Ayarlama)
      - [setTimeout kullanarak Bir Zaman Ayarlama](#setTimeout-kullanarak-bir-zaman-ayarlama)
  - [Fonksiyonel Programlama](#Fonksiyonel-Programalama)
    - [forEach](#forEach)
    - [map](#map)
    - [filter](#filter)
    - [reduce](#reduce)
    - [every](#every)
    - [find](#find)
    - [findIndex](#findindex)
    - [some](#some)
    - [sort](#sort)
      - [String Değerlerini Sıralama](#String-Değerlerini-Sıralama)
      - [Sayısal Değerleri Sıralama](#Sayısal-Değerleri-Sıralama)
      - [Nesne Dizilerini Sıralama](#Nesne-Dizilerini-Sıralama)
  - [💻 Gün 9: Egzersizleri](#-Gün-9-Egzersizleri)
    - [Egzersiz: Seviye 1](#Egzersiz-Seviye-1)
    - [Egzersiz: Seviye 2](#Egzersiz-Seviye-2)
    - [Egzersiz: Seviye 3](#Egzersiz-Seviye-3)

# 📔 Gün 9

## Üst Düzey Fonksiyonlar

Yüksek dereceden (high order) fonksiyonlar, parametre olarak başka bir fonksiyonu içerisine alan veya bir başka fonksiyonu değer olarak döndürebilen fonksiyonlardır.

Bir fonksiyon parametre olarak geçilebiliyorsa bu fonksiyona ise **callback** fonksiyon denir.

### Geri Çağırmak

Callback fonksiyon yukarıda da söylediğimiz gibi bir başka fonksiyona parametre olarak verilen fonksiyonlardır.

```js
// callback fonksiyonun adını istediğimiz şekilde verebiliriz.
const callback = (n) => {
  return n ** 2
}
​
// bir başka fonksiyonu callback olarak alan fonksiyon
function cube(callback, n) {
  return callback(n) * n
}
​
console.log(cube(callback, 3))
```

### Dönen İşlev

Yüksek dereceden fonksiyonlar bir fonksiyonu değer olarak geri döndürebilir.
​

```js
// Bir fonksiyonun başka bir fonksiyonu geri döndürme örneği.
const higherOrder = (n) => {
  const doSomething = (m) => {
    const doWhatEver = (t) => {
      return 2 * n + 3 * m + t;
    };
    return doWhatEver;
  };
  return doSomething;
};
console.log(higherOrder(2)(3)(10));
```

Callback fonksiyonunu nasıl kullandığımızı görelim. Örneğin _foreach_ metodu callback kullanan metotlarından biridir.

```js
const numbers = [1, 2, 3, 4, 5];
const sumArray = (arr) => {
  let sum = 0;
  const callback = function (element) {
    sum += element;
  };
  arr.forEach(callback);
  return sum;
};
console.log(sumArray(numbers));
```

```sh
15
```

Yukarıdaki örnek aşağıdaki gibi basitleştirilebilir::

```js
const numbers = [1, 2, 3, 4]
​
const sumArray = arr => {
  let sum = 0
  arr.forEach(function(element) {
    sum += element
  })
  return sum

}
console.log(sumArray(numbers))
```

```sh
15
```

### Ayar Süresi

JavaScript'te bazı fonksiyonları belirli bir zaman aralığında yürütebiliriz veya bazı fonksiyonları yürütmek için belirli bir süre planlama (bekleme) yapabiliriz.

- setInterval
- setTimeout

#### Bir **setInterval** işlevi kullanarak Aralık Ayarlama

JavaScript'te, belirli bir zaman aralığında sürekli olarak istediğimiz şeyi yapmak için **SetInterval** fonksiyonunu kullanırız. SetInterval, genel olarak bir callback fonksiyonu ve ikinci olarak, belirlemek istediğimiz süreyi parametre alararak kullanılır.

```js
// syntax
var duration = 10;
function callback() {
  // code goes here
}
setInterval(callback, duration);
```

```js
function sayHello() {
  console.log("Hello");
}
setInterval(sayHello, 1000); // saniyede 1 Hello yazdırır, 1000ms = 1s
```

#### **setTimeout** ile zaman ayarlama

In JavaScript, we use setTimeout higher order function to execute some action at some time in the future. The setTimeout global method take a callback function and a duration as a parameter. The duration is in milliseconds and the callback wait for that amount of time.

Javascript'te ileriye dönük çalışacak fonksiyonlar planlayabiliriz. Tam da bu iş için **setTimeOut** metodu imdadımıza koşuyor. setTimeOut fonksiyonu da setInterval fonksiyonuna benzer şekilde bir callback fonksiyon ve ms cinsinden bir süre değerini parametre olarak alır.

```js
// syntax
function callback() {
  // code goes here
}
setTimeout(callback, duration);
```

```js
function sayHello() {
  console.log("Hello");
}
setTimeout(sayHello, 2000); //2 saniye bekledikten sonra "Hello" yazdıracak
```

## setTimeout kullanarak bir zaman ayarlama

JavaScript'in en son sürümü, normal döngü yazmak yerine karmaşık sorunları çözmemize yardımcı olabilecek birçok yerleşik yöntem sunmuştur.Göreceğimiz tüm metotlar callback fonksiyonu ile birlikte kullanılabilir. Bu bölümde, _forEach_, _map_, _filter_, _reduce_, _find_, _every_, _some_, and _sort_ metodlarını göreceğiz

### forEach

_forEach_: Bir dizi elemanlarını sırasıyla gezer. "element", "index" ve dizinin kendisi ile callback fonksiyonunu parametre olarak alabilir. "index" ve dizinin kendisi isteğe bağlı olarak parametre olarak verilmeyebilir.

```js
arr.forEach(function (element, index, arr) {
  console.log(index, element, arr);
});
// Yukarıdaki kod arrow function kullanılarak yazılabilir.
arr.forEach((element, index, arr) => {
  console.log(index, element, arr);
});
// Daha basite indirgemek istersek
arr.forEach((element, index, arr) => console.log(index, element, arr));
```

```js
let sum = 0;
const numbers = [1, 2, 3, 4, 5];
numbers.forEach((num) => console.log(num));
console.log(sum);
```

```sh
1
2
3
4
5
```

```js
let sum = 0;
const numbers = [1, 2, 3, 4, 5];
numbers.forEach((num) => (sum += num));

console.log(sum);
```

```sh
15
```

```js
const countries = ["Finland", "Denmark", "Sweden", "Norway", "Iceland"];
countries.forEach((element) => console.log(element.toUpperCase()));
```

```sh
FINLAND
DENMARK
SWEDEN
NORWAY
ICELAND
```

### map

_map_:Bir dizi elemanını yinelemek ve dizi öğelerini değiştirmek. callback fonksiyonla birlikte "elements", "index" yeni bir diziyi parametre olarak alabilir.

```js
const modifiedArray = arr.map(function (element, index, arr) {
  return element;
});
```

```js
/*Arrow function ve explicit return
const modifiedArray = arr.map((element,index) => element);
*/
//Example
const numbers = [1, 2, 3, 4, 5];
const numbersSquare = numbers.map((num) => num * num);

console.log(numbersSquare);
```

```sh
[1, 4, 9, 16, 25]
```

```js
const names = ["Khatai", "Mathias", "Elias", "Brook"];
const namesToUpperCase = names.map((name) => name.toUpperCase());
console.log(namesToUpperCase);
```

```sh
['KHATAİ', 'MATHIAS', 'ELIAS', 'BROOK']
```

```js
const countries = [
  "Albania",
  "Bolivia",
  "Canada",
  "Denmark",
  "Ethiopia",
  "Finland",
  "Germany",
  "Hungary",
  "Ireland",
  "Japan",
  "Kenya",
];
const countriesToUpperCase = countries.map((country) => country.toUpperCase());
console.log(countriesToUpperCase);

/*
// Arrow function
const countriesToUpperCase = countries.map((country) => {
  return country.toUpperCase();
})
//Explicit return arrow function
const countriesToUpperCase = countries.map(country => country.toUpperCase());
*/
```

```sh
['ALBANIA', 'BOLIVIA', 'CANADA', 'DENMARK', 'ETHIOPIA', 'FINLAND', 'GERMANY', 'HUNGARY', 'IRELAND', 'JAPAN', 'KENYA']
```

```js
const countriesFirstThreeLetters = countries.map((country) =>
  country.toUpperCase().slice(0, 3)
);
```

```sh
 ["ALB", "BOL", "CAN", "DEN", "ETH", "FIN", "GER", "HUN", "IRE", "JAP", "KEN"]
```

### filter

_Filter_: Dizi içerisinden istediğimiz koşullara uyan elemanları filtreleyerek geri döndürür

```js
//Ülkeler "land" ifadesi içersin
const countriesContainingLand = countries.filter((country) =>
  country.includes("land")
);
console.log(countriesContainingLand);
```

```sh
['Finland', 'Ireland']
```

```js
const countriesEndsByia = countries.filter((country) => country.endsWith("ia"));
console.log(countriesEndsByia);
```

```sh
['Albania', 'Bolivia','Ethiopia']
```

```js
const countriesHaveFiveLetters = countries.filter(
  (country) => country.length === 5
);
console.log(countriesHaveFiveLetters);
```

```sh
['Japan', 'Kenya']
```

```js
const scores = [
  { name: "Asabeneh", score: 95 },
  { name: "Khatai", score: 98 },
  { name: "Mathias", score: 80 },
  { name: "Elias", score: 50 },
  { name: "Martha", score: 85 },
  { name: "John", score: 100 },
];

const scoresGreaterEighty = scores.filter((score) => score.score > 80);
console.log(scoresGreaterEighty);
```

```sh
[{name: 'Asabeneh', score: 95}, { name: 'Khatai', score: 98 },{name: 'Martha', score: 85},{name: 'John', score: 100}]
```

### reduce

_reduce_: Reduce fonksiyonu bir callback fonksiyonu gerektirir. Dizinin her değeri için bir işlev yürütür ve sonunda diziyi tek bir değere düşürür.
Metodun dönüş değeri ilk parametresi olan accumulator parametresinde saklanır.

```js
arr.reduce((acc, cur) => {
  // bir değer döndürmeden önce bazı işlevler buraya kodlanır
  return;
}, initialValue);
```

```js
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce((acc, cur) => acc + cur, 0);

console.log(sum);
```

```js
15;
```

### every

_every_: Tüm elemanların tek bir açıdan benzer olup olmadığını kontrol edin. Booelan türünde geri dönüş yapar

```js
const names = ["Khatai", "Mathias", "Elias", "Brook"];
const areAllStr = names.every((name) => typeof name === "string"); // hepsi string türünde mi?

console.log(areAllStr);
```

```sh
true
```

```js
const bools = [true, true, true, true];
const areAllTrue = bools.every((b) => b === true); // hepsi true mu?

console.log(areAllTrue); // true
```

```sh
true

```

### find

_find_: İstenilen koşulu karşılayan ilk elemanı geri döndürür.

```js
const ages = [24, 22, 25, 32, 35, 18];
const age = ages.find((age) => age < 20);

console.log(age);
```

```js
18;
```

```js
const names = ["Khatai", "Mathias", "Elias", "Brook"];
const result = names.find((name) => name.length > 7);
console.log(result);
```

```js
const scores = [
  { name: "Asabeneh", score: 95 },
  { name: "Mathias", score: 80 },
  { name: "Khatai", score: 150 },
  { name: "Martha", score: 85 },
  { name: "John", score: 100 },
];

const score = scores.find((user) => user.score > 80);
console.log(score);
```

```sh
{ name: "Khatai", score: 150 }
```

### findIndex

_findIndex_: koşulu karşılayan ilk elemanın index değerini döndürür.

```js
const names = ["Asabeneh", "Mathias", "Elias", "Brook"];
const ages = [24, 22, 25, 32, 35, 18];

const result = names.findIndex((name) => name.length > 7);
console.log(result); // 0

const age = ages.findIndex((age) => age < 20);
console.log(age); // 5
```

### some

_some_: Bazı elemanların tek bir açıdan benzer olup olmadığını kontrol edin. Boolean türünde geri dönüş yapar.

```js
const names = ["Asabeneh", "Mathias", "Elias", "Brook"];
const bools = [true, true, true, true];

const areSomeTrue = bools.some((b) => b === true);

console.log(areSomeTrue); //true
```

```js
const areAllStr = names.some((name) => typeof name === "number"); // Are all strings ?
console.log(areAllStr); // false
```

### sort

_sort_: sort fonksiyonu, bir diziyi, öğelerini dizelere dönüştürerek ve bu dizeleri Unicode kod karakterleri sırasına göre karşılaştırarak (diziyi alfabetik olarak sıralar) sıralamanıza olanak tanır. Yeni bir dizi oluşturmadan eldeki olan diziyi düzenler

#### String Değerleri Sıralama

```js
const products = ["Milk", "Coffee", "Sugar", "Honey", "Apple", "Carrot"];
console.log(products.sort()); // ['Apple', 'Carrot', 'Coffee', 'Honey', 'Milk', 'Sugar']
//Now the original products array  is also sorted
```

#### Sayısal Değerleri Sıralama

Sayıları sıralamak malesef o kadar basit değil. Sıralama yöntemini doğrudan bir sayı dizisine uygularsak, beklenmedik bir sonuç göreceğiz:

```js
const numbers = [9.81, 3.14, 100, 37];

console.log(numbers.sort()); //[100, 3.14, 37, 9.81]
```

Sayısal değerleri artan veya azalan düzende sıralamak için, sıralama kriterini belirleyen bir fonksiyon kullanmamız gerekir. Sıralama yöntemi neyse ki negatif, sıfır ve pozitif değerleri doğru sırada sıralayabilir. **Sort()** methodu iki değeri karşılaştırdığında, değerleri karşılaştırma fonksiyonuna gönderir ve döndürülen değere göre sıralar.

- Sonuç negatifse; a, b'den önce sıralanır
- Sonuç pozitifse; a, b'den sonra sıralanır
- Sonuç 0 ise; hiçbir şey değişmez

Tek ihtiyacımız olan ise sort() metodu içinde karşılaştırma fonksiyonu kullanmak.

```js
numbers.sort(function (a, b) {
  return a - b;
});

console.log(numbers); // [3.14, 9.81, 37, 100]

numbers.sort(function (a, b) {
  return b - a;
});
console.log(numbers); //[100, 37, 9.81, 3.14]
```

#### Nesne Dizilerini Sıralama

Bir dizideki nesneleri sıraladığımız zaman karşılaştırmak için key objesini kullanırız. Aşağıdaki örneğe bakalım.

```js
objArr.sort(function (a, b) {
  if (a.key < b.key) return -1;
  if (a.key > b.key) return 1;
  return 0;
});

// or

objArr.sort(function (a, b) {
  if (a["key"] < b["key"]) return -1;
  if (a["key"] > b["key"]) return 1;
  return 0;
});

const users = [
  { name: "Asabeneh", age: 150 },
  { name: "Khataik", age: 50 },
  { name: "Eyob", age: 100 },
  { name: "Elias", age: 22 },
];
users.sort((a, b) => {
  if (a.age < b.age) return -1;
  if (a.age > b.age) return 1;
  return 0;
});
console.log(users); // sorted ascending
// [{…}, {…}, {…}, {…}]
```

🌕 Çok iyi gidiyorsunuz. Asla vazgeçmeyin, çünkü harika şeyler zaman alır. 9. Günü tamamladın ve mükemmelliğe giden yolda 9 adım attınız. Şimdi beyniniz ve kasınız için egzersiz yapın.

## 💻 Gün 9: Egzersizleri

### Egzersiz: Seviye 1

```js
const countries = ["Finland", "Azerbaijan", "Denmark", "Norway", "IceLand"];
const names = ["Asabeneh", "Khatai", "Elias", "Brook"];
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const products = [
  { product: "banana", price: 3 },
  { product: "mango", price: 6 },
  { product: "potato", price: " " },
  { product: "avocado", price: 8 },
  { product: "coffee", price: 10 },
  { product: "tea", price: "" },
];
```

1. gruptaki farkı açıklayın: **_forEach, map, filter, and reduce_**.
2. forEach, haritalama, filtreleme veya azaltmada kullanmadan önce bir geri arama işlevi tanımlayın.
3. **_forEach_** kullanarak, ülkeler dizisindeki her ülkeyi console.log dosyasına kaydedin.
4. Name dizisindeki her adı console.log olarak kaydetmek için **_forEach_** kullanın.
5. Numbers dizisindeki her sayıyı console.log için **_forEach_** kullanın.
6. **_map_** kullanarak, ülkeler dizisindeki her ülkeyi büyük harfe çevirerek yeni bir dizi oluşturun.
7. **_map_** kullanarak ülkeler dizisinden bir ülke uzunluğu dizisi oluşturun.
8. Numbers dizisindeki her sayıyı kareye çevirerek yeni bir dizi oluşturmak için **_map_** kullanın
9. Name dizisindeki her adı büyük harfe çevirmek için **_map_** kullanın.
10. Ürün dizisini ilgili fiyatlara eşlemek için **_map_** kullanın.
11. **_land_** içeren ülkeleri filtrelemek için **_filter_** kullanın.
12. Altı karakterli ülkeleri filtrelemek için **_filter_** kullanın.
13. Ülke dizisinde altı veya daha fazla harf içeren ülkeleri filtrelemek için **_filter_** kullanın.
14. 'E' ile başlayan ülkeyi filtrelemek için **_filter_** kullanın;
15. Yalnızca değerleri olan fiyatları filtrelemek için **_filter_** kullanın.
16. Bir diziyi parametre olarak alan ve ardından yalnızca dize öğeleriyle bir dizi döndüren getStringLists adlı bir işlev bildirin.
17. Numbers dizisindeki tüm sayıları toplamak için **_reduce_** kullanın.
18. Tüm ülkeleri birleştirmek ve şu cümleyi oluşturmak için **_reduce_** kullanın: **_Estonya, Finlandiya, İsveç, Danimarka, Norveç ve İzlanda kuzey Avrupa ülkeleridir_**
19. **_bazı_** ve **_every_** arasındaki farkı açıklayın
20. **_some_** kullanarak, name dizisindeki bazı adların yediden uzun olup olmadığını kontrol edin
21. Tüm ülkelerin arazi kelimesini içerip içermediğini kontrol etmek için **_every_** kullanın
22. **_find_** ve **_findIndex_** arasındaki farkı açıklayın.
23. **_find_** kullanarak ülkeler dizisinde yalnızca altı harf içeren ilk ülkeyi bulun
24. **_findIndex_** ile ülkeler dizisinde yalnızca altı harf içeren ilk ülkenin konumunu bulun
25. -1 alacağınız dizide yoksa **_Norway_** konumunu bulmak için **_findIndex_** kullanın.
26. **_findIndex_** kullanarak **_Russia_** dizisinde yoksa -1 alacağınız dizideki konumunu bulun.

### Egzersiz: Seviye 2

1. İki veya daha fazla dizi yineleyiciyi zincirleyerek ürünlerin toplam fiyatını bulun(örn. arr.map(callback).filter(callback).reduce(callback))
2. Ürünlerin fiyatlarının toplamını sadece küçült ve azalt(geri ara) kullanarak bulun.
3. **_categorizeCountries_** adlı bir işlev tanımlayın ve bu işlev bazı ortak modellere sahip bir ülkeler dizisi döndürür (bu depoda ülkeler dizisini country.js olarak bulabilirsiniz(örneğin 'arazi', 'ia', 'ada',') dur')).
4. Bir ülke adıyla başlamak için harf ve harfin kullanım sayısı olan bir nesne dizisini döndüren bir işlev oluşturun.
5. Bir **_getFirstTenCountries_** işlevi bildirin ve on ülkeden oluşan bir dizi döndürün. Country.js dizisinde çalışmak için farklı işlevsel programlama kullanın
6. Country dizisindeki son on ülkeyi döndüren bir **_getLastTenCountries_** işlevi bildirin.
7. Ülkeler dizisinden bir ülke adının ilk harfi olarak birçok kez hangi \_harfin kullanıldığını bulun (örn. Finlandiya, Fiji, Fransa vb.)

### Egzersiz: Seviye 3

1. Veri klasöründeki ülke bilgilerini kullanın. Ülkeleri ada göre, sermayeye göre, nüfusa göre sıralayın
2. \*\*\* En çok konuşulan 10 dili bulun:

   ````js
   // Your output should look like this
   console.log(mostSpokenLanguages(countries, 10))
   [
   {country: 'English',count:91},
   {country: 'French',count:45},
   {country: 'Arabic',count:25},
   {country: 'Spanish',count:24},
   {country:'Russian',count:9},
   {country:'Portuguese', count:9},
   {country:'Dutch',count:8},
   {country:'German',count:7},
   {country:'Chinese',count:5},
   {country:'Swahili',count:4}
   ]

   // Your output should look like this
   console.log(mostSpokenLanguages(countries, 3))
   [
   {country: 'English',count: 91},
   {country: 'French',count: 45},
   {country: 'Arabic',count: 25},
   ]```

   ````

3. \*\*\*country_data.js dosyasını kullanarak en kalabalık on ülkeyi oluşturan bir işlev oluşturun

   ````js
   console.log(mostPopulatedCountries(countries, 10))

   [
   {country: 'China', population: 1377422166},
   {country: 'India', population: 1295210000},
   {country: 'United States of America', population: 323947000},
   {country: 'Indonesia', population: 258705000},
   {country: 'Brazil', population: 206135893},
   {country: 'Pakistan', population: 194125062},
   {country: 'Nigeria', population: 186988000},
   {country: 'Bangladesh', population: 161006790},
   {country: 'Russian Federation', population: 146599183},
   {country: 'Japan', population: 126960000}
   ]

   console.log(mostPopulatedCountries(countries, 3))
   [
   {country: 'China', population: 1377422166},
   {country: 'India', population: 1295210000},
   {country: 'United States of America', population: 323947000}
   ]
   ```

   ````

4. \*\*\* Bir örneğin merkezi eğilim ölçüsünü (ortalama, medyan, mod) ve değişkenlik ölçüsünü (aralık, varyans, standart sapma) hesaplayan bir program geliştirmeye çalışın. Bu ölçümlere ek olarak örneğin min, max, sayım, yüzdelik ve frekans dağılımını bulun. İstatistik adında bir nesne oluşturabilir ve istatistik nesnesi için yöntem olarak istatistiksel hesaplamalar yapan tüm işlevleri oluşturabilirsiniz. Aşağıdaki çıktıyı kontrol edin.

   ```js
   const ages = [31, 26, 34, 37, 27, 26, 32, 32, 26, 27, 27, 24, 32, 33, 27, 25, 26, 38, 37, 31, 34, 24, 33, 29, 26]

   console.log('Count:', statistics.count()) // 25
   console.log('Sum: ', statistics.sum()) // 744
   console.log('Min: ', statistics.min()) // 24
   console.log('Max: ', statistics.max()) // 38
   console.log('Range: ', statistics.range() // 14
   console.log('Mean: ', statistics.mean()) // 30
   console.log('Median: ',statistics.median()) // 29
   console.log('Mode: ', statistics.mode()) // {'mode': 26, 'count': 5}
   console.log('Variance: ',statistics.var()) // 17.5
   console.log('Standard Deviation: ', statistics.std()) // 4.2
   console.log('Variance: ',statistics.var()) // 17.5
   console.log('Frequency Distribution: ',statistics.freqDist()) # [(20.0, 26), (16.0, 27), (12.0, 32), (8.0, 37), (8.0, 34), (8.0, 33), (8.0, 31), (8.0, 24), (4.0, 38), (4.0, 29), (4.0, 25)]
   ```

   ```sh
   console.log(statistics.describe())
   Count: 25
   Sum:  744
   Min:  24
   Max:  38
   Range:  14
   Mean:  30
   Median:  29
   Mode:  (26, 5)
   Variance:  17.5
   Standard Deviation:  4.2
   Frequency Distribution: [(20.0, 26), (16.0, 27), (12.0, 32), (8.0, 37), (8.0, 34), (8.0, 33), (8.0, 31), (8.0, 24), (4.0, 38), (4.0, 29), (4.0, 25)]
   ```

🎉 Tebrikler ! 🎉

[<< Gün 8](../08_Gün_Nesneler/08_gün_nesneler.md) | [Gün 10 >>](../10_Gün_Setler_ve_Haritalar/10_gün_setler_ve_haritalar.md)
