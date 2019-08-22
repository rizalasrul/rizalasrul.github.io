---
layout: post
menu: Bekerja Dengan Object pada Bahasa Pemrograman JavaScrpt
title: "Bekerja Dengan Object pada JavaScript"
date: 2017-12-27 17:02:12 +0700
categories: object javascript programming
description: object adalah salah satu hal yang fundamental di javascript. yuk simak bagaimana object pada javascript bekerja.
---

<div class="img_row">
  <img class="col three" src="https://miro.medium.com/max/700/1*QN9v1NV0TxVQ4ZefxbCSww.jpeg">
</div>
<div class="col three caption">
  Sintaks JavaScript
</div>

Berdasarkan pengalaman ketika saya memulai belajar JavaScript, memahami object adalah sesuatu yang fundamental. Inti dari JavaScript adalah tipe data object. Jika kita sudah belajar pemrograman Java atau .Net, kita pasti familiar dengan tipe data integer, float, char, dan string sebagai tipe data primitif. Di JavaScript — tidak hanya memiliki tipe data primitif — ia juga memiliki tipe data yang kompleks, yaitu tipe data object sebagai tipe data referensi atau reference

# Object? Apakah itu?
<br />
Object adalah sekumpulan list dari tipe data primitif (terkadang juga tipe data reference) yang menyimpan nilai dengan konsep berpasangan name-value. Tiap item (yang lebih dikenal dengan nama variabel) disebut dengan property, dan function disebut dengan method.

Ini adalah contoh sederhana dari object:

{% highlight js %}
var people  = {
  first_name : "Rizal",
  last_name : "Asrul Pambudi",
}
{% endhighlight %}

Kita sudah tahu bahwa object menyimpan data secara berpasangan name-value nya. Berdasarkan contoh di atas, `first_name` dan `last_name` adalah property. Dan valuenya adalah `Rizal` dan `Asrul Pambudi`.

Nama property dapat berupa string atau number, tetapi jika nama property adalah sebuah number, maka dia diakses dengan cara yang berbeda. Ini adalah contohnya.

{% highlight js %}
var people = {
  name : "Rizal Asrul Pambudi",
  85 : "My weight",
}

console.log(people.85) // This will throw an error
console.log(people['85']) // Correct. This will display "My weight"

// The best way to avoid number as a property name is using square bracket notation.
{% endhighlight %}

# Tipe data reference dan primitif
<br />
Menurut saya, salah satu perbedaan utama antara tipe data reference dan primitif adalah value. Value dari tipe data reference berupa alamat dari variabel yang diisi, sedangkan value dari tipe data primitif berupa nilai. Apa maksutnya?

{% highlight js %}
// Primitive data type number is stored as value
var age   = 24;
var sameAge  = age; // age's value stored in sameAge

age = 20; // age's value changed

console.log(age)  // 20
console.log(sameAge) // 24
{% endhighlight %}

Mari kita bandingkan dengan tipe data object yang bertipe data reference.

{% highlight js %}
// Reference data type is stored as reference
var laptop = {brand : "Toshiba"};
var newLaptop = laptop;

laptop.merk = 'HP';

console.log(newLaptop.brand); // HP
console.log(laptop.brand); // HP
{% endhighlight %}

Lihat, terdapat perbedaan hasil bukan? Itu dikarenakan value dari `laptop` disimpan sebagai reference dan bukan nilai itu sendiri. Dan ketika kita mengubah properti `laptop` jadi “HP”, `newLaptop` juga berubah.

# Dua cara umum untuk membuat object.
<br />
Cara terumum dan termudah untuk membuat object adalah dengan menggunakan teknik object literal.

{% highlight js %}
// This is an empty object initialized using object literal notation
var emptyObject = {};

// This is an object with 4 items using object literal notation too
var banana = {
  color : 'yellow',
  shape : 'long',
  price : 5000,

  printFlavour : function() { // This is the example of create method in object
    console.log('so sweet');
  }
};
{% endhighlight %}

Cara kedua adalah dengan teknik object constructor. Constructor adalah function yang digunakan untuk inisialisasi object baru, dan kita menggunakan keyword newuntuk menggunakannya.

{% highlight js %}
// This is an empty object initialized using object constructor notation
var banana = new Object();

// And then we initialize it with 4 items
banana.color = 'yellow';
banana.shape = 'long';
banana.price = 5000;
banana.printFlavour = function() {
  console.log('so sweet');
};
{% endhighlight %}

# Kesimpulan
<br />
Inti JavaScript — yang paling sering digunakan dan paling fundamental — tipe data adalah object. Satu perbedaan utama antara tipe data primitif dan reference adalah tipe data reference menggunakan alamat sebagai nilai dari datanya, sedangkan tipe data primitif menggunakan nilai itu sendiri. Terdapat dua cara umum untuk membuat object: object literal dan constructor.
