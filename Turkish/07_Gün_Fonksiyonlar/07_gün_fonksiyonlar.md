<div align="center">
<h1> 30 günde JavaScript: - Fonksiyonlar</h1>

<a class="header-badge" target="_blank" href="https://twitter.com/developerkhatai">
<img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/developerkhatai?style=social">
</a><br>

<sub>Yazar:
<a href="github.com/bilgegates">Khatai Huseynzade</a><br>
<small> Temmuz, 2022</small>
</sub>

</div>

[<< Gün 6](../06_Gün_Döngüler/06_gün_döngüler.md) | [Gün 8 >>](../08_Gün_Nesneler/08_gün_nesneler.md)

- [📔 Gün 7](#📔Gün-7)
  - [ Fonksiyonlar](#Fonksiyonlar)
    - [Klasik fonksiyon tanımlama](#Klasik-fonksiyon-tanımlama)
      - [İsimsiz Fonksiyon](#İsimsiz-fonksiyon)
        - [İfade Fonksiyon](#İfade-fonksiyon)
    - [Parametresiz ve dönüş değeri olmayan fonksiyon](#Parametresiz-ve-dönüş-değeri-olamayan-fonksiyon)
    - [Fonksiyonlarda return kullanımı](#Fonksiyonlarda-return-kullanımı)
    - [Bir parametreli fonksiyon](#Parametreli-fonksiyon)
    - [İki parametreli fonksiyon](#İki-parametreli-fonksiyon)
    - [Çok parametreli fonksiyon](#Çok-parametreli-fonksiyon)
    - [Sınırsız sayıda parametreyle çalışan fonksiyon](#Sınırsız-sayıda-parametreyle-çalışan-fonksiyon)
      - [Klasik fonksiyonda sınırsız sayıda parametre](#Klasik-fonksiyonda-sınırsız-sayıda-parametre)
    - [Kendi-Kendine Çağırılan Fonksiyon ](#Kendi-kendine-çağırılan-fonksiyon)
    - [Ok Fonksiyonu](#OK-fonksiyonu)
    - [Ok Fonksiyonunda sınırsız sayıda parametre](#Ok-Fonksiyonunda-sınırsız-sayıda-parametre)
    - [Default parametre ile fonksiyon kullanımı](#default-parametre-ile-fonksiyon-kullanımı)
    - [Function declaration versus Arrow function](#function-declaration-versus-arrow-function)
  - [💻 Gün 7: Egzersizleri](#💻Gün-7-Egzersizleri)
    - [Egzersiz: Seviye 1](#egzersiz-seviye-1)
    - [Egzersiz: Seviye 2](#egzersiz-seviye-2)
    - [Egzersiz: Seviye 3](#egzersiz-seviye-3)

# 📔 Gün 7

## Fonksiyonlar

Şimdiye kadar birçok JavaScript fonksiyonu yazdık. Bu bölümde, custom fonksiyonlara odaklanacağız. Fonksiyon yazmaya başlamadan önce, fonksiyonun ne olduğunu ve neden fonksiyona ihtiyacımız olduğunu bakalım.

Bir fonksiyon, belirli bir görevi gerçekleştirmek üzere tasarlanmış ve yeniden kullanılabilir bir kod bloğu veya programlama tanımıdır.

Bir fonksiyon, `function` anahtar kelimesi ardından gelen o fonksiyona ait fonksiyon ismi ve parantezler ile tanımlanır. Bu paranteler fonksiyona parametre atayabilmemizi sağlar. Şayet fonksiyon parametre alırsa bu parametre fonksiyon scope'u içerisinde geçerli olan bir değişkendir. Farklı bir kullanım olarak da bu parametreye default değerler atayabiliriz. Eğer bir fonksiyon yardımı ile veri taşımak istiyorsak söz konusu fonksiyonun belirli bir veri türünü geriye değişken olarak döndürmesi gerekir. Daha sonra dönen bu değişkeni bir başka değişkene atayarak kullanabilir.

Fonksiyon kullanmanın avantajları:

- temiz ve okunması kolay
- yeniden kullanılabilir
- kolay test edilir

Bir fonksiyon birkaç şekilde tanımlanabilir:

- _Klasik Declaration function_
- _Expression function_
- _Anonymous function_
- _Arrow function_

### Klasik Fonksiyon Tanımlama

Bir fonksiyonun nasıl tanımlanacağını ve çağırılacağını görelim.

```js
//parametresiz fonksiyon tanımıı
function functionName() {
  // istenilen kod parçası
}
functionName(); // fonksiyon, fonksiyon adı ve parantezler ile çağırılır
```

### İsimsiz Fonksiyon

```js
const anonymousFun = function () {
  console.log("İsimsiz bir fonksiyonum ve değerim anonim olarak saklanıyor");
};
```

### İfade Fonksiyonu

Expression function, isimsiz fonksiyonlardır. İsimsiz bir fonksiyon oluşturduktan sonra bir değişkene atayarak kullanırız. Fonksiyondan bir değer geri döndürmek için değişkeni çağırmalıyız. Örnek vemrek gerekirse.

```js
// Function expression
const square = function () {
  console.log("Bu bir expression function türünde fonksiyondur");
};
```

### Parametresiz ve dönüş değeri olamayan fonksiyon

Fonksiyon, parametre olmadan tanımlanabilir. (Şu ana kadar tanımladıklarımız zaten parametresizdi)

**Example:**

```js
function square() {
  let num = 2;
  let square = num * num;
  console.log(square);
}

square(); // 4

// parametresiz fonksiyon örnek 2:
function addTwoNumbers() {
  let numOne = 10;
  let numTwo = 20;
  let sum = numOne + numTwo;

  console.log(sum);
}

addTwoNumbers(); // fonksiyon, kendisine verilen isim ile çağırılmalı
```

```js
function printFullName() {
  let firstName = "Asabeneh";
  let lastName = "Yetayeh";
  let space = " ";
  let fullName = firstName + space + lastName;
  console.log(fullName);
}

printFullName(); // fonksiyon çağırımına bir örnek
```

### Bir değer döndüren fonksiyon

Fonksiyonlar geriye bir değer döndürebilir. bu işlemi `return` anahtar kelimesini kullanarak sağlarız. Normal fonksiyondan farklı olarak bir field'a atanabilir veya bir metot içerisinde parametre olarak kullanılabilir.

```js
function printFullName() {
  let firstName = "Asabeneh";
  let lastName = "Yetayeh";
  let space = " ";
  let fullName = firstName + space + lastName;
  return fullName;
}
console.log(printFullName());
```

```js
function addTwoNumbers() {
  let numOne = 2;
  let numTwo = 3;
  let total = numOne + numTwo;
  return total;
}

console.log(addTwoNumbers());
```

### Parametreli fonksiyon

Bir fonksiyonda farklı veri türlerini (number, string, boolean, object, function) parametre olarak geçebiliriz.

```js
// bir parametreli fonksiyon
function functionName(parm1) {
  // istenilen kod parçası
}
functionName(parm1); // fonksiyonu çağırma sırasında parantezler arasına bir parametreye ihtiyaç duyar

function areaOfCircle(r) {
  let area = Math.PI * r * r;
  return area;
}

console.log(areaOfCircle(10)); // bağımsız bir değişkenle çağırılmalı

function square(number) {
  return number * number;
}

console.log(square(10));
```

### İki parametreli fonksiyon

```js
// iki parametreli fonksiyon
function functionName(parm1, parm2) {
  //istenilen kod parçası
}
functionName(parm1, parm2); //fonksiyonu çağırma sırasında parantezler arasında iki tane parametreye ihtiyaç duyar

// Parametresiz fonksiyon giriş yapmaz, bu nedenle parametrelerle bir fonksiyon yapalım
function sumTwoNumbers(numOne, numTwo) {
  let sum = numOne + numTwo;
  console.log(sum);
}
sumTwoNumbers(10, 20); // fonksiyon çağırımı
// Bir fonksiyon değer döndürmezse veri depolayamaz, bu nedenle değer döndürmelidir.

function sumTwoNumbers(numOne, numTwo) {
  let sum = numOne + numTwo;
  return sum;
}

console.log(sumTwoNumbers(10, 20));
function printFullName(firstName, lastName) {
  return `${firstName} ${lastName}`;
}
console.log(printFullName("Asabeneh", "Yetayeh"));
```

### Çok parametreli fonksiyon

```js
// çok parametreli fonksiyon
function functionName(parm1, parm2, parm3,...){
  //istenilen kod parçası
}
functionName(parm1,parm2,parm3,...) // fonksiyon çağırımı sırasında birden çok parametreye ihtiyaç duyar


// bu fonksiyon, bir diziyi parametre olarak alır ve dizideki sayıları toplar
function sumArrayValues(arr) {
  let sum = 0;
  for (let i = 0; i < arr.length; i++) {
    sum = sum + arr[i];
  }
  return sum;
}
const numbers = [1, 2, 3, 4, 5];
    //fonksiyon çağırımı
console.log(sumArrayValues(numbers));


    const areaOfCircle = (radius) => {
      let area = Math.PI * radius * radius;
      return area;
    }
console.log(areaOfCircle(10))

```

### Sınırsız sayıda parametreyle çalışan fonksiyon

Fonksiyonlarla çalışırken kaç tane parametre gerekebileceğini bilemeyebiliriz. Javascript'te bu durumda bize sınırsız sayıda parametre alan fonksiyon yazabilme imkanı tanır. Bu şekilde bir fonksiyon tanımlamanın iki yolu vardır.

#### Klasik fonksiyonda sınırsız sayıda parametre

A function declaration provides a function scoped arguments array like object. Any thing we passed as argument in the function can be accessed from arguments object inside the functions. Let us see an example

Bu fonksiyonun tanımlanmasını fonksiyon scope'nda object temelli arguments anahtar kelimesi ile erişilir. Parametre olarak atanan her öğeye arguments üzerinden ulaşabiliriz. Bir örneğine bakmak gerekirse;

```js
// arguments nesnesine erişelim
​
function sumAllNums() {
 console.log(arguments)
}

sumAllNums(1, 2, 3, 4)
// Arguments(4) [1, 2, 3, 4, callee: ƒ, Symbol(Symbol.iterator): ƒ]

```

```js
// fonksiyon tanımı
​
function sumAllNums() {
  let sum = 0
  for (let i = 0; i < arguments.length; i++) {
    sum += arguments[i]
  }
  return sum
}

console.log(sumAllNums(1, 2, 3, 4)) // 10
console.log(sumAllNums(10, 20, 13, 40, 10))  // 93
console.log(sumAllNums(15, 20, 30, 25, 10, 33, 40))  // 173
```

> Arrow function'da sınırsız sayıda parametre konusunu Arraw fonksiyonu gördükten sonra görebilirsiniz.

### Kendi-kendine çağırılan fonksiyon

JavaScript sözdiziminde birçok ilginç şey vardır, bunlardan biri kendi kendine çalışan (kendi kendini çağıran) fonksiyonların tanımıdır. Böyle bir fonksiyonu şu şekilde tanımlayabiliriz:

```js
(function (n) {
  console.log(n * n);
})(2); // 4, but instead of just printing if we want to return and store the data, we do as shown below

let squaredNum = (function (n) {
  return n * n;
})(10);

console.log(squaredNum);
```

Yukarıdaki fonksiyon, tanımlandıktan hemen sonra çağrılır. Kendi kendini çağıran işlevlerin yararı, global ad alanını karıştırmadan (herhangi bir global bildirmeden) kodu bir kez yürütmemize olanak vermeleridir.

### Ok Fonksiyonu

Klasik fonksiyona alternatif olarak kullanılan arrow function sözdiziminde ufak bir farklılık vardır. `function` anahtar kelimesi yerine `=>` işareti kullanılır.

Sırasıyla aynı fonksiyonun klasik ve arrow function halini yazalım

```js
function square(n) {
  return n * n;
}

console.log(square(2)); // 4

const square = (n) => {
  return n * n;
};

console.log(square(2)); // -> 4

// kod bloğumuzda sadece bir satır kod varsa bu fonksiyon şu şekilde yazılabilir.
const square = (n) => n * n; // -> 4
```

```js
const changeToUpperCase = (arr) => {
  const newArr = [];
  for (const element of arr) {
    newArr.push(element.toUpperCase());
  }
  return newArr;
};

const countries = ["Finland", "Sweden", "Norway", "Denmark", "Iceland"];
console.log(changeToUpperCase(countries));

// ["FINLAND", "SWEDEN", "NORWAY", "DENMARK", "ICELAND"]
```

```js
const printFullName = (firstName, lastName) => {
  return `${firstName} ${lastName}`;
};

console.log(printFullName("Asabeneh", "Yetayeh"));
```

Yukarıdaki fonksiyon yalnızca geri dönüş ifadesine sahiptir, bu nedenle bunu aşağıdaki şekilde açıkça iade edebiliriz.

```js
const printFullName = (firstName, lastName) => `${firstName} ${lastName}`;

console.log(printFullName("Asabeneh", "Yetayeh"));
```

#### OK Fonksiyonunda sınırsız sayıda parametre

Arrow function, klasik fonksiyon gibi arguments nesnesine sahip değildir. Arrow function'da sınırsız sayıda parametre kullanmak istersek spread operatör (...) ve hemen ardından parametre adı kullanılır. Fonksiyonda bağımsız değişken olarak geçtiğimiz her şeye arrow functionda dizi olarak erişilebilir. Bir örnek görelim

```js
// arguments nesnesine erişmemize bir örnek
​
const sumAllNums = (...args) => {
 // console.log(arguments), arguments nesnesi bulunamadı
 // bunun yerine spread operator (...) ve parametre adı kullanalım
 console.log(args)
}

sumAllNums(1, 2, 3, 4)
// [1, 2, 3, 4]

```

```js
// function declaration
​
const sumAllNums = (...args) => {
  let sum = 0
  for (const element of args) {
    sum += element
  }
  return sum
}

console.log(sumAllNums(1, 2, 3, 4)) // 10
console.log(sumAllNums(10, 20, 13, 40, 10))  // 93
console.log(sumAllNums(15, 20, 30, 25, 10, 33, 40))  // 173
```

### Default parametre ile fonksiyon kullanımı

Bazen parametrelere default değerler geçmek isteyebiliriz. Bu durumda fonksiyon çağırımı sırasında söz konusu parametreyi vermek zorunda olmadan kullanabiliriz. Eğer bu parametreyi vermezsek fonksiyon işlevinin parametrenin default değerini kullanarak tamamlayacaktır.

```js
// syntax - söz dizimi
// fonksiyon tanımı
function functionName(param = value) {
  //codes
}

// fonksiyon çağırımı
functionName();
functionName(arg);
```

**Example:**

```js
function greetings(name = "Peter") {
  let message = `${name}, welcome to 30 Days Of JavaScript!`;
  return message;
}

console.log(greetings());
console.log(greetings("Asabeneh"));
```

```js
function generateFullName(firstName = "Asabeneh", lastName = "Yetayeh") {
  let space = " ";
  let fullName = firstName + space + lastName;
  return fullName;
}

console.log(generateFullName());
console.log(generateFullName("David", "Smith"));
```

```js
function calculateAge(birthYear, currentYear = 2019) {
  let age = currentYear - birthYear;
  return age;
}

console.log("Age: ", calculateAge(1819));
```

```js
function weightOfObject(mass, gravity = 9.81) {
  let weight = mass * gravity + " N"; // değer önce dize olarak değiştirilmelidir
  return weight;
}

console.log("Weight of an object in Newton: ", weightOfObject(100)); // 9.81 Dünya yüzeyinde yerçekimi
console.log("Weight of an object in Newton: ", weightOfObject(100, 1.62)); // Ay yüzeyinde yerçekimi
```

Yukarıdaki fonksiyonları bir de arrow function kullanarak tanımlayalım

```js
// syntax -  söz dizimi
// fonksiyonu tanımlama
const functionName = (param = value) => {
  //codes
};

// fonksiyonu çağırma
functionName();
functionName(arg);
```

**Example:**

```js
const greetings = (name = "Peter") => {
  let message = name + ", welcome to 30 Days Of JavaScript!";
  return message;
};

console.log(greetings());
console.log(greetings("Asabeneh"));
```

```js
const generateFullName = (firstName = "Asabeneh", lastName = "Yetayeh") => {
  let space = " ";
  let fullName = firstName + space + lastName;
  return fullName;
};

console.log(generateFullName());
console.log(generateFullName("David", "Smith"));
```

```js
const calculateAge = (birthYear, currentYear = 2019) => currentYear - birthYear;
console.log("Age: ", calculateAge(1819));
```

```js
const weightOfObject = (mass, gravity = 9.81) => mass * gravity + " N";

console.log("Weight of an object in Newton: ", weightOfObject(100)); // 9.81 Dünya yüzeyinde yerçekimi
console.log("Weight of an object in Newton: ", weightOfObject(100, 1.62)); // Ay yüzeyinde yerçekimi
```

🌕 Serinin 7. gününü de başarıyla tamamladın. Durmak yok yola devam!

## 💻 Gün 7: Egzersizleri

### Egzersiz: Seviye 1

1. _fullName_ işlevini bildirin ve tam adınızı yazdırın.
2. Bir _fullName_ işlevi bildirin ve şimdi firstName, lastName'i parametre olarak alır ve tam adınızı döndürür.
3. _addNumbers_ işlevini bildirin ve iki iki parametre alır ve toplamı döndürür.
4. Dikdörtgenin alanı şu şekilde hesaplanır: _alan = uzunluk x genişlik_. _areaOfRectangle_ değerini hesaplayan bir fonksiyon yazın.
5. Bir dikdörtgenin çevresi şu şekilde hesaplanır: _çevre= 2x(uzunluk + genişlik)_. _perimeterOfRectangle_ değerini hesaplayan bir fonksiyon yazın.
6. Dikdörtgenler prizmasının hacmi şu şekilde hesaplanır: _hacim = uzunluk x genişlik x yükseklik_. _volumeOfRectPrism_ değerini hesaplayan bir fonksiyon yazın.
7. Dairenin alanı şu şekilde hesaplanır: _alan = π x r x r_. _areaOfCircle_ değerini hesaplayan bir fonksiyon yazın
8. Bir dairenin çevresi şu şekilde hesaplanır: _çevre = 2πr_. _circumOfCircle_'ı hesaplayan bir işlev yazın
9. Bir maddenin yoğunluğu şu şekilde hesaplanır:_yoğunluk= kütle/hacim_. _yoğunluğu_ hesaplayan bir fonksiyon yazın.
10. Hız, hareketli bir nesnenin kat ettiği toplam mesafenin, alınan toplam süreye bölünmesiyle hesaplanır. Hareket eden bir nesnenin hızını hesaplayan bir fonksiyon yazın, _hız_.
11. Bir maddenin ağırlığı şu şekilde hesaplanır: _ağırlık = kütle x yerçekimi_. _ağırlığı_ hesaplayan bir fonksiyon yazın.
12. oC cinsinden sıcaklık, şu formül kullanılarak oF'ye dönüştürülebilir: _oF = (oC x 9/5) + 32_. oC'yi oF _convertCelsiusToFahrenheit_'a çeviren bir fonksiyon yazın.
13. Vücut kitle indeksi (VKİ) şu şekilde hesaplanır: _bmi = Kg cinsinden ağırlık / m2 cinsinden (boy x boy). \_bmi_ hesaplayan bir fonksiyon yazın. BMI, 20 yaş ve üzerindeki yetişkinlerde farklı ağırlık gruplarını geniş bir şekilde tanımlamak için kullanılır. Aşağıda verilen bilgilere göre bir kişinin _zayıf, normal, fazla kilolu_ veya _obez_ olup olmadığını kontrol edin.

    - Aynı gruplar hem erkekler hem de kadınlar için geçerlidir.
    - _Düşük kilolu_: BMI 18,5'ten az
    - _Normal ağırlık_: BMI 18,5 ila 24,9
    - _Fazla kilolu_: BMI 25 ila 29,9
    - _Obez_: BMI 30 veya daha fazla

14. _checkSeason_ adlı bir işlev yazın, bir aylık parametre alır ve sezonu döndürür: Sonbahar, Kış, İlkbahar veya Yaz.
15. Math.max en büyük bağımsız değişkenini döndürür. Math.max yöntemini kullanmadan üç bağımsız değişken alan ve bunların maksimum değerini döndüren bir findMax işlevi yazın.

    ```js
    console.log(findMax(0, 10, 5));
    10;
    console.log(findMax(0, -10, -2));
    0;
    ```

### Egzersiz: Seviye 2

1.  Doğrusal denklem şu şekilde hesaplanır: _ax + by + c = 0_. _solveLinEquation_ adlı doğrusal bir denklemin değerini hesaplayan bir fonksiyon yazın.
2.  İkinci dereceden denklem şu şekilde hesaplanır: _ax2 + bx + c = 0_. İkinci dereceden bir denklem olan _solveQuadEquation_'ın değerini veya değerlerini hesaplayan bir fonksiyon yazın.

    ```js
    console.log(solveQuadratic()); // {0}
    console.log(solveQuadratic(1, 4, 4)); // {-2}
    console.log(solveQuadratic(1, -1, -2)); // {2, -1}
    console.log(solveQuadratic(1, 7, 12)); // {-3, -4}
    console.log(solveQuadratic(1, 0, -4)); //{2, -2}
    console.log(solveQuadratic(1, -1, 0)); //{1, 0}
    ```

3.  _printArray_ işlev adını bildirin. Diziyi parametre olarak alır ve dizinin her değerini yazdırır.
4.  Date nesnesini kullanarak zamanı şu biçimde gösteren bir işlev adı _showDateTime_ yazın: 08/01/2020 04:08.

    ```ş
    showDateTime()
    08/01/2020 04:08
    ```

5.  Bir işlev adı _swapValues_ bildirin. Bu işlev, x'in değerini y'ye değiştirir.

    ```js
    takasDeğerleri(3, 4); // x => 4, y=>3
    takasDeğerleri(4, 5); // x = 5, y = 4
    ```

6.  _reverseArray_ işlev adını bildirin. Diziyi parametre olarak alır ve dizinin tersini döndürür (yöntem kullanmayın).

    ```js
    console.log(reverseArray([1, 2, 3, 4, 5]));
    //[5, 4, 3, 2, 1]
    console.log(reverseArray(["A", "B", "C"]));
    //['C', 'B', 'A']
    ```

7.  Bir işlev adı _capitalizeArray_ bildirin. Diziyi parametre olarak alır ve - büyük harfli diziyi döndürür.
8.  Bir işlev adı _addItem_ bildirin. Bir öğe parametresi alır ve öğeyi ekledikten sonra bir dizi döndürür
9.  _removeItem_ işlev adını bildirin. Bir indeks parametresi alır ve bir öğeyi çıkardıktan sonra bir dizi döndürür
10. Bir işlev adı _sumOfNumbers_ bildirin. Bir sayı parametresi alır ve o aralıktaki tüm sayıları toplar.
11. Bir işlev adı _sumOfOdds_ bildirin. Bir sayı parametresi alır ve o aralıktaki tüm tek sayıları toplar.
12. Bir işlev adı _sumOfEven_ bildirin. Bir sayı parametresi alır ve o aralıktaki tüm çift sayıları toplar.
    1.evensAndOdds bir işlev adı bildirin. Parametre olarak pozitif bir tamsayı alır ve sayıdaki çiftleri ve tekleri sayar.

        ```ş
        çiftlerVeOdds(100);
        Oran sayısı 50'dir.
        Çiftlerin sayısı 51'dir.
        ```

13. Herhangi bir sayıda argüman alan ve argümanların toplamını döndüren bir fonksiyon yazın.

    ```js
    toplam(1, 2, 3); // -> 6
    toplam(1, 2, 3, 4); // -> 10
    ```

14. Bir _randomUserIp_ oluşturan bir işlev yazın.
15. _randomMacAddress_ üreten bir işlev yazın
16. _randomHexaNumberGenerator_ adlı bir işlev adı bildirin. Bu işlev çağrıldığında rastgele bir onaltılık sayı üretir. İşlev onaltılık sayıyı döndürür.

    ```ş
    console.log(randomHexaNumberGenerator());
    "#ee33df"
    ```

17. _userIdGenerator_ adlı bir işlev adı bildirin. Bu fonksiyon çağrıldığında yedi karakterlik bir id üretir. İşlev kimliği döndürür.

    ```ş
    console.log(userIdGenerator());
    41XTDbE
    ```

### Egzersiz: Seviye 3

1. _userIdGenerator_ işlevini değiştirin. _userIdGeneratedByUser_ işlev adını bildirin. Herhangi bir parametre almaz, ancak prompt() kullanarak iki girdi alır. Girdilerden biri karakter sayısı, ikinci girdi ise üretilmesi gereken id sayısıdır.

   ```ş
   userIdGeneratedByUser()
   'kcsy2
   SMFYb
   bWmeq
   ZXOYh
   2Rgxf
   '
   userIdGeneratedByUser()
   '1GCSgPLMaBAVQZ26
   YD7eFwNQKNs7qXaT
   ycArC5yrRupyG00S
   UbGxOFI7UXSWAyKN
   diV0SSUTgAdKwStr
   '
   ```

2. Bir işlev adı _rgbColorGenerator_ yazın ve rgb renkleri üretir.

   ```ş
   rgbColorGenerator()
   RGB(125.244.255)
   ```

3. Bir dizide herhangi bir sayıda onaltılık renk döndüren bir **_arrayOfHexaColors_** işlevi yazın.
4. Bir dizide herhangi bir sayıda RGB rengi döndüren bir **_arrayOfRgbColors_** işlevi yazın.
5. Hexa rengini rgb'ye dönüştüren ve bir rgb rengi döndüren bir **_convertHexaToRgb_** işlevi yazın.
6. rgb'yi hexa rengine dönüştüren ve bir hexa rengi döndüren bir **_convertRgbToHexa_** işlevi yazın.
7. Herhangi bir sayıda hexa veya rgb rengi üretebilen bir **_generateColors_** işlevi yazın.

   ```js
   console.log(generateColors("hexa", 3)); // ['#a3e12f', '#03ed55', '#eb3d2b']
   console.log(generateColors("hexa", 1)); // '#b334ef'
   console.log(generateColors("rgb", 3)); // ['rgb(5, 55, 175)', 'rgb(50, 105, 100)', 'rgb(15, 26, 80)']
   console.log(generateColors("rgb", 1)); // 'rgb(33,79, 176)'
   ```

8. İşlevinizi _shuffleArray_ olarak adlandırın, parametre olarak bir dizi alır ve karıştırılmış bir dizi döndürür
9. İşlevinizi _factorial_ olarak adlandırın, parametre olarak bir tam sayı alır ve sayının bir faktöriyelini döndürür.
10. Fonksiyonunuzu _isEmpty_ olarak adlandırın, bir parametre alır ve boş olup olmadığını kontrol eder.
11. İşlevinizi _sum_ olarak adlandırın, herhangi bir sayıda argüman alır ve toplamı döndürür.
12. _sumOfArrayItems_ adlı bir işlev yazın, bir dizi parametresi alır ve tüm öğelerin toplamını döndürür. Tüm dizi öğelerinin sayı türleri olup olmadığını kontrol edin. Değilse, makul geri bildirimde bulunun.
13. _average_ adlı bir işlev yazın, bir dizi parametresi alır ve öğelerin ortalamasını döndürür. Tüm dizi öğelerinin sayı türleri olup olmadığını kontrol edin. Değilse, makul geri bildirimde bulunun.
14. _modifyArray_ adlı bir işlev yazın, diziyi parametre olarak alır ve dizinin beşinci öğesini değiştirir ve diziyi döndürür. Dizi uzunluğu beşten azsa, 'öğe bulunamadı' döndürür.

```js
console.log(modifyArray(['Avokado', 'Domates', 'Patates','Mango', 'Limon','Havuç']);
```

```ş
['Avokado', 'Domates', 'Patates', 'Mango', 'LİMON', 'Havuç']
```

```js
console.log(modifyArray(['Google', 'Facebook','Apple', 'Amazon','Microsoft', 'IBM']);
```

```ş
['Google', 'Facebook','Apple', 'Amazon','MICROSOFT', 'IBM']
```

```js
console.log(modifyArray(['Google', 'Facebook','Elma', 'Amazon']);
```

```ş
  'Bulunamadı'
```

15. Bir sayının asal sayı olup olmadığını kontrol eden _isPrime_ adlı bir işlev yazın.
16. Dizideki tüm öğelerin benzersiz olup olmadığını kontrol eden bir işlev yazın.
17. Dizideki tüm öğelerin aynı veri tipi olup olmadığını kontrol eden bir fonksiyon yazın.
18. JavaScript değişken adı, \$ veya \_ dışındaki özel karakterleri veya sembolleri desteklemez. Bir değişkenin geçerli mi yoksa geçersiz mi olduğunu kontrol eden bir **isValidVariable** işlevi yazın.
19. 0-9 aralığında yedi rasgele sayıdan oluşan bir dizi döndüren bir fonksiyon yazın. Tüm sayılar benzersiz olmalıdır.

```js
sevenRandomNumbers()[(1, 4, 5, 7, 9, 8, 0)];
```

20. reverseCountries adlı bir işlev yazın, bu, ülkeler dizisini alır ve önce diziyi kopyalar ve orijinal dizinin tersini döndürür

🎉 Tebrikler ! 🎉

[<< Gün 6](../06_Gün_Döngüler/06_gün_döngüler.md) | [Gün 8 >>](../08_Gün_Nesneler/08_gün_nesneler.md)
