<div align="center">
<h1> 30 Günde JavaScript: Veri Tipleri</h1>

<a class="header-badge" target="_blank" href="https://twitter.com/developerkhatai">
<img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/developerkhatai?style=social">
</a><br>

<sub>Çevirmen:
<a href="https://github.com/BilgeGatess">Khatai Huseynzade</a><br>
<small> Mayıs, 2023</small>
</sub>

</div>

[<< Gün 1](../01_Gün_Giriş/01_gün_giriş.md) | [Gün 3 >>](../03_Gün_Boole-değerleri_Operatörler_Tarih-objesi/03_gün_boole-değerleri_operatörler_tarih-objesi.md)

- [📔 Gün 2](#-Gün-2)
  - [Veri Tipleri](#Veri-Tipleri)
    - [İlkel Veri Türleri](#İlkel-Veri-Türleri)
    - [İlkel Olmayan Veri Türleri](#İLkel-Olmayan-Veri-Türleri)
  - [Sayılar](#Sayılar)
    - [Sayı Veri Türlerini Bildirme](#Sayı-Veri-Türleri-Bildirme)
    - [Matematik Nesnesi ](#Matematik-Nesnesi)
      - [Rastgele Sayı Üretme](#Rastgele-Sayı-Üretme)
  - [Stringler](#Stringler)
    - [String Birleştirme](#String-Birleştirme)
      - [Toplama Operatörünü Kullanarak Birleştirme](#Toplama-Operatörü-Kullanarak-Birleştirme)
      - [Uzun Değişmez Stringler](#Uzun-Değişmez-Stringler)
      - [Stringlerdeki Kaçış Dizileri](#Stringlerdeki-Kaçış-Dizileri)
      - [Şablon Değişmezleri](#Şablon-Değişmezleri)
    - [String Metotları](#String-Metotları)
  - [Veri Türlerini Kontrol Etme ve Döküm](#Veri-Türlerini-Kontrol-Etme-ve-Döküm)
    - [Veri Türlerini Kontrol Etme](#Veri-Türlerini-Kontrol-Etme)
    - [Veri Türünü Değiştirme ](#Veri-Türünü-Değiştirme)
      - [String to Int](#String-to-İnt)
      - [String to Float](#String-to-Float)
      - [Float to Int](#Float-to-İnt)
  - [💻 Gün 2: Egzersizleri](#-Gün-2-Egzersizleri)
    - [Egzersiz: Seviye 1](#Egzersiz-Seviye-1)
    - [Egzersiz: Seviye 2](#Egzersiz-Seviye-2)
    - [Egzersiz: Seviye 3](#Egzersiz-Seviye-3)

# 📔 Gün 2

## Veri Tiperi

Bir Önceki bölümde, veri türlerinden biraz bahsettik. Veri veya değerlerin (veri) türleri vardır.
Veri türleri, verilerin özelliklerini tanımlar. Veri türleri ikiye ayrılabilir:

1. İlkel veri türleri
2. İlkel olmayan veri türleri (Nesne Referansları)

### İlkel Veri Türleri

JavaScript'teki ilkel veri türleri şunları içerir:

1.  Numbers - Tamsayılar - Ondalık sayılar
2.  Strings - Tek tırnak, çift tırnak veya ters tırnak içerisindeki tüm veriler..
3.  Booleans - true yada false (true = 1 false = 0 bu iki terimi bu şekilde öğrenin. Çevirilerine çok girmeyin kısaca var yada yok )
4.  Null - Boş değer yada değeri yok
5.  Undefined - Bir değer verilmeyen değişken. ( Örn: let variables; )
6.  Symbol - Sembol yapıcısı tarafından oluşturulabilen benzersiz bir değer

JavaScript'teki ilkel olmayan veri türleri şunları içerir:

1.  Nesneler
2.  Diziler

Şimdi ilkel ve ilkel olmayan veri türlerinin tam olarak ne anlama geldiğini görelim.
_İlkel_ veri türleri değişmez (değiştirilemez) veri türleridir. İlkel bir veri türü oluşturulduktan sonra onu değiştiremeyiz.

**Örnek:**

```js
let word = "JavaScript";
```

_word_ değişkeninde saklanan dizeyi değiştirmeye çalışırsak JavaScript bir hata vermelidir. Tek, çift veya ters tırnak arasındaki herhangi bir veri türü, dize veri türüdür.

```js
word[0] = "Y";
```

Bu ifade _word_ değişkeninde saklanan dizeyi değiştirmez. Yani, string'lerin değiştirilemez ya da başka bir deyişle değişmez olduğunu söyleyebiliriz.
İlkel veri türleri değerlerine göre karşılaştırılır. Farklı veri değerlerini karşılaştıralım. Aşağıdaki örneğe bakın:

```js
let numOne = 3;
let numTwo = 3;

console.log(numOne == numTwo); // true ( Burada iki değişkende 3 e eşit olduğu için birbirine eşit olduğu sonucu çıkıyor )

let js = "JavaScript";
let py = "Python";

console.log(js == py); //false  ( Burada iki değişkende farklı olduğu ve eşitlenemedikleri için false yani 0 değeri dönüyor )

let lightOn = true;
let lightOff = false;

console.log(lightOn == lightOff); //false  ( Yukarıdaki örnek gibi eeşit olmadıkları için false yani 0 değeri dönüyor )
```

### İlkel Olmayan Veri Türleri

_İlkel olmayan_ veri türleri düzenlenebilir veya değiştirilebilir. İlkel olmayan veri türlerinin değerini, oluşturulduktan sonra değiştirebiliriz.
Bir dizi oluşturarak görelim. Dizi, köşeli parantez içindeki veri değerlerinin bir listesidir.Diziler aynı veya farklı veri türlerini içerebilir. Dizi değerleri dizin indekslerine ( dizinine ) göre referans alınır. JavaScript'te dizilerin indeksi sıfırdan başlar. Yani bir dizinin ilk elemanı sıfır indeksinde, ikinci elemanı bir indeksinde, üçüncü elemanı iki indeksinde bulunur.
( Orjinal anlatıma bağlı kalmak istiyorum lakin bazen anlamsız olabiliyor. Kısaca diziler okunurken 0-1-2-3 .... şeklinde indekslenir. Bir dizinin ilk elemanına erişmek istiyorsanız indeks numarasına 0 yazmalısınız. Aşağıdaki örneği incelerseniz bu karmaşıklığı çözmüş olacaksınız. )

```js
let nums = [1, 2, 3];
nums[0] = 10;

console.log(nums); // [10, 2, 3] ( nums değişkeninin ilk elemanı yada 0. indeksinin değerini 10 yapmış oldu )
```

Gördüğünüz gibi "DİZİ" ilkel olmayan bir veri türü değişkenidir. İlkel olmayan veri türleri değere göre karşılaştırılamaz. İlkel olmayan veri türleri aynı özelliklere ve değerlere sahip olsa bile, kesinlikle eşit değildirler.

```js
let nums = [1, 2, 3];
let numbers = [1, 2, 3];

console.log(nums == numbers); // false

let userOne = {
  name: "Khatai",
  country: "Azerbaijan",
};

let userTwo = {
  name: "Khatai",
  country: "Huseynzade",
};

console.log(userOne == userTwo); // false
```

Temel kural, ilkel olmayan veri türlerini karşılaştıramıyoruz. Dizileri (arrays), fonksiyonları (functions) veya nesneleri (objects) karşılaştırmayın.
İlkel olmayan değerler, değer yerine referansla karşılaştırıldıkları için referans türleri olarak adlandırılır. İki nesne, yalnızca aynı temel nesneye atıfta bulunuyorlarsa kesinlikle eşittir.

```js
let nums = [1, 2, 3];
let numbers = nums;

console.log(nums == numbers); // true ( değişken oluştururken numbers'ın değerini nums'a eşitlediği için bunun sonucu true dönmektedir.)

let userOne = {
  name: "Khatai",
  country: "Azerbaijan",
};

let userTwo = userOne;

console.log(userOne == userTwo); // true ( yukarıdaki ile aynı )
```

İlkel veri türleri ile ilkel olmayan veri türleri arasındaki farkı anlamakta zorluk çekiyorsan, bunu yaşayan tek kişi değilsin. Sakin ol ve bir sonraki bölüme geç ve bir süre sonra geri gelip burayı tekrar incele. Şimdi sayı türlerine göre veri türlerine başlayalım.

## Sayılar

Sayılar, tüm aritmetik işlemleri yapabilen tam sayılar ve ondalık değerlerdir.
Hadi sayılar ile ilgili bazı örnekler görelim.

### Sayı Veri Türlerini Bildirme

```js
let age = 35;
const gravity = 9.81; // yer çekimi kuvvet değeri bu değer haliyle değişmeyeceği için const olarak tanımlanıyor. Değişmez değişkenleri const ile tanımlarsınız. Bunu unutmayın.
let mass = 72; // kilogram cinsinden kütle
const PI = 3.14; // pi sayısı matematikte sabit bir sayı olduğu için const ile oluşturulmuş. ( küsüratı almamış )

// daha fazla örnek
const boilingPoint = 100; // derece cinsinden sıcaklık, suyun sabit olan kaynama noktası ( derecesi )
const bodyTemp = 37; // derece. İnsan vücudun sabit olan ortalama sıcaklığı

console.log(age, gravity, mass, PI, boilingPoint, bodyTemp);
```

### Matematik Nesnesi

JavaScript'te Math Objesi, sayılar ile çalışmanız için birçok yöntem sağlar.

```js
const PI = Math.PI; // Buraya kısa bir açıklama getirelim. Math objesi sayesinde PI sayısının değerini otomatik alıyoruz.

console.log(PI); // 3.141592653589793

// En yakın sayıya yuvarlama
// Eğer .5'in altındaysa aşağıya üstündeyse yukarıya yuvarlar. Örn: 3.14 ise 3 yapar 3.51 ise 4 yapar.

console.log(Math.round(PI)); // 3.14 olduğu için 3 e yuvarlama yapıyor

console.log(Math.round(9.81)); // Ondası 0.5 üstünde olduğu için 10 yapar

console.log(Math.floor(PI)); // floor aşağı yuvarlar Bu 3 olur

console.log(Math.ceil(PI)); // ceil yukarı yuvarlar Bu 4 olur

console.log(Math.min(-5, 3, 20, 4, 5, 10)); // En küçük sayıyı bulmaya yaradığı için sonuç -5 döner

console.log(Math.max(-5, 3, 20, 4, 5, 10)); // En büyük sayıyı bulmaya yaradığı için sonuç 20 döner

const randNum = Math.random(); // 0 ile 0.999999 arasında rastgele bir sayı üretir.
console.log(randNum);

// 0 ile 10 arasında rastgele bir sayı oluşturalım.

const num = Math.floor(Math.random() * 11); // 0 ile 10 arasında rastgele sayı oluşturur
console.log(num);

//Mutlak değer
console.log(Math.abs(-10)); // 10

//Kare kök
console.log(Math.sqrt(100)); // 10

console.log(Math.sqrt(2)); // 1.4142135623730951

// Üs
console.log(Math.pow(3, 2)); // 9

console.log(Math.E); // 2.718

// Logaritma
// Returns the natural logarithm with base E of x, Math.log(x)
console.log(Math.log(2)); // 0.6931471805599453
console.log(Math.log(10)); // 2.302585092994046

// Sırasıyla 2 ve 10'un doğal logaritmasını döndürür
console.log(Math.LN2); // 0.6931471805599453
console.log(Math.LN10); // 2.302585092994046

// Trigonometri
Math.sin(0);
Math.sin(60);

Math.cos(0);
Math.cos(60);
```

#### Rastgele Sayı Üretme

JavaScript'te Math nesnesi random() methodu 0 ile 0,999999999 arasında bir sayı üretir

```js
let randomNum = Math.random(); // 0 ile 0.999999999 arasında bir sayı üretir
```

Şimdi 0 ile 10 arasında rastgele bir sayı üretmek için random() methodu'nu nasıl kullanabileceğimizi görelim:

```js
let randomNum = Math.random(); // 0 ile 0.999 arasında oluşturur
let numBtnZeroAndTen = randomNum * 11;

console.log(numBtnZeroAndTen); // Sonuç : minimum  0 ve maksimum 10.99

let randomNumRoundToFloor = Math.floor(numBtnZeroAndTen); // yuvarlama yapıyor
console.log(randomNumRoundToFloor); // Sonuç 0 ile  10 arasında çıkar
```

## Strings

Dizeler **_tek_**, **_çift_** ve **_ters tırnak_** arasındaki metinlerdir.
Bir dize bildirmek için değişken adına, atama operatörüne, tek tırnak, çift tırnak veya ters tırnak içerisinde bir değere ihtiyacımız var.
Bazı dize örnekleri görelim:

```js
let space = " "; // boş alan string çift tırnaklı
let firstName = _'Khatai'_; // tek tırnaklı string
let lastName = "Huseynzade"; // çift tırnaklı string
let country = `Azerbaijan`; // ters tırnaklı string
```

### String Birleştirme

İki veya daha fazla string'i birbirine bağlama işlemine birleştirme denir.
Yukarda bulunan string örneklerini kullanarak:

```js
let fullName = firstName + space + lastName; // birleştirme, iki string'i bir araya getirme.
console.log(fullName);
```

```sh
Asabeneh Yetayeh
```

String'leri farklı şekildede birleştirebiliriz.

#### Toplama Operatörünü Kullanarak Birleştirme

Ekleme operatörü kullanarak birleştirme eski bir yöntemdir. Bu birleştirme yöntemi sıkıcı ve hataya açıktır. Bu şekilde nasıl birleştirileceğini bilmek iyidir, ancak ES6 şablon dizelerini kullanmanızı şiddetle tavsiye ederim (daha sonra açıklanacaktır).

```js
// Farklı veri türlerini oluşturma
let space = " ";
let firstName = "Khatai";
let lastName = "Huseynzade";
let country = "Azerbaijan";
let city = "Baku";
let language = "JavaScript";

let fullName = firstName + space + lastName;
let personInfoOne = fullName + ". I live in " + country; //  toplama operatörü ile değişkenleri birleştiriyor

console.log(personInfoOne);
```

```sh
Khatai Huseynzade.  I live in Azerbaijan
```

#### Uzun Değişmez Stringler

Stringler tek bir karakter, paragraf yada sayfa olabilir. String uzunluğu çok büyükse tek bir satıra sığmayabilir. String'in bir sonraki satırda devam edeceğini belirtmek için her satırın sonunda ters eğik çizgi karakterini (\\) kullanabiliriz.  
**Örnek:**

```js
//
const paragraph = "My name is Khatai";

console.log(paragraph);
```

#### String'lerdeki Kaçış Dizileri

JavaScript ve diğer programlama dillerinde \ (ters eğik çizgi ) ardından bazı karakterler kaçış dizisidir. En yaygın kaçış karakterlerini görelim:

- \n: yeni satır
- \t: Tab, 8 boşluk anlamına gelir ( klavyedeki tab tuşunu temsil eder )
- \\\\: Ters eğik çizgi
- \\': Tek Tırnak (')
- \\": Çift Tırnak (")

```js
// kodları console kısmına yazarak denerseniz daha iyi anlarsınız.
console.log(
  "Umarım herkes JavaScript'in 30 Günü yarışmasından keyif alıyordur."
); //  Buradakı \n satır sonu anlamına gelir sonrası aşağı iner
console.log("Günler\tKonular\tEgzersizler"); // Burada her kelimeden sonra bir tab (\t) tuşuna basılmış etkisi verir
console.log("Gün 1\t3\t5"); // \t bir başka örnek
console.log("Gün 2\t3\t5"); // \t bir başka örnek
console.log("Gün 3\t3\t5"); // \t bir başka örnek
console.log("Gün 4\t3\t5"); // \t bir başka örnek
console.log("This is a backslash  symbol (\\)"); // Ters eğik çizgi yazmak için \\ kullanılıyor
console.log('In every programming language it starts with "Hello, World!"'); // Hello World'ü çift tırnak içine almak için \" Hello World \" kullanılıyor.
console.log("In every programming language it starts with 'Hello, World!'"); // Hello World'ü tek tırnak içine almak için \' Hello World \' kullanılıyor.
console.log("The saying 'Seeing is Believing' isn't correct in 2020"); // Bu kısımdada alıntıları kullanmak için \ kullanımı gösterilmiş.
```

Konsol çıktıları :

```sh
"Umarım herkes JavaScript'in 30 Günü yarışmasından keyif alıyordur."
Günler Konular Egzersizler
Gün 1 3 5
Gün 2 3 5
Gün 3 3 5
Gün 4 3 5
Bu bir ters eğik çizgi simgesidir (\)
Her programlama dilinde "Merhaba Dünya!" ile başlar.
Her programlama dilinde 'Merhaba Dünya!' ile başlar.
2020'de 'Görmek inanmaktır' sözü doğru değil
```

#### Şablon Değişmezleri

Şablon string'leri oluşturmak için iki ters tırnak kullanıyoruz. Verileri bir şablon string'i içine ifade olarak ekleme yapabiliriz. Verileri eklemek için, ifadeyi $ (dolar) işareti ile başlayan bir küme parantezinin "{}" içine alırız. Aşağıdaki sözdizimine bakın.

```js
//Syntax
`String değişmez metni``String değişmez metni ${expression}`;
```

**Örnek : 1**

```js
console.log(`2 ve 3-ün toplamı beştir`); // statik bir veri
let a = 2;
let b = 3;
console.log(`${a} ve ${b}'nin toplamı ${a + b}`); // verileri dinamik olarak ekleme
```

**Örnek :2**

```js
// Bu kısımda yazar + kullanarak ekleme yapmanın diğer yöntemi olan  ekleme yöntemini gösteriyor. Bu daha stabil çalışıyor.
let firstName = "Khatai";
let lastName = "Huseynzade";
let country = "Azerbaijan";
let city = "Baku";
let fullName = firstName + " " + lastName;

let personInfoTwo = `I am ${fullName}. I am ${age}. I live in ${country}.`; // dize ekleme yöntemi
let personInfoThree = `I am ${fullName}. I live in ${city}, ${country}`;
console.log(personInfoTwo);
console.log(personInfoThree);
```

```sh
Ben Khatai Huseynzade. Ben Azerbaijanda yaşıyorum.
Ben Khatai Huseynzade. Ben Baku, Azerbaijanda yaşıyorum.
```

Bir string şablonu veya interpolasyon ( matematiksel bir terim ) yöntemi kullanarak, bir değer olabilecek ifadeler veya bazı işlemler ekleyebiliriz.(karşılaştırma, aritmetik işlemler, üçlü işlem)

```js
let a = 2;
let b = 3;
console.log(`${a} is greater than ${b}: ${a > b}`); // a b den büyüktür yazıyor ve  interpolasyon metodu bunun yanlış olduğunu söylecek
```

```sh
2 is greater than 3: false
```

### String Metodları

JavaScript'teki her şey bir nesnedir. Bir string ilkel veri türüyse bunu değiştiremeyiz. String bir nesnenin, birçok string metodu vardır. Birçok string metodu bulunmaktadır, bunlar string'ler ile çalışmamıza yardımcı olurlar. ( stringlerin özelliklerini vb bulma metodları bunlar Örneğe bakın)

1. _length_: String içerisindeki karakterlerin sayısını belirtir. Boşluklar dahildir.

**Örnek :**

```js
let js = "JavaScript";
console.log(js.length); // 10
let firstName = "Khatai";
console.log(firstName.length); // 8
```

2. _String'deki karakterlere erişim_: String içerisinde bulunan her karaktere indeks numarasıyla erişebiliriz. Programlamada sayma 0 dan başlar. String'in ilk dizini 0, son dizini ise toplam uzunluğun -1'dir. ( Kısaca 10 karakter varsa sıralama 0-9 arasında yapılıyor. Resme bakın daha iyi anlayacaksınız.)

![Dizine göre dizine erişme](../../images/string_indexes.png)

'JavaScript' string'indeki farklı karakterlere erişelim.

```js
let string = "JavaScript";
let firstLetter = string[0];

console.log(firstLetter); // J

let secondLetter = string[1]; // a
let thirdLetter = string[2];
let lastLetter = string[9];

console.log(lastLetter); // t

let lastIndex = string.length - 1;

console.log(lastIndex); // 9
console.log(string[lastIndex]); // t
```

3. _toUpperCase()_: bu metot string verisini büyük harflere dönüştürür.

```js
let string = "JavaScript";

console.log(string.toUpperCase()); // JAVASCRIPT

let firstName = "Khatai";

console.log(firstName.toUpperCase()); // KHATAI

let country = "Azerbaijan";

console.log(country.toUpperCase()); // AZERBAIJAN
```

4. _toLowerCase()_: bu metot string verisini küçük harflere dönüştürür.

```js
let string = "JavaSript";

console.log(string.toLowerCase()); // javascript

let firstName = "Khatai";

console.log(firstName.toLowerCase()); // khatai

let country = "Azerbaijan";

console.log(country.toLowerCase()); // azerbaijan
```

5. _substr()_: İki arrgüman alır, başlangıç indeksi ve silenecek karakter sayısı.

```js
let string = "JavaScript";
console.log(string.substr(4, 6)); // Script

let country = "Finland";
console.log(country.substr(3, 4)); // land
```

6. _substring()_: Başlangıç indeksi ve durma indeksi olmak üzere iki argüman almaktadır.

```js
let string = "JavaScript";

console.log(string.substring(0, 4)); // Java
console.log(string.substring(4, 10)); // Script
console.log(string.substring(4)); // Script

let country = "Finland";

console.log(country.substring(0, 3)); // Fin
console.log(country.substring(3, 7)); // land
console.log(country.substring(3)); // land
```

7. _split()_: Bu metot bir stringi belirtilen yerden bölmeye yarar. ( array oluşturuyor )

```js
let string = "30 Günde JavaScript";

console.log(string.split()); // bu kısımda birşey belirtmediğin için 1 elementli dizi oluştu -> ["30 Günde JavaScript"]
console.log(string.split(" ")); // bu kısımda boşluktan böl dediğimiz için 3 elementli dizi oluştu -> ["30", "Günde", "JavaScript"]

let firstName = "Khatai";

console.log(firstName.split()); // - > ["Khatai"]
console.log(firstName.split("")); // burada sadece tek tırnak kullandığımız için string'in içindeki tüm karakterleri array haline getirdi  ->  ["K", "h", "a", "t", "a", "i"]

let countries = "Finland, Azerbaijan, Norway, Denmark, and Iceland";

console.log(countries.split(",")); // Dikkat edin sadece virgül ile ayırıyor. İknci elementin solunda boşluk oluşuyor.  ["Finland", " Azerbaijan", " Norway", " Denmark", " and Iceland"]
console.log(countries.split(", ")); // Dikkat edin burayada. ', ' virgül ve boşluk bulunmakta bu yüzden elementleri virgülden ayırıp boşluklsuz arrray oluşturuyor.  ["Finland", "Azerbaijan", "Norway", "Denmark", "and Iceland"]
```

8. _trim()_: String'in başında ve sonundaki boşlukları silmeye yarar.

```js
let string = "   30 Günde JavaScript  ";

console.log(string);
console.log(string.trim(" "));

let firstName = " Khatai ";

console.log(firstName);
console.log(firstName.trim()); // içinde tırnak kullanmasanız dahi boşlukları siler
```

```sh
   30 Günde JavaScript
30 Günde JavaScript
  Khatai
Khatai
```

9. _includes()_: Bu metot string içerisinde varlık kontrolü yapmaya yarar. Eğer bulursa true, bulamazsa false döner. ( birebir arama yapar )

```js
let string = "30 Days Of JavaScript";

console.log(string.includes("Günde")); // true
console.log(string.includes("günde")); // false - birebir arama yapar!
console.log(string.includes("Script")); // true
console.log(string.includes("script")); // false
console.log(string.includes("java")); // false
console.log(string.includes("Java")); // true

let country = "Azerbaijan";

console.log(country.includes("aze")); // false
console.log(country.includes("Aze")); // true
console.log(country.includes("an")); // true
console.log(country.includes("An")); // false
```

10. _replace()_: Bu metot string içerisinde değiştirme yapmamızı sağlar. Eski ve Yeni olmak üzere iki argüman alır.

```js
string.replace(oldsubstring, newsubstring);
```

```js
let string = "30 Günde JavaScript";
console.log(string.replace("JavaScript", "Python")); // 30 Days Of Python

let country = "Azerbaijan";
console.log(country.replace("baijan", "noman")); // Azernoman
```

11. _charAt()_: Stringdeki indeksi belirttiğinizde o indeksin değerini yazdırır.

```js
string.charAt(index);
```

```js
let string = "30 Günde JavaScript";
console.log(string.charAt(0)); // 3 (0. indeksin değerini döndürdü)

let lastIndex = string.length - 1; // bu kısımda yukardaki değişkenin karakter sayısını alıyor (21) sonra bu sonucu 1 ile çıkartıyor sonuç 20. aşağı bak
console.log(string.charAt(lastIndex)); // pogramlamada sayma 0 dan başladığı için -1 yapıyor yukarıda console.log da çıkan sonuç "t" olacaktır. Buda 20. karakterdir. İnanmazsan say =) ama sıfırdan başlamayı unutma
```

12. _charCodeAt()_: String'teki vermiş olduğunuz index değerinin ASCII numarasını döndürür.

```js
string.charCodeAt(index);
```

```js
let string = "30 Günde JavaScript";
console.log(string.charCodeAt(3));

let lastIndex = string.length - 1;
console.log(string.charCodeAt(lastIndex)); // t ASCII  116
```

13. _indexOf()_: Bu metot belirtilen değerin indeksini verir. Değer bulunamazsa -1 sonucunu döndürür. ( Birebir arama yapar örneğe bakın )

```js
string.indexOf(substring);
```

```js
let string = "30 Günde JavaScript";

console.log(string.indexOf("G")); // 3
console.log(string.indexOf("Günde")); // 3
console.log(string.indexOf("günde")); // -1
console.log(string.indexOf("ü")); // 4
console.log(string.indexOf("JavaScript")); // 11
console.log(string.indexOf("Script")); //15
console.log(string.indexOf("script")); // -1
```

14. _lastIndexOf()_: Bu metot belirtilen değerin son değer indeksini verir. Değer bulunamazsa -1 sonucunu döndürür. ( Birebir arama yapar örneğe bakın )

```js
//syntax
string.lastIndexOf(substring);
```

```js
let string =
  "JavaScript'i seviyorum. JavaScript'i sevmiyorsanız, başka neleri sevebilirsiniz?";

console.log(string.lastIndexOf("seviyorum"));
console.log(string.lastIndexOf("JavaScript"));
console.log(string.lastIndexOf("başka"));
```

15. _concat()_: Bu metot birleştirme işlemini sağlar, birden fazla değer alabilir

```js
string.concat(substring, substring, substring);
```

```js
let string = "30";
console.log(string.concat("Günde", "JavaScript")); // 30GündeJavaScript

let country = "Aze";
console.log(country.concat("baijan")); // Azerbaijan
```

16. _startsWith_: String'in belirtilen değer ile başlayıp başlamadığını kontrol eder. true yada false döndürür.

```js
//syntax
string.startsWith(substring);
```

```js
let string = "Aşk bu dünyada en iyisidir";

console.log(string.startsWith("Aşk")); // true
console.log(string.startsWith("bu")); // false
console.log(string.startsWith("dünyada")); // false

let country = "Azerbaijan";

console.log(country.startsWith("Aze")); // true
console.log(country.startsWith("aze")); // false
console.log(country.startsWith("baijan")); //  false
```

17. _endsWith_: String'in belirtilen değer ile bitip bitmediğini kontrol eder. true yada false döndürür.

```js
string.endsWith(substring);
```

```js
let string = "Aşk bu dünyada en iyisidir";

console.log(string.endsWith("iyisidir")); // true
console.log(string.endsWith("aşk")); // false
console.log(string.endsWith("en iyisidir")); // true

let country = "Azerbaijan";

console.log(country.endsWith("baijan")); // true
console.log(country.endsWith("Aze")); // false
console.log(country.endsWith("aze")); //  false
```

18. _search_: Argüman olarak bir alt dize alır ve ilk eşleşmenin dizinini döndürür. Arama değeri bir dize veya normal ifade kalıbı olabilir.

```js
string.search(substring);
```

```js
let string =
  "JavaScript'i seviyorum. JavaScript'i sevmiyorsanız, başka neleri sevebilirsiniz?";
console.log(string.search("başka"));
console.log(string.search(/javascript/gi));
```

19. _match_: Argüman olarak bir alt dize veya normal ifade kalıbı alır ve eşleşme varsa bir dizi döndürür, değilse null döndürür. Normal bir ifade kalıbının nasıl göründüğünü görelim. / işareti ile başlar ve / işareti ile biter.

```js
let string = "başka";
let patternOne = /başka/; // koşulsuz
let patternTwo = /başka/gi; // g-bütün metinde ara, i - büyük küçük harf duyarsız
```

Match sözdizimi

```js
// sözdizimi
string.match(substring);
```

```js
let string =
  "JavaScript'i seviyorum. JavaScript'i sevmiyorsanız, başka neleri sevebilirsiniz?";
console.log(string.match("love"));
```

```sh
["başka", index: 52, input: "JavaScript'i seviyorum. JavaScript'i sevmiyorsanız, başka neleri sevebilirsiniz?.", groups: undefined]
```

```js
let pattern = /başka/gi;
console.log(string.match(pattern)); // ["başka"]
```

Normal bir ifade kullanarak metinden sayıları çıkaralım. Burası normal ifade bölümü değil, panik yapmayın! Düzenli ifadeleri daha sonra ele alacağız.

```js
let txt = "Ben 100 yıldır Azerbaycanda yaşıyorum";
let regEx = /\d+/;

// kaçış karakterli d, d'nin normal olmadığı anlamına gelir, d bunun yerine bir rakam gibi davranır
// + bir veya daha fazla basamaklı sayı anlamına gelir,
// ondan sonra g varsa global demektir, her yerde ara.

console.log(txt.match(regEx)); // ["1", "0", "0"]
console.log(txt.match(/\d+/g)); // ["100"]
```

20. _repeat()_: bağımsız değişken olarak bir sayı alır ve stringi sayı kadar döndürür.

```js
string.repeat(n);
```

```js
let string = "başka";
console.log(string.repeat(10)); // başkabaşkabaşkabaşkabaşkabaşkabaşkabaşkabaşkabaşka
```

## Veri Türlerini Kontrol Etme ve Döküm

### Veri Türlerini Kontrol Etme

Belirli bir değişkenin veri türünü kontrol etmek için _typeof_ yöntemini kullanırız.

**Örnek:**

```js
// Farklı javascript veri türleri
// Farklı veri tipleri tanımlayalım

let firstName = "Khatai"; // string
let lastName = "Yetayeh"; // string
let country = "Azerbaijan"; // string
let city = "Baku"; // string
let age = 250; // number,  benim gerçek yaşım değil merak etme
let job; // undefined, çünkü bir değer atanmamış

console.log(typeof "Khatai"); // string
console.log(typeof firstName); // string
console.log(typeof 10); // number
console.log(typeof 3.14); // number
console.log(typeof true); // boolean
console.log(typeof false); // boolean
console.log(typeof NaN); // number
console.log(typeof job); // undefined
console.log(typeof undefined); // undefined
console.log(typeof null); // object
```

### Veri Türünü Değiştirme

- Döküm: Bir veri tipini başka bir veri tipine dönüştürme. Kullandıklarımız _parseInt()_, _parseFloat()_, _Number()_, _+ sign_, _str()_
  Aritmetik işlemler yapmadan önce string sayıları önce integer yada float türüne dönüştürmeliyiz yoksa hata alırız.

#### String to Int

String bir numarayı sayıya dönüştürebiliriz. Alıntı içerisindeki herhangi bir sayı string numarasıdır. Bir string numarası örneği: '10', '5', vb.
Aşağıdaki metotları kullanarak string'i sayıya dönüştürebiliriz:

- parseInt()
- Number()
- Plus sign(+) // artı işareti demek

```js
let num = "10";
let numInt = parseInt(num);
console.log(numInt); // 10
```

```js
let num = "10";
let numInt = Number(num);

console.log(numInt); // 10
```

```js
let num = "10";
let numInt = +num;

console.log(numInt); // 10
```

#### String to Float

String içindeki ondalık numarayı sayıya çevirebiliriz. Tırnak içerisindeki ondalık sayı string ondalık sayıdır. Bir string ondalık numarası örneği: '9.81', '3.14', '1.44' vb.
Aşağıdaki metotları kullanarak ondalık stringi sayıya dönüştürebiliriz:

- parseFloat()
- Number()
- Plus sign(+)

```js
let num = "9.81";
let numFloat = parseFloat(num);

console.log(numFloat); // 9.81
```

```js
let num = "9.81";
let numFloat = Number(num);

console.log(numFloat); // 9.81
```

```js
let num = "9.81";
let numFloat = +num;

console.log(numFloat); // 9.81
```

#### Float to Int

Ondalık sayıları tam sayılara çevirebiliriz. (Int) ( bu aşağıya yuvarlıyor )
Float'ı int'e dönüştürmek için aşağıdaki metodu kullanıyoruz:

- parseInt()

```js
let num = 9.81;
let numInt = parseInt(num);

console.log(numInt); // 9
```

🌕 Harikasın!. 2. gün zorluklarını yeni tamamladınız ve mükemmelliğe giden yolda iki adım öndesiniz. Şimdi beyniniz ve kasınız için bazı egzersizler yapın.

## 💻 Gün 2: Egzersizleri

### Egzersiz: Seviye 1

1. Challenge adında bir değişken tanımlayın ve **'30 Günde JavaScript'** başlangıç ​​değerine atayın.
2. **console.log()** kullanarak tarayıcı konsolunda değişkeni yazdırın,
3. _console.log()_ kullanarak tarayıcı konsolunda dizenin **length** değerini yazdırın,
4. **toUpperCase()** yöntemini kullanarak tüm dize karakterlerini büyük harflerle değiştirin,
5. **toLowerCase()** yöntemini kullanarak tüm dize karakterlerini küçük harflerle değiştirin,
6. **substr()** veya **substring()** yöntemini kullanarak string'in ilk kelimesini kesin-silin (dilimleyin)
7. _Günde JavaScript_ ifadesini _30 Günde JavaScript_'ten ayırın.
8. **includes()** yöntemini kullanarak string'in **Script** kelimesini içerip içermediğini kontrol edin
9. **split()** yöntemini kullanarak **string** öğesini bir **array**'ye bölün
10. 30 Günde JavaScript dizesini **split()** yöntemini kullanarak boşlukta bölün
11. 'Facebook, Google, Microsoft, Apple, IBM, Oracle, Amazon' dizeyi virgülden **split** ve bir dizi olarak değiştirin.
12. **replace()** yöntemini kullanarak 30 Günde JavaScript'i 30 Days of Python olarak değiştirin.
13. 'JavaScript'in 30 Günü' dizesinde dizin 15'teki karakter nedir? **charAt()** yöntemini kullanın.
14. **charCodeAt()** kullanan 'JavaScript'in 30 Günü' dizesindeki J karakter kodu nedir?
15. 30 Günde JavaScript'te **a** öğesinin ilk oluşumunun konumunu belirlemek için **indexOf** kullanın
16. 30 Günde JavaScript'te **a** öğesinin son oluşumunun konumunu belirlemek için **lastIndexOf** kullanın.
17. Aşağıdaki cümlede **çünkü** kelimesinin ilk geçtiği yeri bulmak için **indexOf** kullanın:
    **'Bir cümleyi çünkü ile bitiremezsiniz çünkü çünkü bir bağlaçtır'**
18. Aşağıdaki cümlede **çünkü** kelimesinin son geçtiği yeri bulmak için **lastIndexOf** kullanın:
    **'Bir cümleyi çünkü ile bitiremezsiniz çünkü çünkü bir bağlaçtır'**
19. Aşağıdaki cümlede **çünkü** kelimesinin ilk geçtiği yeri bulmak için **search** kullanın:
    **'Bir cümleyi çünkü ile bitiremezsiniz çünkü çünkü bir bağlaçtır'**
20. Bir dizgenin başındaki ve sonundaki boşlukları kaldırmak için **trim()** kullanın. Örneğin '30 Günde JavaScript'.
21. _30 Günde JavaScript_ dizesiyle **startsWith()** yöntemini kullanın ve sonucu doğru yapın
22. _30 Günde JavaScript_ dizesiyle **endsWith()** yöntemini kullanın ve sonucu doğru yapın
23. JavaScript'in 30 Günü'ndeki tüm **a**'leri bulmak için **match()** yöntemini kullanın
24. **concat()** kullanın ve '30 Days of' ve 'JavaScript'i tek bir dize olan '30 Günde JavaScript' ile birleştirin
25. 30 Günde JavaScript'i 2 kez yazdırmak için **repeat()** yöntemini kullanın

### Egzersiz: Seviye 2

1. console.log() kullanarak aşağıdaki ifadeyi yazdırın:

   ```sh
   Alıntı 'Kalp için aşağı uzanıp insanları kaldırmaktan daha iyi bir egzersiz yoktur.' John Holmes bize birbirimize yardım etmeyi öğretiyor.
   ```

2. console.log()'u kullanarak Rahibe Teresa'nın aşağıdaki alıntısını yazdırın:

   ```sh
   "Aşk patronluk taslamak değildir ve hayırseverlik merhametle ilgili değildir, aşkla ilgilidir. Hayırseverlik ve sevgi aynıdır - hayırseverlikle sevgi verirsiniz, bu yüzden sadece para vermeyin, onun yerine elinizi uzatın."
   ```

3. '10' tipinin tam olarak 10'a eşit olup olmadığını kontrol edin. Değilse tam olarak eşit yapın.
4. parseFloat('9.8') 10'a tam olarak eşit değilse, 10'a eşit olup olmadığını kontrol edin.
5. Hem python hem de jargonda 'on' ifadesinin bulunup bulunmadığını kontrol edin
6. _Umarım bu kurs jargonla dolu değildir_. Cümlede _jargon_ olup olmadığını kontrol edin.
7. 0 ile 100 arasında rastgele bir sayı üretin.
8. 50 ile 100 arasında rastgele bir sayı üretin.
9. Dahil olmak üzere 0 ile 255 arasında rastgele bir sayı oluşturun.
10. Rastgele bir sayı kullanarak 'JavaScript' dize karakterlerine erişin.
11. Aşağıdaki kalıbı yazdırmak için console.log() ve kaçış karakterlerini kullanın.

    ```js
    1 1 1 1 1
    2 1 2 4 8
    3 1 3 9 27
    4 1 4 16 64
    5 1 5 25 125
    ```

12. **substr** kullanarak **çünkü çünkü** ifadesini aşağıdaki cümleden ayırın:**'Bir cümleyi çünkü ile bitiremezsiniz çünkü çünkü bir bağlaçtır'**

### Egzersiz: Seviye 3

1. 'Aşk bu dünyadaki en iyi şeydir. Bazıları aşkını buldu ve bazıları hala aşkını arıyor.' Bu cümledeki **love** kelimesini sayın.
2. Aşağıdaki cümledeki tüm **çünkü** sayısını saymak için **match()** kullanın:**'Bir cümleyi çünkü ile bitiremezsiniz çünkü çünkü bir bağlaçtır'**
3. Aşağıdaki metni temizleyin ve en sık kullanılan kelimeyi bulun (ipucu, değiştirme ve normal ifadeleri kullanın).

   ```js
   const sentence =
     "%I $am@% a %tea@cher%, &and& I lo%#ve %te@a@ching%;. The@re $is no@th@ing; &as& mo@re rewarding as educa@ting &and& @emp%o@weri@ng peo@ple. ;I found tea@ching m%o@re interesting tha@n any ot#her %jo@bs. %Do@es thi%s mo@tiv#ate yo@u to be a tea@cher!? %Th#is 30#Days&OfJavaScript &is al@so $the $resu@lt of &love& of tea&ching";
   ```

4. Aşağıdaki metinden sayıları çıkararak kişinin yıllık toplam gelirini hesaplayın.

'Aylık maaşından 5000 euro, yıllık 10000 euro ikramiye, ayda 15000 euro online kurstan kazanıyor.'

🎉 TEBRİKLER ! 🎉

[<< Gün 1](../01_Gün_Giriş/01_gün_giriş.md) | [Gün 3 >>](../03_Gün_Boole-değerleri_Operatörler_Tarih-objesi/03_gün_boole-değerleri_operatörler_tarih-objesi.md)
