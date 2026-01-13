<div align="center">
<h1> 30 Günde JavaScript: Kapatma</h1>

[![GitHub](https://img.shields.io/badge/Follow-0a4d0a?style=for-the-badge&logo=github&logoColor=white)](https://github.com/BilgeGates)<br>

<sub>Çevirmen:
<a href="https://github.com/BilgeGates">Khatai Huseynzada</a><br>
<small>Mayıs, 2023</small>
</sub>

</div>
</div>

[<< Gün 18](../18_Gün_Sözler/18_gün_sözler.md) | [Gün 20 >>](../20_Gün_Temiz_Kod_Yazımı/20_gün_temiz_kod_yazımı.md)

- [ 📔 Gün 19](#-Gün-19)
  - [Kapatma](#Kapatma)
- [💻 Gün 19: Egzersizleri](#-Gün-19-Egzersizleri)
  - [Egzersiz: Seviye 1](#Egzersiz-Seviye-1)
  - [Egzersiz: Seviye 2](#Egzersiz-Seviye-2)
  - [Egzersiz: Seviye 3](#Egzersiz-Seviye-3)

# 📔 Gün 19

## Kapatma

JavaScript, bir dış(outher) fonksiyonu içine yazma fonksiyonu izni verir. İstediğimiz kadar iç(Inner) fonksiyon yazabiliriz. İç fonksiyonu, dış fonksiyonun değişkenlerine erişiyorsa, buna kapatma denir.

```js
function outerFunction() {
  let count = 0;
  function innerFunction() {
    count++;
    return count;
  }

  return innerFunction;
}
const innerFunc = outerFunction();

console.log(innerFunc());
console.log(innerFunc());
console.log(innerFunc());
```

```sh
1
2
3
```

İç(Inner) fonksiyonlara daha fazla örnek vermek gerekirse

```js
function outerFunction() {
  let count = 0;
  function plusOne() {
    count++;
    return count;
  }
  function minusOne() {
    count--;
    return count;
  }

  return {
    plusOne: plusOne(),
    minusOne: minusOne(),
  };
}
const innerFuncs = outerFunction();

console.log(innerFuncs.plusOne);
console.log(innerFuncs.minusOne);
```

```sh
1
0
```

🌕 İlerleme kaydediyorsun. Hızınızı koruyun, iyi işlere devam edin. Şimdi beyniniz ve kasınız için bazı egzersizler yapın.

## 💻 Gün 19: Egzersizleri

### Egzersiz: Seviye 1

1. Bir inner(iç) fonksiyonu olan closure yapısı oluşturun.

### Egzersiz: Seviye 2

1. Üç tane inner(iç) fonksiyonu olan closure yapısı oluşturun.

### Egzersiz: Seviye 3

1. Bir personAccount outer(dış) fonksiyonu oluşturun. Ad, soyad, gelir ve gider inner(iç) değişkenleridir. totalIncome, totalExpense, accountInfo,addIncome, addExpense ve accountBalance inner fonksiyonlara sahiptir.

🎉 TEBRİKLER ! 🎉

[<< Gün 18](../18_Gün_Sözler/18_gün_sözler.md) | [Gün 20 >>](../20_Gün_Temiz_Kod_Yazımı/20_gün_temiz_kod_yazımı.md)
