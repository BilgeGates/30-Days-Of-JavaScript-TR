<div align="center">
<h1> 30 Günde JavaScript: Sözler</h1>

[![GitHub](https://img.shields.io/badge/Follow-0a4d0a?style=for-the-badge&logo=github&logoColor=white)](https://github.com/BilgeGates)<br>

<sub>Çevirmen:
<a href="https://github.com/BilgeGates">Khatai Huseynzada</a><br>
<small>Mayıs, 2023</small>
</sub>

</div>
</div>

[<< Gün 17](../17_Gün_Web_Depoları/17_gün_web_depoları.md) | [Gün 19>>](../19_Gün_Kapatma/19_gün_kapatma.md)

- [ 📔 Gün 18](#-Gün-18)
  - [Söz](#Söz)
    - [Geri Aramalar](#Geri-Aramalar)
    - [Söz Yapıcısı](#Söz-Yapıcısı)
    - [Fetch APİ](#Fetch-APİ)
    - [Async ve Await Fonksiyonu](#async-ve-await-Fonksiyonu)
  - [💻 Gün 18: Egzersizleri](#-Gün-18-Egzersizleri)
    - [Egzersiz: Seviye 1](#Egzersiz-Seviye-1)
    - [Egzersiz: Seviye 2](#Egzersiz-Seviye-2)
    - [Egzersiz: Seviye 3](#Egzersiz-Seviye-3)

# 📔 Gün 18

## Söz

Biz insanlar, belirli bir zamanda bir faaliyette bulunma sözü veririz veya alırız. Sözümüzü tutarsak başkalarını mutlu ederiz, ama sözümüzü tutmazsak hoşnutsuzluklara yol açabilir. JavaScript'te söz vermenin yukarıdaki örneklerle ortak bir yanı vardır.

Bir söz, JavaScript'te asynchronous işlemleri işlemenin bir yoludur. Asynchronous bir eylemin nihai başarı değeri veya başarısızlık nedeni ile işleyicilere izin verir. Bu, asynchronous yöntemlerin synchronous yöntemler gibi değerler döndürmesine olanak tanır: asynchronous yöntem, nihai değeri hemen döndürmek yerine, gelecekte bir noktada değeri sağlama sözü verir.

Bir söz şu durumlardan birindedir:

- pending: başlangıç ​​durumunda, ne tamamlandı ne de reddedildi.
- fulfilled: işlemin başarıyla tamamlandığı anlamına gelir.
- rejected: işlemin başarısız olduğu anlamına gelir.

Bekleyen bir söz ya bir değerle yerine getirilebilir ya da bir sebeple reddedilmiş olabilir. Bu seçeneklerden herhangi biri gerçekleştiğinde, bir sözün o zaman yöntemiyle sıraya alınan ilişkili işleyiciler çağrılır. (Karşılık gelen bir işleyici eklendiğinde söz bir işlemin tamamlanması ile işleyicilerinin eklenmesi arasında bir yarış koşulu yoktur.)

Promise.prototype.then() ve Promise.prototype.catch() yöntemleri sözleri döndürdüğü için zincirlenebilirler.

## Geri Aramalar

Sözü çok iyi anlamak için önce geri arama mantığını anlayalım. Aşağıdaki geri arama örneklerini görelim. Aşağıdaki kod bloklarında, geri arama ve söz arasındaki farkları fark edeceksiniz.

- Geri arama
  İki parametre alabilen bir geri arama işlevi görelim. İlk parametre err ve ikincisi sonuçtur. err parametresi false ise hata olmaz aksi takdirde hata döndürür.

Bu durumda err bir değere sahiptir ve err bloğunu döndürür.

```js
//Callback
const doSomething = (callback) => {
  setTimeout(() => {
    const skills = ["HTML", "CSS", "JS"];
    callback("It did not go well", skills);
  }, 2000);
};

const callback = (err, result) => {
  if (err) {
    return console.log(err);
  }
  return console.log(result);
};

doSomething(callback);
```

```sh
// 2 saniye sonra yazdırıcak
It did not go well
```

```js
const doSomething = (callback) => {
  setTimeout(() => {
    const skills = ["HTML", "CSS", "JS"];
    callback(false, skills);
  }, 2000);
};

doSomething((err, result) => {
  if (err) {
    return console.log(err);
  }
  return console.log(result);
});
```

```sh
// 2 saniye sonra yazdırıcak
["HTML", "CSS", "JS"]
```

### Söz Yapıcısı

Sözyapıcısını kullanarak bir söz oluşturabiliriz. `new` anahtar kelimesini, ardından `Promise` kelimesini ve ardından bir parantez kullanarak yeni bir söz oluşturabiliriz. Parantez içinde bir `callback` işlevi alır. Söz geri arama fonksiyonu, `resolve` ve `reject` fonksiyonları olmak üzere iki parametreye sahiptir.

```js
// syntax
const promise = new Promise((resolve, reject) => {
  resolve("success");
  reject("failure");
});
```

```js
// Söz
const doPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    const skills = ["HTML", "CSS", "JS"];
    if (skills.length > 0) {
      resolve(skills);
    } else {
      reject("Something wrong has happened");
    }
  }, 2000);
});

doPromise
  .then((result) => {
    console.log(result);
  })
  .catch((error) => console.log(error));
```

```sh
["HTML", "CSS", "JS"]
```

Yukarıdaki söz kararlılıkla yerine getirilmiştir. Sözen reddedilmesi ile kararlaştırıldığı başka bir örnek verelim.

```js
// söz
const doPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    const skills = ["HTML", "CSS", "JS"];
    if (skills.includes("Node")) {
      resolve("fullstack developer");
    } else {
      reject("Something wrong has happened");
    }
  }, 2000);
});

doPromise
  .then((result) => {
    console.log(result);
  })
  .catch((error) => console.error(error));
```

```sh
Something wrong has happened
```

## Fetch API

Fetch API'si, kaynakları almak için bir interface sağlar. XMLHttpRequest kullanan herkese tanıdık gelecektir, ancak yeni API daha güçlü ve esnek bir özellik seti sağlar. Bu görevde, url ve APIS istemek için fetch kullanacağız. Buna ek olarak, fetch API'sini kullanarak ağ kaynaklarına erişimde söz kullanım durumunu gösterelim.

```js
const url = "https://restcountries.com/v2/all"; // countries api
fetch(url)
  .then((response) => response.json()) // API verilerine JSON olarak erişme
  .then((data) => {
    // verileri almak
    console.log(data);
  })
  .catch((error) => console.error(error)); // yanlış bir şey olursa işleme hatası
```

## async ve await Fonksiyonu

async ve await Fonksiyonu, söz yerine getirmenin zarif bir yoludur. Anlaşılması kolay ve yazması temiz.

```js
const square = async function (n) {
  return n * n;
};

square(2);
```

```sh
Promise {<resolved>: 4}
```

Bir fonksiyonun önündeki async kelimesi, fonksiyonun bir söz vereceği anlamına gelir. Yukarıdaki kare fonksiyonu bir değer yerine bir söz verir.

Söz gelen değere nasıl erişiriz? Söz verilen değere erişmek için, wait anahtar sözcüğünü kullanacağız.

```js
const square = async function (n) {
  return n * n;
};
const value = await square(2);
console.log(value);
```

```sh
4
```

Şimdi, yukarıdaki örnekte de görebileceğiniz gibi, bir fonksiyonun önüne async yazarak bir söz oluşturun ve bir söz değer almak için bekliyoruz. Async ve await birlikte çalışır, biri olmadan diğeri olamaz.

API verilerini hem söz yöntemini kullanarak hem de async ve await yöntemini kullanarak getirelim.

- Söz

```js
const url = "https://restcountries.com/v2/all";
fetch(url)
  .then((response) => response.json())
  .then((data) => {
    console.log(data);
  })
  .catch((error) => console.error(error));
```

- async ve await fonksiyonu

```js
const fetchData = async () => {
  try {
    const response = await fetch(url);
    const countries = await response.json();
    console.log(countries);
  } catch (err) {
    console.error(err);
  }
};
console.log("===== async and await");
fetchData();
```

🌕 Sen gerçeksin ve sözünü tuttun ve 18. güne ulaştın. Sözünü tut ve azimle meydan oku. Büyüklüğe giden yolda 18 adım öndesin. Şimdi beyniniz ve kaslarınız için bazı egzersizler yapın

## 💻 Gün 18: Egzersizleri

```js
const countriesAPI = "https://restcountries.com/v2/all";
const catsAPI = "https://api.thecatapi.com/v1/breeds";
```

### Egzersiz: Seviye 1

1. Fetch kullanarak countriesAPI'sini okuyun ve country, capital, languages, population ve area adını yazdırın.

### Egzersiz: Seviye 2

1. Tüm kedi adlarını catNames değişkenine yazdırın.

### Egzersiz: Seviye 3

1. catsAPI'sini okuyun ve kedinin ortalama ağırlığını metrik birimde bulun.
2. countriesAPI'sini okuyun ve en büyük(largest) 10 ülkeyi bulun.
3. countriesAPI'sini okuyun ve dünyada resmi olarak kullanılan toplam dil sayısını bulun.

🎉 TEBRİKLER ! 🎉

[<< Gün 17](../17_Gün_Web_Depoları/17_gün_web_depoları.md) | [Gün 19>>](../19_Gün_Kapatma/19_gün_kapatma.md)
