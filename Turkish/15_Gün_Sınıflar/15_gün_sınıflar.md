<div align="center">
<h1> 30 Günde JavaScript: Sınıflar</h1>

<a class="header-badge" target="_blank" href="https://twitter.com/developerkhatai">
<img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/developerkhatai?style=social">
</a><br>

<sub>Çevirmen:
<a href="https://github.com/BilgeGates">Khatai Huseynzade</a><br>
<small>Mayıs, 2023</small>
</sub>

</div>
</div>

[<< Gün 14](../14_Gün_Hata_Yönetimi/14_gün_hata_yönetimi.md) | [Gün 16 >>](../16_Gün_JavaScript_Nesne_Kavramı/16_gün_javascript_nesne_kavramı.md)

- [ 📔 Gün 15](#-Gün-15)
  - [Sınıflar](#Sınıflar)
    - [Sınıfın Tanımı ](#Sınıfın-Tanımı)
    - [Sınıf Örneklemesi](#Sınıf-Örneklemesi)
    - [Sınıf Oluşturucu](#Sınıf-Oluşturucu)
    - [Yapıcı ile Varsayılan Ceğerler](#Yapıc-ile-Varsayılan_Değerler)
    - [Sınıf Metodları](#Sınıf-Metodları)
    - [Başlangıç ​​Değeri Olan Özellikler](#Başlanğıç-Değeri-Olan-Özellikler)
    - [Alıcı](#Alıcı)
    - [Tasarımcı](#Tasarımcı)
    - [Statik Metod](#Statik-Metod)
  - [Miras](#Miras)
    - [Geçersiz Kılma Yöntemleri](#Geçersiz-Kılma-Yöntemleri)
  - [💻 Gün 15: Egzersizleri](#-Gün-15-Egzersizleri)
    - [Egzersiz: Seviye 1](#Egzersiz-Seviye-1)
    - [Egzersiz: Seviye 2](#Egzersiz-Seviye-2)
    - [Egzersiz: Seviye 3](#Egzersiz-Seviye-3)

# 📔 Gün 15

## Sınıflar

JavaScript nesne tabanlı progralama dilidir. JavaScript'teki her şey, özellikleri ve yöntemleriyle bir nesnedir. Nesne oluşturmak için sınıf oluşturutuz. Sınıflar nesne oluşturucu (constructor) gibidir yada nesne oluşturmak için taslak gibidir. Nesne oluşturmak için sınıf oluştururuz. Sınıf, nesnenin niteliklerini ve davranışını tanımlarken, nesne ise sınıfı temsil eder.

Bir sınıf oluşturduğumuzda, istediğimiz zaman ondan nesne oluşturabiliriz. Bir sınıftan nesne oluşturmaya class instantiation(sınıf başlatma) denir.

Nesne bölümünde, bir nesne değişmezinin nasıl oluşturulacağını gördük. Nesne değişmezi bir singleton'dur. Benzer bir nesne elde etmek istiyorsak, onu yazmalıyız. Ancak sınıf, birçok nesne oluşturmaya izin verir. Bu, kod miktarını ve kod tekrarını azaltmaya yardımcı olur.

### Sınıfın Tanımı

JavaScript'te bir sınıf tanımlamak için class anahtar kelimesine, **CamelCase**'de bir sınıfın adına ve blok koduna (iki küme parantez) ihtiyacımız var. Kişi adında bir sınıf oluşturalım.

```sh
// syntax
class ClassName {
    //  code goes here
}

```

**Örnek:**

```js
class Person {
  // code goes here
}
```

Person sınıfı oluşturduk fakat içine bir şey yazmadık.

### Sınıf Örneklemesi

Örnekleme sınıfı, bir sınıftan bir nesne oluşturmak anlamına gelir. _new_ anahtar kelimesine ihtiyacımız var ve sınıfın adını _new_ kelimesinden sonra çağırıyoruz.

Person sınıfımız içerisine dog nesnesi oluşturalım.

```js
class Person {
  // code goes here
}
const person = new Person();
console.log(person);
```

```sh
Person {}
```

Gördüğünüz gibi bir Person nesnesi oluşturduk. Sınıfın henüz herhangi bir özelliği olmadığı için nesne de boştur.

Sınıfta farklı özellikler iletmek için class constructor(sınıf yapıcısını) kullanalım.

### Sınıf Oluşturucu

Constructor, nesnemiz için bir taslak oluşturmamıza izin veren yerleşik bir fonksiyondur. Constructor fonksiyonu, constructor anahtar sözcüğü ile başlar ve ardından bir parantez gelir. Parantez içinde nesnenin özelliklerini parametre olarak iletiyoruz. Bu anahtar sözcüğü, constructor parametrelerini sınıfa eklemek için kullanırız.

Aşağıdaki Person sınıfı oluşturucusu firstName ve lastName özelliği oluşturur. Bu özellikler, _this_ anahtar kelimesi kullanılarak Person sınıfına eklenir. _this_ sınıfın kendinisi ifade eder.

```js
class Person {
  constructor(firstName, lastName) {
    console.log(this); // Check the output from here
    this.firstName = firstName;
    this.lastName = lastName;
  }
}

const person = new Person();

console.log(person);
```

```sh
Person {firstName: undefined, lastName:undefined}
```

Nesnenin tüm anahtarları tanımsızdır(undefined). Ne zaman somutlaştırsak, özelliklerin değerini geçmeliyiz. Sınıfı somutlaştırdığımızda şu anda değeri iletelim.

```js
class Person {
  constructor(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
  }
}

const person1 = new Person("Khatai", "Huseynzade");

console.log(person1);
```

```sh
Person {firstName: "Khatai", lastName: "Huseynzade"}
```

En başta da belirttiğimiz gibi bir sınıf oluşturduğumuzda, sınıfı kullanarak birçok nesne oluşturabiliriz. Şimdi, Person sınıfını kullanarak birden fazla kişi nesnesi oluşturalım.

```js
class Person {
  constructor(firstName, lastName) {
    console.log(this); // Check the output from here
    this.firstName = firstName;
    this.lastName = lastName;
  }
}

const person1 = new Person("Khatai", "Huseynzadr");
const person2 = new Person("Ugur", "Hasanli");
const person3 = new Person("Abraham", "Mamedyarov");

console.log(person1);
console.log(person2);
console.log(person3);
```

```sh
Person {firstName: "Khatai", lastName: "Huseynzade"}
Person {firstName: "Ugur", lastName: "Hasanli"}
Person {firstName: "Abraham", lastName: "Mamedyarov"}
```

Person sınıfını kullanarak 3 kişi nesnesi oluşturduk. Gördüğünüz gibi sınıfımızda çok fazla özellik yok,hadi biraz daha sınıfımızın içerisine özellik ekleyelim.

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    console.log(this); // Check the output from here
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
    this.country = country;
    this.city = city;
  }
}

const person1 = new Person("Khatai", "Huseynzade", 250, "Azerbaijan", "Baku");

console.log(person1);
```

```sh
Person {firstName: "Khatai", lastName: "Huseynzade", age: 250, country: "Azerbaijan", city: "Baku"}
```

### Yapıcı ile Varsayılan Değerler

Yapıcı fonksiyonun özellikleri,diğer normal fonksiyonlar gibi bir değere sahip olabilir.

```js
class Person {
  constructor(
    firstName = "Khatai",
    lastName = "Huseynzade",
    age = 250,
    country = "Azerbaijan",
    city = "Baku"
  ) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
    this.country = country;
    this.city = city;
  }
}

const person1 = new Person(); // it will take the default values
const person2 = new Person("Ugur", "Hasanli", 28, "Azerbaijan", "Guba");

console.log(person1);
console.log(person2);
```

```sh
Person {firstName: "Khatai", lastName: "Huseynzade", age: 250, country: "Azerbaijan", city: "Baku"}
Person {firstName: "Ugur", lastName: "Hasanli", age: 28, country: "Azerbaijan", city: "Guba"}
```

### Sınıf Metodları

Bir sınıfın içindeki yapıcı, nesne için bir tasklak oluşturmamıza izin veren yerleşik bir fonksiyondur. Bir sınıfta sınıf metodları oluşturabiliriz. Metodlar, sınıf içindeki JavaScript fonksiyonlarıdır. Bazı sınıf metodları oluşturalım.

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
    this.country = country;
    this.city = city;
  }
  getFullName() {
    const fullName = this.firstName + " " + this.lastName;
    return fullName;
  }
}

const person1 = new Person("Khatai", "Huseynzade", 250, "Azerbaijan", "Baku");
const person2 = new Person("Ugur", "Hasanli", 28, "Azerbaijan", "Guba");

console.log(person1.getFullName());
console.log(person2.getFullName());
```

```sh
Khatai Huseynzade
Ugur Hasanli
```

### Başlangıç ​​Değeri Olan Özellikler

Bazı özellikler için bir sınıf oluşturduğumuzda bir başlangıç değerine sahip olabiliriz. Örneğin bir oyun oynuyorsanız, başlama puanınız sıfır olacaktır. Yani, sıfır olan bir başlangıç puanımız veya herhangi bir puanımız olabilir. Diğer bir şekilde, bir başlangıç becerisine sahip olabiliriz ve bir süre sonra biraz beceri kazanacağız.

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
    this.country = country;
    this.city = city;
    this.score = 0;
    this.skills = [];
  }
  getFullName() {
    const fullName = this.firstName + " " + this.lastName;
    return fullName;
  }
}

const person1 = new Person("Khatai", "Huseynzade", 250, "Azerbaijan", "Baku");
const person2 = new Person("Ugur", "Hasanli", 28, "Azerbaijan", "Guba");

console.log(person1.score);
console.log(person2.score);

console.log(person1.skills);
console.log(person2.skills);
```

```sh
0
0
[]
[]
```

Bir metod düzenli, alıcı yada tasarımcı olabilir. Alıcı ve tasarımcını yakından inceleyelim.

### Alıcı

Alıcı yöntemi, nesneden değere erişmemizi sağlar. _*Get*_ anahtar sözcüğünü ve ardından bir fonksiyon kullanarak bir get metodu yazıyoruz. Özelliklere doğrudan nesneden erişmek yerine değeri almak için getter kullanırız. Aşağıdaki örneğe bakalım

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
    this.country = country;
    this.city = city;
    this.score = 0;
    this.skills = [];
  }
  getFullName() {
    const fullName = this.firstName + " " + this.lastName;
    return fullName;
  }
  get getScore() {
    return this.score;
  }
  get getSkills() {
    return this.skills;
  }
}

const person1 = new Person("Khatai", "Huseynzade", 250, "Azerbaijan", "Baku");
const person2 = new Person("Ugur", "Hasanli", 28, "Azerbaijan", "Guba");

console.log(person1.getScore);
console.log(person2.getScore);

console.log(person1.getSkills);
console.log(person2.getSkills);
```

```sh
0
0
[]
[]
```

### Tasarımcı

Tasarımcı yöntemi, belirli özelliklerin değerini değiştirmemize izin verir. _set_ anahtar kelimesini kullanarak bir fonksiyon kullanarak bir tasarımcı metodu yazıyoruz. Aşağıdaki örneğe bakalım.

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
    this.country = country;
    this.city = city;
    this.score = 0;
    this.skills = [];
  }
  getFullName() {
    const fullName = this.firstName + " " + this.lastName;
    return fullName;
  }
  get getScore() {
    return this.score;
  }
  get getSkills() {
    return this.skills;
  }
  set setScore(score) {
    this.score += score;
  }
  set setSkill(skill) {
    this.skills.push(skill);
  }
}

const person1 = new Person("Khatai", "Huseynzade", 250, "Azerbaijan", "Baku");
const person2 = new Person(
  "Ugur",
  "Hasanli",
  "Tekle",
  28,
  "Azerbaijan",
  "Baku"
);

person1.setScore = 1;
person1.setSkill = "HTML";
person1.setSkill = "CSS";
person1.setSkill = "JavaScript";

person2.setScore = 1;
person2.setSkill = "Planning";
person2.setSkill = "Managing";
person2.setSkill = "Organizing";

console.log(person1.score);
console.log(person2.score);

console.log(person1.skills);
console.log(person2.skills);
```

```sh
1
1
["HTML", "CSS", "JavaScript"]
["Planning", "Managing", "Organizing"]
```

Normal metod ile alıcı arasındaki fark sizi şaşırtmasın. Normal bir metod yapmayı biliyorsanız, iyisiniz. Person sınıfına getPersonInfo adlı normal metod ekleyelim.

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
    this.country = country;
    this.city = city;
    this.score = 0;
    this.skills = [];
  }
  getFullName() {
    const fullName = this.firstName + " " + this.lastName;
    return fullName;
  }
  get getScore() {
    return this.score;
  }
  get getSkills() {
    return this.skills;
  }
  set setScore(score) {
    this.score += score;
  }
  set setSkill(skill) {
    this.skills.push(skill);
  }
  getPersonInfo() {
    let fullName = this.getFullName();
    let skills =
      this.skills.length > 0 &&
      this.skills.slice(0, this.skills.length - 1).join(", ") +
        ` and ${this.skills[this.skills.length - 1]}`;
    let formattedSkills = skills ? `He knows ${skills}` : "";

    let info = `${fullName} is ${this.age}. He lives ${this.city}, ${this.country}. ${formattedSkills}`;
    return info;
  }
}

const person1 = new Person("Khatai", "Huseynzade", 250, "Azerbaijan", "Baku");
const person2 = new Person("Ugur", "Hasanli", 28, "Azerbaijan", "Guba");
const person3 = new Person("John", "Doe", 50, "Mars", "Mars city");

person1.setScore = 1;
person1.setSkill = "HTML";
person1.setSkill = "CSS";
person1.setSkill = "JavaScript";

person2.setScore = 1;
person2.setSkill = "Planning";
person2.setSkill = "Managing";
person2.setSkill = "Organizing";

console.log(person1.getScore);
console.log(person2.getScore);

console.log(person1.getSkills);
console.log(person2.getSkills);
console.log(person3.getSkills);

console.log(person1.getPersonInfo());
console.log(person2.getPersonInfo());
console.log(person3.getPersonInfo());
```

```sh
1
1
["HTML", "CSS", "JavaScript"]
["Planning", "Managing", "Organizing"]
[]
Khatai Huseynzade is 250. He lives Azerbaijan, Baku. He knows HTML, CSS and JavaScript
Ugur Hasanli is 28. He lives Azerbaijan, Guba. He knows Planning, Managing and Organizing
John Doe is 50. He lives Mars city, Mars.
```

### Statik Metod

Statik anahtar kelime, bir sınıf için statik bir yöntem tanımlar. Statik metodlar, sınıfın örneklerinde çağrılmaz. Bunun yerine, sınıfın kendisinde çağrılırlar. Bunlar genellikle nesneler oluşturma veya klonlama fonskiyonları gibi yardımcı fonksiyonlardır. Statik metoda bir örnek _Date.now()_'dur. _now_ yöntemi doğrudan sınıftan çağrılır.

```js
class Person {
  constructor(firstName, lastName, age, country, city) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
    this.country = country;
    this.city = city;
    this.score = 0;
    this.skills = [];
  }
  getFullName() {
    const fullName = this.firstName + " " + this.lastName;
    return fullName;
  }
  get getScore() {
    return this.score;
  }
  get getSkills() {
    return this.skills;
  }
  set setScore(score) {
    this.score += score;
  }
  set setSkill(skill) {
    this.skills.push(skill);
  }
  getPersonInfo() {
    let fullName = this.getFullName();
    let skills =
      this.skills.length > 0 &&
      this.skills.slice(0, this.skills.length - 1).join(", ") +
        ` and ${this.skills[this.skills.length - 1]}`;

    let formattedSkills = skills ? `He knows ${skills}` : "";

    let info = `${fullName} is ${this.age}. He lives ${this.city}, ${this.country}. ${formattedSkills}`;
    return info;
  }
  static favoriteSkill() {
    const skills = ["HTML", "CSS", "JS", "React", "Python", "Node"];
    const index = Math.floor(Math.random() * skills.length);
    return skills[index];
  }
  static showDateTime() {
    let now = new Date();
    let year = now.getFullYear();
    let month = now.getMonth() + 1;
    let date = now.getDate();
    let hours = now.getHours();
    let minutes = now.getMinutes();
    if (hours < 10) {
      hours = "0" + hours;
    }
    if (minutes < 10) {
      minutes = "0" + minutes;
    }

    let dateMonthYear = date + "." + month + "." + year;
    let time = hours + ":" + minutes;
    let fullTime = dateMonthYear + " " + time;
    return fullTime;
  }
}

console.log(Person.favoriteSkill());
console.log(Person.showDateTime());
```

```sh
Node
15.1.2020 23:56
```

Statik metodlar, yardımcı fonksiyonlar olarak kullanılabilen yöntemlerdir.

## Kalıt

Kalıt kullanarak ana sınıfın tüm özelliklerine ve yöntemlerine erişebiliriz. Bu, kod tekrarını azaltır. Hatırlarsanız, bir Person ana sınıfımız var ve ondan alt sınıflar yaratacağız. Alt sınıfımız öğrenci, öğretmen vb. olabilir.

```js
// syntax
class ChildClassName extends {
 // code goes here
}
```

Person ebeveyn sınıfından bir Student alt sınıfı oluşturalım.

```js
class Student extends Person {
  saySomething() {
    console.log("I am a child of the person class");
  }
}

const s1 = new Person("Khatai", "Huseynzade", 250, "Azerbaijan", "Baku");
console.log(s1);
console.log(s1.saySomething());
console.log(s1.getFullName());
console.log(s1.getPersonInfo());
```

```sh
Student {firstName: "Khatai", lastName: "Huseynzade", age: "250", country: Azerbaijan, city: "Baku", …}
I am a child of the person class
Khatai Huseynzade
Student {firstName: "Khatai", lastName: "Huseynzade", age: "250", country: Azerbaijan, city: "Baku", …}
Khatai Huseynzade is Azerbaijan. He lives Baku, 250.
```

### Geçersiz Kılma Yöntemleri

Gördüğünüz gibi Person Class'taki tüm yöntemlere erişmeyi başardık ve Student alt sınıfında kullandık. Ana yöntemlerini özelleştirebiliriz, bir alt sınıfa ek özellikler ekleyebiliriz. Özelleştirmek istiyorsak, metodlar ve ekstra özellikler eklemek istiyorsak, alt sınıfa için yapıcı fonksiyonu kullanmamız gerekir. yapıcı işlevinin içinde, üst sınıftan tüm özelliklere erişmek için super() işlevini çağırırız. Person sınıfının cinsiyeti yoktu ama şimdi öğrenci sınıfı için cinsiyet özelliğini verelim. Alt sınıfta aynı metod adı kullanılıyorsa, üst yöntem geçersiz kılınır.

```js
class Student extends Person {
  constructor(firstName, lastName, age, country, city, gender) {
    super(firstName, lastName, age, country, city);
    this.gender = gender;
  }

  saySomething() {
    console.log("I am a child of the person class");
  }
  getPersonInfo() {
    let fullName = this.getFullName();
    let skills =
      this.skills.length > 0 &&
      this.skills.slice(0, this.skills.length - 1).join(", ") +
        ` and ${this.skills[this.skills.length - 1]}`;

    let formattedSkills = skills ? `He knows ${skills}` : "";
    let pronoun = this.gender == "Male" ? "He" : "She";

    let info = `${fullName} is ${this.age}. ${pronoun} lives in ${this.city}, ${this.country}. ${formattedSkills}`;
    return info;
  }
}

const s1 = new Student(
"Khatai"
"Huseynzade"
250
"Azerbaijan"
"Baku";
"Male"

);
const person2 = new Person("Ugur", "Hasanli", 28, "Azerbaijan", "Guba", "female");
s1.setScore = 1;
s1.setSkill = "HTML";
s1.setSkill = "CSS";
s1.setSkill = "JavaScript";

s2.setScore = 1;
s2.setSkill = "Planning";
s2.setSkill = "Managing";
s2.setSkill = "Organizing";

console.log(s1);

console.log(s1.saySomething());
console.log(s1.getFullName());
console.log(s1.getPersonInfo());

console.log(s2.saySomething());
console.log(s2.getFullName());
console.log(s2.getPersonInfo());
```

```sh
Student {firstName: "Khatai", lastName: "Huseynzade", age: "250", country: Azerbaijan, city: "Baku", …}
I am a child of the person class
Khatai Huseynzade
Student {firstName: "Ughur", lastName: "Hasanli", age: 28, country: "Azerbaijan", city: "Guba", …}
I am a child of the person class
Ugur Hasanli
Student {firstName: "Khatai", lastName: "Huseynzade", age: "250", country: Azerbaijan, city: "Baku", …}
I am a child of the person class
Khatai Huseynzade
Student {firstName: "Ughur", lastName: "Hasanli", age: 28, country: "Azerbaijan", city: "Guba", …}
Ugur Hasanli is 28. She lives in Baku, Azerbaijan. He knows Planning, Managing and Organizing
```

Şimdi, getPersonInfo metodu geçersiz kılındı ​​ve kişinin erkek mi yoksa kadın mı olduğunu tanımlar.

🌕 Sen mükemmelsin. Artık sınıf oluşturmayı biliyorsunuz ve her şeyi bir nesneye dönüştürme gücünüz var. Büyüklüğe giden yolun yarısına kadar geldin. Şimdi beyniniz ve kasınız için bazı egzersizler yapın.

## 💻 Gün 15: Egzersizleri

### Egzersiz: Seviye 1

1. Bir Animal sınıfı oluşturun. Sınıf, isim, yaş, renk, ayak sayısı özelliklerine sahip olacak ve farklı yöntemler oluşturacaktır
2. Animal sınıfına Dog ve Cat adı altında alt sınıflar oluşturun

### Egzersiz: Seviye 2

1. Oluşturduğunuz Animal sınıfını override metoduyla yazın

### Egzersiz: Seviye 3

1. Bir örneğin merkezi eğilim ölçüsünü (ortalama, medyan, mod) ve değişkenlik ölçüsünü (aralık, varyans, standart sapma) hesaplayan bir program geliştirmeye çalışalım. Bu ölçülere ek olarak, numunenin min, maks, sayım, yüzdelik ve frekans dağılımını bulun. İstatistikler adlı bir sınıf oluşturabilir ve İstatistik sınıfı için yöntem olarak istatistiksel hesaplamalar yapan tüm işlevleri oluşturabilirsiniz. Aşağıdaki çıktıyı kontrol edin.

```JS
ages = [31, 26, 34, 37, 27, 26, 32, 32, 26, 27, 27, 24, 32, 33, 27, 25, 26, 38, 37, 31, 34, 24, 33, 29, 26]

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
console.log('Frequency Distribution: ',statistics.freqDist()) // [(20.0, 26), (16.0, 27), (12.0, 32), (8.0, 37), (8.0, 34), (8.0, 33), (8.0, 31), (8.0, 24), (4.0, 38), (4.0, 29), (4.0, 25)]
```

```sh
// you output should look like this
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

1. PersonAccount adlı bir sınıf oluşturun. ad, soyad, gelirler, giderler özelliklerine sahip olan totalIncome, totalExpense, accountInfo,addIncome, addExpense ve accountBalance metodlarına sahip.

🎉 TEBRİKLER ! 🎉

[<< Gün 14](../14_Gün_Hata_Yönetimi/14_gün_hata_yönetimi.md) | [Gün 16 >>](../16_Gün_JavaScript_Nesne_Kavramı/16_gün_javascript_nesne_kavramı.md)
