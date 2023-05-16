<div align="center">
<h1> 30 günde JavaScript: Döngüler</h1>

<a class="header-badge" target="_blank" href="https://twitter.com/developerkhatai">
<img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/developerkhatai?style=social">
</a><br>

<sub>Yazar:
<a href="https://github.com/BilgeGatess">Khatai Huseynzade</a><br>
<small> Mayıs, 2023</small>
</sub>

</div>

[<< Gün 5](../05_Gün_Diziler/05_gün_diziler.md) | [Gün 7 >>](../07_Gün_Fonksiyonlar/07_gün_fonksiyonlar.md)

- [📔 Gün 6](#-Gün-6)
  - [Döngüler](#Döngüler)
    - [for Döngüsü](#for-döngüsü)
    - [while Döngüsü](#while-döngüsü)
    - [do while Döngüsü](#do-while-döngüsü)
    - [for of loop Döngüsü](#for-of-loop-döngüsü)
    - [break](#break)
    - [continue ](#continue)
  - [💻 Gün 6: Egzersizleri](#-Gün-6-Egzersizleri)
    - [Egzersiz: Seviye 1](#Egzersiz-seviye-1)
    - [Egzersiz: Seviye 2](#Egzersiz-seviye-2)
    - [Egzersiz: Seviye 3](#Egzersiz-seviye-3)

# 📔 Gün 6

### Döngüler

Yazılım kariyerimizde bir çok defa aynı işi tekrar tekrar yapmamız gerekebilir. Basit olarak Console.log() kullanarak 0'den 100'e kadar çıktı yazdırmayı deneyelim. Bu basit uygulamayı gerçekleştirmek bile 2 ila 5 dakika arasında zamanımızı alabilir; bu tür yorucu ve tekrarlayan görevler döngü kullanılarak gerçekleştirilebilir. Videoları izlemeyi tercih ediyorsanız.

Tekrar eden görevleri gerçekleştirmek için programlama dillerinde farklı döngü türleri kullanırız. Aşağıdaki örnekler, JavaScript ve diğer programlama dillerinde yaygın olarak kullanılan döngülerdir.

### for Döngüsü

```js
// For Döngüsünün yapısı
for(başlangıç_değeri, şart, arttırma/azaltma){
  // uygulamak istediğimiz kod
}
```

```js
for (let i = 0; i <= 5; i++) {
  console.log(i);
}

// 0 1 2 3 4 5
```

```js
for (let i = 5; i >= 0; i--) {
  console.log(i);
}

// 5 4 3 2 1 0
```

```js
for (let i = 0; i <= 5; i++) {
  console.log(`${i} * ${i} = ${i * i}`);
}
```

```sh
0 * 0 = 0
1 * 1 = 1
2 * 2 = 4
3 * 3 = 9
4 * 4 = 16
5 * 5 = 25
```

```js
const countries = ["Finland", "Sweden", "Azerbaijan", "Norway", "Iceland"];
const newArr = [];
for (let i = 0; i < countries.length; i++) {
  newArr.push(countries[i].toUpperCase());
}

// ["FINLAND", "SWEDEN", "AZERBAIJAN", "NORWAY", "ICELAND"]
```

Dizideki tüm elemanları toplama

```js
const numbers = [1, 2, 3, 4, 5];
let sum = 0;
for (let i = 0; i < numbers.length; i++) {
  sum = sum + numbers[i];
  // daha pratik kullanım için, sum += numbers[i]
}

console.log(sum); // 15
```

Mevcut diziyi temel alan yeni bir dizi oluşturma

```js
const numbers = [1, 2, 3, 4, 5];
const newArr = [];
let sum = 0;
for (let i = 0; i < numbers.length; i++) {
  newArr.push(numbers[i] ** 2);
}

console.log(newArr); // [1, 4, 9, 16, 25]
```

```js
const countries = ["Finland", "Sweden", "Norway", "Azerbaijan", "Iceland"];
const newArr = [];
for (let i = 0; i < countries.length; i++) {
  newArr.push(countries[i].toUpperCase());
}

console.log(newArr); // ["FINLAND", "SWEDEN", "NORWAY", "AZERBAIJAN", "ICELAND"]
```

### while Döngüsü

while anahtar kelimesinin yanında belirtilen şarta doğru olduğu sürece çalışan bir döngü türüdür. Eğer koşul sürekli doğru çıkacak şekilde ayarlanırsa while döngüsü uygulama kasten kesilmediği sürece sonsuza kadar devam edebilir. Bu yüzden buraya dikkat etmek gerekebilir.

```js
let i = 0;
while (i <= 5) {
  console.log(i);
  i++;
}

// 0 1 2 3 4 5
```

### do while Döngüsü

do while döngüsü Koşul ile belirtilen alanın doğru olup olmadığına bakmadan kod bloğunu bir kez çalıştırır ve daha sonra Koşul ile belirtilen alan doğru (true) olduğu sürece kod bloğunun çalışması için kullanılır.

```js
let i = 0;
do {
  console.log(i);
  i++;
} while (i <= 5);

// 0 1 2 3 4 5
```

### аor of loop Döngüsü

ES6, geleneksel bir döngüden daha basit olan bir döngü olan yeni bir döngü yöntemi sunar ve her tür için ve giriş döngülerinin eksikliklerini telafi eder.

`for..of `Deyimi, yinelenen nesneler üzerinde yinelemek için bir döngü oluşturur. ES6'da tanıtılan `for..of` döngü , yeni yinelemeli protokollerin yerini alır. `for..in` ve `forEach()` destekler. `for..of` Array (Diziler), String (Metinler), Map (Haritalar), Set (Kümeler), Array benzeri nesneler (örneğin arguments veya NodeList), ve diğer yinelenen veri yapıları arasında yineleme yapmanızı sağlar.

```js
for (const element of arr) {
  // uygulamak istediğimiz kod
}
```

```js
const numbers = [1, 2, 3, 4, 5];

for (const num of numbers) {
  console.log(num);
}

// 1 2 3 4 5

for (const num of numbers) {
  console.log(num * num);
}

// 1 4 9 16 25

// array içindeki tüm nsayıları toplama
let sum = 0;
for (const num of numbers) {
  sum = sum + num;
  // daha pratik kullanım için, sum += num
  // bundan sonra pratik olan bu syntax türünün kullanacağız(+=, -=, *=, /= etc)
}
console.log(sum); // 15

const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
];

for (const tech of webTechs) {
  console.log(tech.toUpperCase());
}

// HTML CSS JAVASCRIPT REACT NODE MONGODB

for (const tech of webTechs) {
  console.log(tech[0]); // her öğenin yalnızca ilk harfini alın,  H C J R N M
}
```

```js
const countries = ["Finland", "Sweden", "Norway", "Azerbaijan", "Iceland"];
const newArr = [];
for (const country of countries) {
  newArr.push(country.toUpperCase());
}

console.log(newArr); // ["FINLAND", "SWEDEN", "NORWAY", "AZERBAIJAN", "ICELAND"]
```

### break

Break, bir döngüyü kesmek için kullanılır.

```js
for (let i = 0; i <= 5; i++) {
  if (i == 3) {
    break;
  }
  console.log(i);
}

// 0 1 2
```

i değeri 3 sayısına eşit olduğunda döngüyü durdurur

### continue

Belirli bir döngü aşamasını atlamak için `continue` anahtar kelimesi kullanılır.

```js
for (let i = 0; i <= 5; i++) {
  if (i == 3) {
    continue;
  }
  console.log(i);
}

// 0 1 2 4 5
```

🌕 Adım-adım öğrenmeye devam! 6. günü başarıyla bitirdiğmize göre şimdi sıra alıştırma ve pratik yapmada.

## 💻 Gün 6: Egzersizleri

### Egzersiz: Seviye 1

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
  "Azerbaijan",
  "Kenya",
];

const webTechs = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Redux",
  "Node",
  "MongoDB",
];

const mernStack = ["MongoDB", "Express", "React", "Node"];
```

1. while ve do while kullanarak 0 dan 10'a kadar giden bir döngü kurun.
2. while ve do while kullanarak 10 dan 0'a kadar giden bir döngü kurun.
3. 0'dan n' e kadar giden bir for döngüsü kurun.
4. Console.log() kullanarak aşağıdaki çıktıyı almayı deneyin.

   ```js
       #
       ##
       ###
       ####
       #####
       ######
       #######
   ```

5. Aşağıdaki çıktıyı almak için bir döngü kurun:

   ```sh
   0 x 0 = 0
   1 x 1 = 1
   2 x 2 = 4
   3 x 3 = 9
   4 x 4 = 16
   5 x 5 = 25
   6 x 6 = 36
   7 x 7 = 49
   8 x 8 = 64
   9 x 9 = 81
   10 x 10 = 100
   ```

6. Aşağıdaki çıktıyı almak için bir döngü kurun:

   ```sh
    i    i^2   i^3
    0    0     0
    1    1     1
    2    4     8
    3    9     27
    4    16    64
    5    25    125
    6    36    216
    7    49    343
    8    64    512
    9    81    729
    10   100   1000
   ```

7. 0'dan 100'e kadar olan çift sayıları bir döngü yardımı ile ekrana yazdırın.
8. 0'dan 100'e kadar olan tek sayıları bir döngü yardımı ile ekrana yazdırın
9. 0'dan 100'e kadar olan asal sayıları bir döngü yardımı ile ekrana yazdırın
10. 0 ile 100 arasındaki tüm sayıların toplamını ekrana yazıdırn

    ```sh
    0 ile 100 arasındaki sayıların toplamı: 5050.
    ```

11. 0 ile 100 arasındaki tek ve çift sayıların toplamını bulun

    ```sh
    Çift sayıların toplamı 2550
    Tek sayıların toplamı 2500
    ```

### Egzersiz: Seviye 2

1. Herhangi bir sayıda rastgele id numarası atayan bir fonksiyon yazın

   ```sh
     fe3jo1gl124g
   ```

   ```sh
     xkqci4utda1lmbelpkm03rba
   ```

2. Rastgele hexadecimal sayı üreten bir fonksiyon yazın.

   ```sh
   '#ee33df'
   ```

3. Rastgele bir rgb renk numarası oluşturan fonksiyon yazın.

   ```sh
   rgb(240,180,80)
   ```

   ```sh
   ["ALBANIA", "BOLIVIA", "CANADA", "DENMARK", "AZERBAIJAN", "FINLAND", "GERMANY", "HUNGARY", "IRELAND", "JAPAN", "KENYA"]
   ```

4. Yukarıdaki array'i kullanarak rastgele yeni bir dizi oluşturun.

5. Yukarıdaki array'i kullanarak ülkelerin harf uzunluklarını içeren bir dizi olşturun'.

   ```sh
   [7, 7, 6, 7, 8, 7, 7, 7, 7, 5, 5]
   ```

6. Yukarıdaki diziyi kullanarak aşağıdaki diziyi oluşturun:

   ```sh
     [
     ['Albania', 'ALB', 7],
     ['Bolivia', 'BOL', 7],
     ['Canada', 'CAN', 6],
     ['Denmark', 'DEN', 7],
     ['Ethiopia', 'ETH', 8],
     ['Finland', 'FIN', 7],
     ['Germany', 'GER', 7],
     ['Azerbaijan', 'AZE', 7],
     ['Ireland', 'IRE', 7],
     ['Iceland', 'ICE', 7],
     ['Japan', 'JAP', 5],
     ['Kenya', 'KEN', 5]
   ]
   ```

7. Yukarıdaki ülkeler dizisinde "land" sözcüğünü içeren bir ülke veya ülke olup olmadığını kontrol edin. "land" içeren ülkeler varsa bunu dizi halinde yazdırın.

   ```sh
   ['Finland','Azerbaijan', 'Iceland']
   ```

8. Yukarıdaki ülkeler dizisinde "ia" sözcüğünü içeren bir ülke veya ülke olup olmadığını kontrol edin. "ia" içeren ülkeler varsa bunu dizi halinde yazdırın..

   ```sh
   ['Albania', 'Bolivia','Ethiopia']
   ```

9. Yukarıdaki ülkeler dizisini kullanarak en fazla karakter içeren ülkeyi bulun.

   ```sh
   Ethiopia
   ```

10. Yukarıdaki ülkeler dizisini kullanarak, yalnızca 5 karakter içeren ülkeyi bulun.

    ```sh
    ['Japan', 'Kenya']
    ```

### Egzersiz: Seviye 2

1. Countries dizisini kopyalayın(Avoid mutation)
2. Diziler değişebilir. Dizinin orjinalini değişirmeden bir kopyasını oluşturun. Oluşturduğunuz diziyi alfabetik olarak sıralayın ve sortedCountries dizisine atayın
3. webTechs dzisini ve mernStack dizisini sıralayın
4. [Ölkelerin Dizileri](https://github.com/BilgeGates/30-Days-Of-JavaScript-TR/blob/master/data/countries.js) inden "land" sözüğü ile biten ülkeleri farklı bir diziye atayın
5. [Ölkelerin Dizileri](https://github.com/BilgeGates/30-Days-Of-JavaScript-TR/blob/master/data/countries.js) inden en uzun karakterli ülkeyi bulun
6. [Ölkelerin Dizileri](https://github.com/BilgeGates/30-Days-Of-JavaScript-TR/blob/master/data/countries.js) inde 4 karakterli ülkeleri yazdırın
7. [Ölkelerin Dizileri](https://github.com/BilgeGates/30-Days-Of-JavaScript-TR/blob/master/data/countries.js) inde iki veya daha fazla kelime içieren ülkeleri farklı bir diziye atayın
8. [Ölkelerin Dizileri](https://github.com/BilgeGates/30-Days-Of-JavaScript-TR/blob/master/data/countries.js) i ters çevirin ve ülkelerin tüm harflerini büyük hale gertirin

🎉 Tebrikler ! 🎉

[<< Gün 5](../05_Gün_Diziler/05_gün_diziler.md) | [Gün 7 >>](../07_Gün_Fonksiyonlar/07_gün_fonksiyonlar.md)
