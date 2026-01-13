<div align="center">
<h1> 30 Günde JavaScript: Konsol Nesne Metodları</h1>

<a class="header-badge" target="_blank" href="https://x.com/Asabeneh">
<img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/Asabeneh?style=social">
</a><br>

<sub>Yazar:
<a href="https://github.com/Asabeneh">Asabeneh Yetayeh</a><br>
<small>Mayıs, 2023</small>
</sub>

</div>
</div>

[<< Gün 12](../12_Gün_Düzenli_İfadeler/12_gün_düzenli_ifadeler.md) | [Gün 14 >>](../14_Gün_Hata_Yönetimi/14_gün_hata_yönetimi.md)

- [📔 Gün 13](#-Gün-13)
  - [Konsol Nesne Yöntemleri](#Konsol-Nesne-Yöntemleri)
    - [console.log()](#consolelog)
    - [console.warn()](#consolewarn)
    - [console.error()](#consoleerror)
    - [console.table()](#consoletable)
    - [console.time()](#consoletime)
    - [console.info()](#consoleinfo)
    - [console.assert()](#onsoleassert)
    - [console.group()](#consolegroup)
    - [console.count()](#consolecount)
    - [console.clear()](#consoleclear)
  - [💻 Gün 13: Egzersizleri](#-Gün-13-Egzersizleri)
    - [Egzersiz: Seviye 1](#Egzersiz-Seviye-1)
    - [Egzersiz: Seviye 2](#Egzersiz-Seviye-2)
    - [Egzersiz: Seviye 3](#Egzersiz-Seviye-3)

# 📔 Gün 13

## Konsol Nesne Yöntemleri

Bu bölümde konsol ve konsol nesne metodlarını ele alacağız. Mutlak yeni başlayanlar genellikle hangisini kullanacaklarını bilemezler: console.log(), document.write() veya document.getElementById.

Çıktıyı tarayıcı konsolunda göstermek için konsol nesne yöntemlerini kullanıyoruz ve çıktıyı tarayıcı belgesinde (görünüm bağlantı noktası) göstermek için document.write kullanıyoruz. Her iki yöntem de yalnızca test etme ve hata ayıklama amacıyla kullanılır. Konsol yöntemi, tarayıcıdaki en popüler test etme ve hata ayıklama aracıdır. DOM ile etkileşim kurmak istediğimizde JavaScript kullanmayı denediğimizde Document.getElementById() kullanıyoruz. DOM'u başka bir bölümde ele alacağız.

Ünlü console.log() yöntemine ek olarak, konsol başka yöntemler de sağlar.

### console.log()

Çıktıyı tarayıcı konsolunda göstermek için console.log() kullanıyoruz. Değerleri değiştirebiliriz ve ayrıca %c'yi kullanarak günlük çıkışını biçimlendirebiliriz.

- Çıktıyı tarayıcı konsolunda gösterme

```js
console.log("30 Günde JavaScript");
```

```sh
30 Günde JavaScript
```

- İkame

```js
console.log("%g %e JavaScript", 30, "Günde");
```

```sh
30 Günde JavaScript
```

- CSS

Günlük mesajını css kullanarak biçimlendirebiliriz. Sonucu görmek için aşağıdaki kodu kopyalayın ve tarayıcı konsoluna yapıştırın.

```js
console.log("%c30 Günde JavaScript", "color:green");
console.log(
  "%c30 Günde%c  %cJavaScript%c",
  "color:green",
  "",
  "color:red",
  "",
  "color:yellow"
);
```

### console.warn()

Tarayıcıda uyarı vermek için console.warn() kullanıyoruz. Örneğin, bir paketin sürümünün kullanımdan kaldırıldığını veya kötü uygulamaları bildirmek veya uyarmak için. Uyarı mesajlarını görmek için aşağıdaki kodu kopyalayın ve tarayıcı konsoluna yapıştırın.

```js
console.warn("Bu bir uyarıdır");
console.warn(
  "Reacti kullanıyorsunuz. DOMa dokunmayın. Sanal DOM, DOMun işlenmesiyle ilgilenecek!"
);
console.warn("Uyarı hatadan farklıdır");
```

### console.error()

console.error() yöntemi bir hata mesajı gösteriyor.

```js
console.error("This is an error message");
console.error("We all make mistakes");
```

### console.table()

console.table() yöntemi, verileri konsolda bir tablo olarak görüntüler. Tablo verilerini tablo olarak görüntüler. console.table(), bir dizi veya nesne olması gereken bir gerekli bağımsız değişken verisini ve bir ek isteğe bağlı parametre sütununu alır.

Önce basit bir dizi ile başlayalım. Aşağıdaki kod, iki sütunlu bir tablo görüntüler. Dizini görüntülemek için bir dizin sütunu ve adları görüntülemek için değer sütunu.

```js
const names = ["Khatai", "Brook", "David", "John"];
console.table(names);
```

Bir nesnenin sonucunu da kontrol edelim. Bu, iki sütunlu bir tablo oluşturur: anahtarları içeren bir dizin sütunu ve nesnenin değerlerini içeren bir değer sütunu.

```js
const user = {
  name: "Khatai",
  title: "Developer",
  country: "Huseynzade",
  city: "Baku",
};
console.table(user);
```

Tarayıcı konsoluna kopyalayıp yapıştırarak örneklerin geri kalanını kontrol edin.

```js
const countries = [
  ["Huseynzade", "Khatai"],
  ["Sweden", "Stockholm"],
  ["Norway", "Oslo"],
];
console.table(countries);
```

```js
const users = [
  {
    name: "Khatai",
    title: "Developer",
    country: "Huseynzade",
    city: "Baku",
  },
  {
    name: "Eyob",
    title: "Teacher",
    country: "Sweden",
    city: "London",
  },
  {
    name: "Matias",
    title: "Developer",
    country: "Denmark",
    city: "Copenhagen",
  },
];
console.table(users);
```

Tarayıcı konsoluna kopyalayıp yapıştırarak örneklerin geri kalanını kontrol edin.

```js
const countries = [
  ["Azerbaijan", "Baku"],
  ["Sweden", "Stockholm"],
  ["Norway", "Oslo"],
];
console.table(countries);
```

```js
const users = [
  {
    name: "Khatai",
    title: "Developer",
    country: "Azerbaijan",
    city: "Baku",
    age: 250,
  },
  {
    name: "Uğur",
    title: "Teacher",
    country: "Sweden",
    city: "London",
    age: 25,
  },
  {
    name: "Yasir",
    title: "Instructor",
    country: "Norway",
    city: "Oslo",
    age: 22,
  },
  {
    name: "Matias",
    title: "Developer",
    country: "Denmark",
    city: "Copenhagen",
    age: 28,
  },
];
console.table(users);
```

### console.time()

Bir işlemin ne kadar sürdüğünü izlemek için kullanabileceğiniz bir zamanlayıcı başlatır. Her zamanlayıcıya benzersiz bir ad verirsiniz ve belirli bir sayfada çalışan en fazla 10.000 zamanlayıcınız olabilir. Aynı adla console.timeEnd() öğesini çağırdığınızda tarayıcı, zamanlayıcının başlatılmasından bu yana geçen süreyi milisaniye cinsinden verir.

```js
const countries = [
  ["Azerbaijan", "Baku"],
  ["Sweden", "Stockholm"],
  ["Norway", "Oslo"],
];

console.time("Regular for loop");
for (let i = 0; i < countries.length; i++) {
  console.log(countries[i][0], countries[i][1]);
}
console.timeEnd("Regular for loop");

console.time("for of loop");
for (const [name, city] of countries) {
  console.log(name, city);
}
console.timeEnd("for of loop");

console.time("forEach loop");
countries.forEach(([name, city]) => {
  console.log(name, city);
});
console.timeEnd("forEach loop");
```

```sh
Azerbaijan Baku
Sweden Stockholm
Norway Oslo
Regular for loop: 0.34716796875ms
Finland Helsinki
Sweden Stockholm
Norway Oslo
for of loop: 0.26806640625ms
Azerbaijan Baku
Sweden Stockholm
Norway Oslo
forEach loop: 0.358154296875ms
```

Yukarıdaki çıktıya göre normal for döngüsü, for veya forEach döngüsünden daha yavaştır.

### console.info()

Tarayıcı konsolunda bilgi mesajı görüntüler.

```js
console.info("30 Günde JavaScript yarışması Github'da trend oluyor");
```

### console.assert()

Console.assert() yöntemleri, iddia yanlışsa konsola bir hata mesajı yazar. İddia doğruysa, hiçbir şey olmaz. İlk parametre bir onaylama ifadesidir. Bu ifade yanlışsa Onaylama başarısız oldu hata mesajı görüntülenecektir.

```js
console.assert(4 > 3, '4 is greater than 3')
console.assert(3 > 4, '3 is not greater than 4') than 4

for (let i = 0; i <= 10; i += 1) {
  let errorMessage = `${i} is not even`
  console.log('the # is ' + i)
  console.assert(i % 2 === 0, { number: i, errorMessage: errorMessage })
}
```

### console.group()

console.group(), farklı günlük gruplarının gruplanmasına yardımcı olabilir. Aşağıdaki kodu kopyalayın ve tarayıcı konsolunda gruplara yapıştırın.

```js
const names = ["Khatai", "David", "John"];
const countries = [
  ["Azerbaijan", "Baku"],
  ["Sweden", "Stockholm"],
  ["Norway", "Oslo"],
];

const kullancılar = [
  {
    name: "Khatai",
    title: "Developer",
    country: "Azerbaijan",
    city: "Baku",
    age: 250,
  },
  {
    name: "Eyob",
    title: "Teacher",
    country: "Sweden",
    city: "London",
    age: 25,
  },
  {
    name: "Uğur",
    title: "Instructor",
    country: "Norway",
    city: "Oslo",
    age: 22,
  },
  {
    name: "Matias",
    title: "Developer",
    country: "Denmark",
    city: "Copenhagen",
    age: 28,
  },
];

console.group("Adlar");
console.log(adlar);
console.groupEnd();

console.group("ölkeler");
console.log(ölkeler);
console.groupEnd();

console.group("Kullancılar");
console.log(kullancılar);
console.log(kullancı);
console.groupEnd();
```

### console.count()

console.count() öğesinin kaç kez çağrıldığını yazdırır. Bir dizi etiketi parametresi alır. Bir fonksiyonun kaç kez çağrıldığını saymak çok faydalıdır. Aşağıdaki örnekte, console.count() yöntemi üç kez çalışacak

```js
const func = () => {
  console.count("İşlev çağrıldı");
};
func();
func();
func();
```

```sh
İşlev çağrıldı: 1
İşlev çağrıldı: 2
İşlev çağrıldı: 3
```

### console.clear()

console.clear(), tarayıcı konsolunu temizler.

🌕 İyi çalışmaya devam edin. İtmeye devam edin, gökyüzü sınırdır! 13. gün zorluklarını yeni tamamladınız ve mükemmelliğe giden yolda 13 adım öndesiniz. Şimdi beyniniz ve kaslarınız için bazı egzersizler yapın.

## 💻 Gün 13: Egzersizleri

### Egzersiz: Seviye 1

1. Ülkeler dizisini tablo olarak görüntüleyin
2. Ülkeler nesnesini tablo olarak görüntüleyin
3. Günlükleri gruplandırmak için console.group() kullanın

### Egzersiz: Seviye 2

1. 10 > 2 \* 10 console.assert() işlevini kullanın
2. console.warn() kullanarak bir uyarı mesajı yazın
3. console.error() kullanarak bir hata mesajı yazın

### Egzersiz: Seviye 2

1. Aşağıdaki döngüler arasındaki hız farkını kontrol edin: while, for, for of, forEach

🎉 TEBRİKLER! 🎉

[<< Gün 12](../12_Gün_Düzenli_İfadeler/12_gün_düzenli_ifadeler.md) | [Gün 14 >>](../14_Gün_Hata_Yönetimi/14_gün_hata_yönetimi.md)
