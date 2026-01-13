<div align="center">
  <h1> 30 Günde Javascript: Nesneler</h1>

[![GitHub](https://img.shields.io/badge/Follow-0a4d0a?style=for-the-badge&logo=github&logoColor=white)](https://github.com/BilgeGates)<br>

<sub>Çevirmen:
<a href="https://github.com/BilgeGates">Khatai Huseynzada</a><br>
<small> Mayıs, 2023</small>
</sub>

</div>

[<< Gün 7](../07_Gün_Fonksiyonlar/07_gün_fonksiyonlar.md) | [Gün 9 >>](../09_Gün_Üst_Düzey_Fonksiyonlar/09_gün_üst_düzey_fonksiyonlar.md)

- [📔 Gün 8](#-Gün-8)
  - [Kapsam Alanları](#Kapsam-Alanları)
    - [Window Küresel Nesne](#Window-Küresel-Nesne)
    - [Küresel Kapsam](#Küresel-Kapsam)
    - [Yerel Kapsam](#Yerel-Kapsam)
  - [Nesne](#Nesne)
    - [Boş Nesne Oluşturmak](#Boş-Nesne-Oluşturmak)
    - [Değerlerle Birlikte Bir Nesne Oluşturmak](#Değerlerle-Birlikte-Bir-Nesne-Oluşturmak)
    - [Nesneden Değerleri Alabilmek](#Nesneden-Değerleri-Alabilmek)
    - [Nesne Metodu Oluşturma](#Nesne-Metodu-Oluşturma)
    - [Nesne İçin Yeni Bir Anahtar Oluşturma](#Nesne-İçin-Yeni-Bir-Anahtar-Oluşturma)
    - [Nesne Metodları](#Nesne-metodları)
      - [Keys Metodu](#Keys-Metodu)
      - [Values Metodu](#Values-Metodu)
      - [Entries Metodu](#Entries-Metodu)
      - [hasOwnProperty Metodu](#HasOwnProperty-Metodu)
  - [💻 Gün 8: Egzersizleri](#-Gün-8-Egzersizleri)
    - [Egzersiz: Seviye 1](#Egzersiz-Seviye-1)
    - [Egzersiz: Seviye 2](#Egzersiz-Seviye-2)
    - [Egzersiz: Seviye 3](#Egzersiz-Seviye-3)

# 📔 Gün 8

## Kapsam Alanları

Bu konu değişken tanımlamanın temel kısmını oluşturur. Farklı veri türlerini depolamak için değişken tanımlarız. Bir değişkeni tanımlamak için `var`, `let` veya `const` anahtar sözcüklerini kullanırız. Bir değişken farklı kapsam alanlarında tanımlanabilir. Bu bölümde, `var` veya `let` kullandığımızda kapsam değişkenlerinin kodumuzu nasıl etkilediğini göreceğiz.

Değişken scope'ları şu şekilde olabilir.

- Global
- Local

`var`, `let` veya `const` olmadan tanımlanan her değişken global scope olarak geçerlidir.

Scope.js adında bir dosyanızın olduğunu düşünelim.

### Window Küresel Nesne

Geçerli dosya içerisinde global scope da diyebiliriz bu duruma

Console.log() metodunu kullanmadan tarayıcınızı açın ve kontrol edin; tarayıcıya a veya b yazarsanız a ve b değerlerini görebilirsiniz. Bu durum a ve b değişkenlerinin zaten hali hazırda mevcut olduğu anlamına gelir.

```js
//scope.js dosyası içerisi

a = "JavaScript"; // bir değişkeni let veya const anahtar kelimeleri olamadan tanımlamako değişkeni global hale getirir ve geçerli dosya içerisinde her yerden erişilebilir.

b = 10; // bu gloabl scope olarak tanımlanmıştır ve dosya içerisinde her yerden erişilebilir.
function letsLearnScope() {
  console.log(a, b);
  if (true) {
    console.log(a, b);
  }
}
console.log(a, b); // erişilebilir
```

### Küresel Kapsam

Aynı dosyanın her yerinde global olarak tanımlanan bir değişkene erişilebilir. Global olma durumu iki şekilde olabilir Dosyanın direkt kendisinde global olabilir veya bazı kod bloklarına göre global olabilir.

```js
//scope.js
let a = "JavaScript"; // bu dosyanın herhangi bir yerinde erişilebilecek global bir kapsamdır
let b = 10; // bu da dosyanın herhangi bir yerinde erişilebilecek global bir kapsamdır
function letsLearnScope() {
  console.log(a, b); // JavaScript 10, erişilebilir
  if (true) {
    let a = "Python";
    let b = 100;
    console.log(a, b); // Python 100
  }
  console.log(a, b);
}
letsLearnScope();
console.log(a, b); // JavaScript 10, erişilebilir
```

### Yerel Kapsam

Yerel olarak tanımlanan bir değişkene yalnızca belirli kod bloğunda erişilebilir.

- Block Scope
- Function Scope

```js
//scope.js dosyasının içerisi

let a = "JavaScript"; // bu dosyanın herhangi bir yerinde erişilebilecek global bir kapsamdır.
let b = 10; // bu dosyanın herhangi bir yerinde erişilebilecek global bir kapsamdır.

// Function scope
function letsLearnScope() {
  console.log(a, b); // JavaScript 10, erişilebilir
  let value = false;
  // block scope
  if (true) {
    let a = "Python";
    let b = 20;
    let c = 30;
    let d = 40;
    value = !value;
    console.log(a, b, c, value); // Python 20 30 true
  }
  //c değişkenine erişemiyoruz çünkü c değişkeni sadec if bloğunda geçerli bir değişkendir
  console.log(a, b, c, value); // JavaScript 10 undefined true
}
letsLearnScope();
console.log(a, b); // JavaScript 10, erişilebilir
```

Artık scope'lar hakkında bir şeyler öğrendik. `var` anahtar kelimesi ile tanımlanan bir değişken fonksiyon scope'u içerisinde geçerlidir. Ancak `let` veya `const` anahtar kelimeleri ile tanımlanan değişkenler block scope'unda geçerlidir. (fonksiyon, if veya diğer dönggü blokları). Block kapsamını biraz daha netleştirmek gerekirse Javascript ve diğer çoğu yazılım dili için süslü parantezler arası demek olur. `{  }`

```js
//scope.js
function letsLearnScope() {
  var gravity = 9.81;
  console.log(gravity);
}
// console.log(gravity), Yakalanmayan ReferenceError: yerçekimi tanımlanmadı

if (true) {
  var gravity = 9.81;
  console.log(gravity); // 9.81
}
console.log(gravity); // 9.81

for (var i = 0; i < 3; i++) {
  console.log(i); // 0, 1, 2
}
console.log(i); // 3
```

```js
//scope.js
function letsLearnScope() {
  // let veya const kullanabilirsiniz ama yerçekimi sabittir ben const kullanmayı tercih ederim
  const gravity = 9.81;
  console.log(gravity);
}
// console.log(gravity), Yakalanmayan ReferenceError: yerçekimi tanımlanmadı

if (true) {
  const gravity = 9.81;
  console.log(gravity); // 9.81
}
// console.log(gravity), Yakalanmayan ReferenceError: yerçekimi tanımlanmadı

for (let i = 0; i < 3; i++) {
  console.log(i); // 0, 1, 2
}
```

`let` ve `const` anahtar kelimeleri ile tanımlanan değişkenlerin kapsam alanlarının aynı olduğunu ifade ettik. Peki aralarındaki fark ne? Basitçe açıklamak gerekirse `const` ile tanımlanan bir değişkenin değerini daha sonraki satırlarda değiştiremeyiz ancak `let` ile tanımlanan değişkenin değerini değiştirebiliriz. Ben `let` ve `const` kullanarak temiz kod yazmanızı ve hata ayıklamanın zor olmasını önlemek için `let` ve `const` 'ı kullanmanızı tavsiye ederim. Temel kural olarak, herhangi bir sabit değer için `let` ve dizi, nesne, ok fonksiyonu ve işlev ifadesi için `const` özelliğini kullanabilirsiniz.

## Nesne

Her şey bir nesne olabilir ve nesnelerin özellikleri ve özelliklerinin değerleri vardır, bu nedenle bir nesne bir anahtar değer çiftidir.
Bir nesneyi tam anlamıyla oluşturmak için iki köşeli parantez kullanırız.

### Boş Nesne Oluşturmak

Boş bir nesne

```js
const person = {};
```

### Değerle Birlikte Bir Nesne Oluşturmak

Şimdi oluşturacağımız person nesnesinin firstName, lastName, age, country, city ve skills gibi bazı özellikleri olacak şekilde oluşturalım.

```js
const person = {
  firstName: "Khatai",
  lastName: "Huseynzada",
  age: 250,
  country: "Azerbaijan",
  city: "Bakui",
  skills: ["HTML", "CSS", "JavaScript"],
};
console.log(person);
```

### Nesneden Değerleri Alabilmek

Nesnenin değerlerine iki yöntem kullanarak erişebiliriz:

- `.` operatörünü kullanarak erişebiliriz
- köşeli parantez kullanarak erişebiliriz

```js

const person = {
  firstName: "Khatai",
  lastName: "Huseynzada",
  age: 250,
  country: "Azerbaijan",
  city: "Bakui",
  skills:
   [
    "HTML",
    "CSS",
    "JavaScript"
    ],

console.log(person);

  getFullName: function () {
    return `${this.firstName}${this.lastName}`;
  },
  "phone number": "+994 555 55 55",
};

// "." operatörü kullanarak
console.log(person.firstName);
console.log(person.lastName);
console.log(person.age);
console.log(person.location); // undefined

// kçşeli parantez kullanarak
console.log(person["firstName"]);
console.log(person["lastName"]);
console.log(person["age"]);
console.log(person["age"]);
console.log(person["location"]); // undefined

// örneğin, telefon numarasına erişmek için yalnızca köşeli parantez yöntemini kullanırız
console.log(person["phone number"]);
```

### Nesne Metodları Oluşturma

Şimdi, kişi nesnesinin getFullName özellikleri vardır. getFullName, kişi nesnesinin içindeki işlevdir ve biz ona nesne yöntemi diyoruz. _this_ anahtar sözcüğü, nesnenin kendisine atıfta bulunur. Nesnenin farklı özelliklerinin değerlerine erişmek için _this_ kelimesini kullanabiliriz. Bir arrow funtionu nesne yöntemi olarak kullanamayız çünkü bu sözcüğü nesnenin kendisi yerine bir arrow funtionun içindeki pencereyi ifade eder. Örnek olarak:

```js
const person = {
  firstName: "Khatai",
  lastName: "Huseynzada",
  age: 250,
  country: "Azerbaijan",
  city: "Bakui",
  skills: ["HTML", "CSS", "JavaScript"],
};
console.log(person);

  getFullName: function () {
    return `${this.firstName} ${this.lastName}`;
  };

console.log(person.getFullName());
```

### Nesne İçin Yeni Bir Anahtar oluşturma

Nesne, eşlenebilen bir veri yapısıdır ve oluşturulduktan sonra nesnenin içeriğini değiştirebiliriz.

nesne de yeni key'ler oluşturabilme

```js
  firstName: "Khatai",
  lastName: "Huseynzada",
  age: 250,
  country: "Azerbaijan",
  city: "Bakui",
  skills: ["HTML", "CSS", "JavaScript"],
  getFullName: function () {
    return `${this.firstName} ${this.lastName}`;
  },
};
person.nationality = "Azerbaijan";
person.country = "Azerbaijan";
person.title = "student";

person.getPersonInfo = function () {
  let skillsWithoutLastSkill = this.skills
    .splice(0, this.skills.length - 1)
    .join(", ");
  let lastSkill = this.skills.splice(this.skills.length - 1)[0];

  let skills = `${skillsWithoutLastSkill}, and ${lastSkill}`;
  let fullName = this.getFullName();
  let statement = `${fullName} is a ${this.title}.\nHe lives in ${this.country}.\nHe skillss ${skills}.`;
  return statement;
};
console.log(person);
console.log(person.getPersonInfo());
```

```sh
Khatai Huseynzada is a student.
He lives in Azerbaijan.
He skills HTML, CSS, JavaScript.
```

### Nesne Metodları

Bir nesneyi manipüle etmek için farklı yöntemler vardır. Mevcut yöntemlerden bazılarını görelim.

_Object.assign_:Nesneyi orijinal nesneyi değiştirmeden kopyalamak için kullanılır

```js
const person = {
  firstName: "Asabeneh",
  age: 250,
  country: "Finland",
  city: "Helsinki",
  skills: ["HTML", "CSS", "JS"],
  title: "teacher",
  address: {
    street: "Heitamienkatu 16",
    pobox: 2002,
    city: "Helsinki",
  },
  getPersonInfo: function () {
    return `I am ${this.firstName} and I live in ${this.city}, ${this.country}. I am ${this.age}.`;
  },
};

//Object methods: Object.assign, Object.keys, Object.values, Object.entries
//hasOwnProperty

const copyPerson = Object.assign({}, person);
console.log(copyPerson);
```

#### Keys Methodu

_Object.keys_: Bir nesnenin anahtarlarını veya özelliklerini dizi olarak almak için kullanılır

```js
const keys = Object.keys(copyPerson);
console.log(keys); //['firstName', 'age', 'country','city', 'skills','title', 'address', 'getPersonInfo']
const address = Object.keys(copyPerson.address);
console.log(address); //['street', 'pobox', 'city']
```

#### Values Metodu

_Object.values_: Nesnenin key'lerine karşılık gelen değerleri dizi içerisinde almak için kullanılır

```js
const values = Object.values(copyPerson);
console.log(values);
```

#### Entries Metodu

_Object.entries_: Bir dizideki key ve value değerlerini almak için kullanılır

```js
const entries = Object.entries(copyPerson);
console.log(entries);
```

#### hasOwnProperty Metodu

_hasOwnProperty_: Bir nesnede belirli bir anahtar veya özelliğin bulunup bulunmadığını kontrol etmek için kullanılır

```js
console.log(copyPerson.hasOwnProperty("name"));
console.log(copyPerson.hasOwnProperty("score"));
```

🌕 Tebrikler 8. günü de başarıyla tamamladın. 9. günde görüşmek üzere

## 💻 Gün 8: Egzersizleri

### Egzersiz: Seviye 1

1. Köpek adında boş bir nesne oluşturun
2. Köpek nesnesini konsolda yazdırın
3. Köpek nesnesi için ad, bacaklar, renk, yaş ve kabuk özelliklerini ekleyin. bark özelliği, _woof woof_ döndüren bir yöntemdir.
4. Köpek nesnesinden isim, bacak, renk, yaş ve kabuk değeri alın
5. Köpek nesnesinin yeni özelliklerini ayarlayın: cins, getDogInfo

### Egzersiz: Seviye 2

1. Kullanıcılar nesnesinde birçok beceriye sahip kişiyi bulun.
2. Oturum açmış kullanıcıları sayın, aşağıdaki nesneden 50'den fazla puana sahip kullanıcıları sayın.

   ````js
   const users = {
     Alex: {
       email: 'alex@alex.com',
       skills: ['HTML', 'CSS', 'JavaScript'],
       age: 20,
       isLoggedIn: false,
       points: 30
     },
     Asab: {
       email: 'asab@asab.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'Redux', 'MongoDB', 'Express', 'React', 'Node'],
       age: 25,
       isLoggedIn: false,
       points: 50
     },
     Brook: {
       email: 'daniel@daniel.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'React', 'Redux'],
       age: 30,
       isLoggedIn: true,
       points: 50
     },
     Daniel: {
       email: 'daniel@alex.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'Python'],
       age: 20,
       isLoggedIn: false,
       points: 40
     },
     John: {
       email: 'john@john.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'React', 'Redux', 'Node.js'],
       age: 20,
       isLoggedIn: true,
       points: 50
     },
     Thomas: {
       email: 'thomas@thomas.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'React'],
       age: 20,
       isLoggedIn: false,
       points: 40
     },
     Paul: {
       email: 'paul@paul.com',
       skills: ['HTML', 'CSS', 'JavaScript', 'MongoDB', 'Express', 'React', 'Node'],
       age: 20,
       isLoggedIn: false,
       points: 40
     }
   }```

   ````

3. Kullanıcılar nesnesinden MERN yığın geliştiricisi olan kişileri bulun
4. Orijinal kullanıcı nesnesini değiştirmeden kullanıcılar nesnesinde adınızı ayarlayın
5. Kullanıcılar nesnesinin tüm anahtarlarını veya özelliklerini alın
6. Kullanıcılar nesnesinin tüm değerlerini alın
7. Bir ülke adı, başkenti, nüfusu ve dilleri yazdırmak için ülkeler nesnesini kullanın.

### Egzersiz: Seviye 3

1. _personAccount_ adında bir değişmez nesne oluşturun. _FirstName, lastName, gelirler, giderler_ özelliklerine ve _totalIncome, totalExpense, accountInfo,addIncome, addExpense_ ve _accountBalance_ yöntemlerine sahiptir. Gelirler, bir dizi gelir ve tanımı ve giderleri, bir dizi gelir ve açıklamasıdır.
2. \*\*\*\* Sorular:2, 3 ve 4 şu iki diziye dayalıdır:kullanıcılar ve ürünler ()

```js
const users = [
  {
    _id: "ab12ex",
    username: "Alex",
    email: "alex@alex.com",
    password: "123123",
    createdAt: "08/01/2020 9:00 AM",
    isLoggedIn: false,
  },
  {
    _id: "fg12cy",
    username: "Asab",
    email: "asab@asab.com",
    password: "123456",
    createdAt: "08/01/2020 9:30 AM",
    isLoggedIn: true,
  },
  {
    _id: "zwf8md",
    username: "Brook",
    email: "brook@brook.com",
    password: "123111",
    createdAt: "08/01/2020 9:45 AM",
    isLoggedIn: true,
  },
  {
    _id: "eefamr",
    username: "Martha",
    email: "martha@martha.com",
    password: "123222",
    createdAt: "08/01/2020 9:50 AM",
    isLoggedIn: false,
  },
  {
    _id: "ghderc",
    username: "Thomas",
    email: "thomas@thomas.com",
    password: "123333",
    createdAt: "08/01/2020 10:00 AM",
    isLoggedIn: false,
  },
];

const products = [
  {
    _id: "eedfcf",
    name: "mobile phone",
    description: "Huawei Honor",
    price: 200,
    ratings: [
      { userId: "fg12cy", rate: 5 },
      { userId: "zwf8md", rate: 4.5 },
    ],
    likes: [],
  },
  {
    _id: "aegfal",
    name: "Laptop",
    description: "MacPro: System Darwin",
    price: 2500,
    ratings: [],
    likes: ["fg12cy"],
  },
  {
    _id: "hedfcg",
    name: "TV",
    description: "Smart TV:Procaster",
    price: 400,
    ratings: [{ userId: "fg12cy", rate: 5 }],
    likes: ["fg12cy"],
  },
];
```

Yukarıdaki kullanıcı koleksiyonunu bir MongoDB veritabanından aldığınızı hayal edin.
A. Kullanıcının koleksiyona ekleme yapmasına izin veren, signUp adlı bir işlev oluşturun. Kullanıcı varsa, kullanıcıya zaten bir hesabı olduğunu bildirin.
B. Kullanıcının uygulamada oturum açmasına izin veren signIn adlı bir işlev oluşturun.

3. Ürünler dizisinin üç öğesi vardır ve her birinin altı özelliği vardır.
   A. Ürünü derecelendiren rateProduct adlı bir işlev oluşturun
   B. Bir ürünün ortalama puanını hesaplayan averajRating adında bir işlev oluşturun.

4. likeProduct adlı bir işlev oluşturun. Bu işlev, ürünü beğenmezseniz beğenmenize, beğendiyseniz beğenmeyi kaldırmanıza yardımcı olur.

🎉 Tebrikler ! 🎉

[<< Gün 7](../07_Gün_Fonksiyonlar/07_gün_fonksiyonlar.md) | [Gün 9 >>](../09_Gün_Üst_Düzey_Fonksiyonlar/09_gün_üst_düzey_fonksiyonlar.md)
