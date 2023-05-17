<div align="center">
<h1> 30 Günde JavaScript: Web Depoları</h1>

<a class="header-badge" target="_blank" href="https://twitter.com/developerkhatai">
<img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/developerkhatai?style=social">
</a><br>

<sub>Çevirmen:
<a href="https://github.com/BilgeGates">Khatai Huseynzade</a><br>
<small>Mayıs, 2023</small>
</sub>

</div>
</div>

[<< Gün 16](../16_Gün_JavaScript_Nesne_Kavramı/16_gün_javascript_nesne_kavramı.md) | [Gün 18 >>](../18_Gün_Sözler/18_gün_sözler.md)

- [ 📔 Gün 17](#-Gün-17)
  - [HTML5 Web Depolama)](HTML5-Web-Depolama)
    - [Oturum Depolama](#Oturum-Depolame)
    - [Yerel Depolama](#Yerel-Depolama)
    - [Web Depoların Kullanım Durumu](#Web-Depoların-Kullanım-Durumu)
  - [HTML5 Web Depolama Nesneleri](#HTML5-Web-Depolama-Nesneleri)
    - [Öğeyi Yerel Depolamaya ayarlama](#Öğeyi-lYerel-Depolamaya-ayarlama)
    - [Öğeyi Yerel Depolamadan alma](#Öğeyi-Yerel-Depolamadan-alma)
    - [Yerel Depolamayı Temizleme](#Yerel-Depolamayı-Temizleme)
  - [💻 Gün 17: Egzersizleri](#-Gün-17-Egzersizleri)
    - [Egzersiz: Seviye 1](#Egzersiz-Seviye-1)
    - [Egzersiz: Seviye 2](#Egzersiz-Seviye-2)
    - [Egzersiz: Seviye 3](#Egzersiz-Seviye-3)

# 📔 Gün 17

## HTML5 Web Depolama

Web Depolama (sessionStorage ve localStorage), geleneksel tanımlama bilgilerine göre önemli avantajlar sunan yeni bir HTML5 API'sidir. HTML5'ten önce, uygulama verilerinin her sunucu isteğine dahil olan çerezlerde saklanması gerekiyordu. Web depolaması daha güvenlidir ve büyük miktarda veri web sitesi performansını etkilemeden local(yerel) olarak depolanabilir. Çerezlerin birçok web tarayıcısında veri depolama sınırı, çerez başına yaklaşık 4 KB'dir. Web Storage çok daha büyük verileri (en az 5MB) depolayabiliriz ve asla sunucuya aktarılmaz. Aynı veya bir kaynaktan gelen tüm siteler aynı verileri depolayabilir ve bunlara erişebilir.

Depolanan verilere JavaScript kullanılarak erişilebilir; bu, geleneksel olarak sunucu tarafı programlama ve ilişkisel veritabanlarını içeren birçok şeyi yapmak için istemci tarafı komut dosyası oluşturma yeteneğinden yararlanmanızı sağlar. İki Web Depolama nesnesi vardır:

- sessionStorage
- localStorage

localStorage, sessionStorage'a benzer, ancak localStorage'da depolanan verilerin sona erme süresi olmamasına rağmen, sessionStorage'da depolanan verilerin sayfa oturumu sona erdiğinde, yani sayfa kapatıldığında silinmesi dışında.

Yerel Depolama veya Oturum Depolama depolanan verilerin sayfanın protokolüne özel olduğuna dikkat edilmelidir.

Anahtarlar ve değerler her zaman dizelerdir.

![web_storage](../images/web_storage.png)

### Oturum Depolama

Oturum Depolama yalnızca tarayıcı sekmesinde veya pencere oturumunda kullanılabilir. Verileri tek bir web sayfası oturumunda depolamak için tasarlanmıştır. Bu, pencere kapatılırsa oturum verilerinin kaldırılacağı anlamına gelir. Oturum Depolama ve Yerel Depolama benzer yöntemlere sahip olduğundan, sadece Yerel Depolama odaklanacağız.

### Yerel Depolama

HTML5 Yerel Depolama, son kullanma verisi olmadan tarayıcıda veri depolamak için kullanılan web depolama API'sinin para birimidir. Veriler, tarayıcı kapatıldıktan sonra bile tarayıcıda mevcut olacaktır. Yerel Depolama, tarayıcı oturumları arasında bile tutulur. Bu, tarayıcı kapatılıp yeniden açıldığında ve ayrıca sekmeler ve pencereler arasında anında verilerin hala mevcut olduğu anlamına gelir.

Web Depolama verileri, her iki durumda da farklı tarayıcılar arasında mevcut değildir. Örneğin, Firefox'ta oluşturulan depolama nesnelerine tıpkı çerezler gibi Internet Explorer'da erişilemez.
Yerel depolama üzerinde çalışmak için beş yöntem vardır:
_setItem(), getItem(), removeItem(), clear(), key()_

### Web Depolama Kullanım Durumu

Web Depolarının bazı kullanım durumları şunlardır:

- verileri geçici olarak depolamak
- kullanıcının alışveriş sepetine koyduğu ürünleri kaydetme
- veriler, sayfa istekleri, birden çok tarayıcı sekmesi arasında ve ayrıca Yerel Depolama kullanılarak tarayıcı oturumları arasında kullanılabilir hale getirilebilir
- Yerel Depolama kullanılarak tamamen çevrimdışı olarak kullanılabilir
- Web Depolama, sonraki isteklerin sayısını en aza indirmek için istemcide bazı statik veriler depolandığında harika bir performans kazancı olabilir. Görüntüler bile Base64 kodlaması kullanılarak dizelerde saklanabilir.
- kullanıcı kimlik doğrulama yöntemi için kullanılabilir

Yukarıda bahsedilen örnekler için Yerel Depolama kullanmak mantıklıdır. O halde sessionStorage'ı ne zaman kullanmamız gerektiğini merak ediyor olabilirsiniz.

Bazı durumlarda, pencere kapanır kapanmaz verilerden kurtulmak istiyoruz. Ya da uygulamanın başka bir pencerede açık olan aynı uygulamaya müdahale etmesini istemiyorsak. Bu senaryolar en iyi şekilde sessionStorage ile sunulur.

Şimdi, bu Web Depolama API'lerinden nasıl yararlanılacağını görelim.

## HTML5 Web Depolama Nesneleri

HTML web depolama, istemcide veri depolamak için iki nesne sağlar:

- window.localStorage - son kullanma tarihi olmayan verileri depolar
- window.sessionStorage - bir oturum için veri depolar (tarayıcı sekmesi kapatıldığında veriler kaybolur) Çoğu modern tarayıcı Web Depolamayı destekler, ancak localStorage ve sessionStorage için tarayıcı desteğini kontrol etmek iyidir. Web Depolama nesneleri için mevcut yöntemleri görelim.

Web Depolama Nesneleri:

- _localStorage_ - Yerel Depolama nesnesini görüntülemek için
- _localStorage.clear()_ - Yerel Depolamadaki her şeyi kaldırmak için
- _localStorage.setItem()_ - verileri Yerel Depolamada depolamak için. Bir anahtar ve bir değer parametresi alır.
- _localStorage.getItem()_ - Yerel Depolamada depolanan verileri görüntülemek için. Parametre olarak bir anahtar alır.
- _localStorage.removeItem()_ - depolanan öğeyi Yerel Depolamadan kaldırmak için. Parametre olarak bir anahtar alır.
- _localStorage.key()_ - Yerel Depolamada depolanan verileri görüntülemek için. Parametre olarak indeks alır.

![local_storage](../images/local_storage.png)

### Öğeyi Yerel Depolamada Ayarlama

Bir Yerel Depolamada saklanacak verileri ayarladığımızda, bir dize olarak saklanacaktır. Bir diziyi veya nesneyi depoluyorsak, orijinal verinin dizi yapısını veya nesne yapısını kaybetmediğimiz sürece, formatı korumak için önce onu dizgelendirmemiz gerekir.

Verileri Yerel Depolamada _localStorage.setItem_ yöntemini kullanarak depolarız.

```js
//syntax
localStorage.setItem("key", "value");
```

- String ifadeleri localStorage üzerinde saklama

```js
localStorage.setItem("firstName", "Asabeneh"); // değer string olduğundan onu stringleştirmeyiz
console.log(localStorage);
```

```sh
Storage {firstName: 'Asabeneh', length: 1}
```

- Number ifadeleri localStorage üzerinde saklama

```js
localStorage.setItem("age", 200);
console.log(localStorage);
```

```sh
 Storage {age: '200', firstName: 'Asabeneh', length: 2}
```

- Bir diziyi Yerel Depolamada depolamak. Bir diziyi, nesneyi veya nesne dizisini depoluyorsak, önce nesneyi dizgelendirmemiz gerekir. Aşağıdaki örneğe bakın.

```js
const skills = ["HTML", "CSS", "JS", "React"];
//Biçimi korumak için önce skills dizisinin dizilmesi gerekir.
const skillsJSON = JSON.stringify(skills, undefined, 4);
localStorage.setItem("skills", skillsJSON);
console.log(localStorage);
```

```sh
Storage {age: '200', firstName: 'Asabeneh', skills: 'HTML,CSS,JS,React', length: 3}
```

```js
let skills = [
  { tech: "HTML", level: 10 },
  { tech: "CSS", level: 9 },
  { tech: "JS", level: 8 },
  { tech: "React", level: 9 },
  { tech: "Redux", level: 10 },
  { tech: "Node", level: 8 },
  { tech: "MongoDB", level: 8 },
];

let skillJSON = JSON.stringify(skills);
localStorage.setItem("skills", skillJSON);
```

- Bir nesneyi Yerel Depolamada depolamak. Nesneleri bir localStorage'a depolamadan önce, nesnenin dizelenmesi gerekir.

```js
const user = {
  firstName: "Asabeneh",
  age: 250,
  skills: ["HTML", "CSS", "JS", "React"],
};

const userText = JSON.stringify(user, undefined, 4);
localStorage.setItem("user", userText);
```

### Öğeyi Yerel Depolamadan Alma

_localStorage.getItem()_ yöntemini kullanarak yerel depodan veri alıyoruz..

```js
//syntax
localStorage.getItem("key");
```

```js
let firstName = localStorage.getItem("firstName");
let age = localStorage.getItem("age");
let skills = localStorage.getItem("skills");
console.log(firstName, age, skills);
```

```sh
 'Asabeneh', '200', '['HTML','CSS','JS','React']'
```

Gördüğünüz gibi skills string formatında. Normal diziye ayrıştırmak için JSON.parse() kullanalım.

```js
let skills = localStorage.getItem("skills");
let skillsObj = JSON.parse(skills, undefined, 4);
console.log(skillsObj);
```

```sh
['HTML','CSS','JS','React']
```

### Yerel Depolama Temizleme

_*Clear*_ yöntemi, yerel depolamada depolanan her şeyi temizleyecektir.

```js
localStorage.clear();
```

🌕 Kararlısınız. Artık Web Depolama biliyorsunuz ve küçük verileri istemci tarayıcılarında nasıl depolayacağınızı biliyorsunuz. Büyüklüğe giden yolda 17 adım öndesin. Şimdi beyniniz ve kasınız için bazı egzersizler yapın.

## 💻 Gün 17: Egzersizleri

### Egzersiz: Seviye 1

1. Adınızı, soyadınızı, yaşınızı, ülkenizi, şehrinizi tarayıcınızın localStorage'ında saklayın.

### Egzersiz: Seviye 2

1. Bir öğrenci nesnesi oluşturun. Öğrenci nesnesinin adı, soyadı, yaşı, becerileri, ülkesi, kayıtlı anahtarları ve anahtarların değerleri olacaktır. Öğrenci nesnesini tarayıcınızın localStorage'ında saklayın.

### Egzersiz: Seviye 3

1. personAccount adlı bir nesne oluşturun. ad, soyad, gelirler, giderler özelliklerine sahip olup totalIncome, totalExpense, accountInfo,addIncome, addExpense ve accountBalance yöntemlerine sahip olsun. Gelirler bir dizi gelirdir ve tanımı ve giderleri de bir dizi gider ve tanımıdır.

🎉 TEBRİKLER ! 🎉

[<< Gün 16](../16_Gün_JavaScript_Nesne_Kavraml/16_gün_javascript_nesne_kavramı.md) | [Gün 18 >>](../18_Gün_Sözler/18_gün_sözler.md)
