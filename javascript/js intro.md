Javascript Introduction / Javascript'e Giriş

[TOC]

# Giriş Kurulum

## Vs Code Js Eklentiler


# Temel

## Değişken Tanımlama

- var,let,const

        var : global atama
        let : lokal atama
        const : sabit atama

- const referans bir obje veya array oluşturursak, yeni set edemeyiz, fakat mevcut içinde değişiklik yapabiliriz.

## Veri Tipini Değiştirme

- Veri tipini string e çevirme

        value = String(323);
        value = String(true);
        value = String(function() { console.log()});
        value = String([1,2,3])

        value= (10).toString();

- Veri tipini sayıya çevirme

        value = Number("123");
        value = Number(null); // 0

undefined,string,fonksiyonu ve array'i number a çeviremeyiz.

    value = parseFloat("3.14");
    value = parseInt("3");

- Otomatik Çevirme

        const a = "Hello" + 34 // Hello34
        // 34 ü stringe çevirdi.

## Operatörler ve Math Objesi

    let a = 20
    let b = 10

    a + b
    a - b
    a * b
    a % b  (mod işlemi)

- Math objesi

```javascript
        a = Math.PI
        b = Math.E

        Math.round(3.6) // 4
        Math.ceil(3.2) // 4
        Math.floor(3.6) // 3

        Math.sqrt(16) // 4
        Math.abs(-10) // 10
        Math.pow(2,3) // 8

        Math.max(10,-1,100) // 100
        Math.min(3,9,10) // 3

        Math.random() // 0-1 arasında sayı üretir

        Math.random() * 20 // 0-20 arasında sayı üretir

        Math.floor(Math.random()*20+1); // 1 ile 20 arasında değer üretir
```

## String Metodları

- concatation

        let a = "Ali" + " " + "Kaya"

        a + = ":";

        a.concat(" Sayın"); // a + " Sayın"

- Bazı metodlar

        a.length
        a.toLowerCase();
        a.toUpperCase();

string değeri içindeki karakterlerin indexi 0 dan başlar.

    a[0] // A verir

// indexOf

    a.indexOf("A") // 0
    a.indexOf("x") // -1

// chatAt
    
    a.charAt(0) // A

// split

    let degerler = "Ali,Veli,Kaya";
    degerler.split(","); // [Ali,Veli,Kaya]

// replace

    degerler.replace("Ali","Kemal") // Ali nin yerine Kemali koyar

// includes

    degerler.includes("Veli") // true döner


## Template Literal - String oluşturmada yeni standart

    let name = "Ali Veli";
    let department = "Bilişim"

    const a = `İsim:$(name)\nDepartment$(department)\n`

    const html = `<ul><li>$(name)<li><ul>`

- aritmetik işlem yapabiliriz.
    
        $(10/4) 

## Arraylerin Özellikleri

    const numbers= [15,2,5,6] // stringde ekleyebiliriz.
    
    const numbers = new Array(15,2,5,6)

    const langs = ["Phyton","Java"]

    // uzunluk
    value = numbers.length;

    // indeks ile erişim
    value = numbers[0] // 15
    value = numbers[numbers.length-1] // son elemana erişir

    numbers[0] = 152

    // index of
    numbers.indexOf(5) // 2 verir

    // array sonuna ekler
    numbers.push(200)

    // array başına ekleme
    numbers.unshift(324)

    // arrayin sonundaki elemanı çıkarır
    numbers.pop()

    // arrayin başındaki elemanı çıkarır
    numbers.shift()

    // arrayden eleman çıkarma indeks ile
    numbers.splice(0,2) // indeks 0 ve 2 de olan elemanları çıkarır

    // tersine çevirir
    numbers.reverse()

    // sıralama (string çevirererk göre yapar)
    numbers.sort()

    // sayıları sıralama
    numbers.sort(function(x,y){ // küçükten büyüğe
        return x-y;
    });
 
     
    numbers.sort(function(x,y){ // büyükten küçüğe sırala
    return x-y;
    });
 
 ## Js de Obje Kavramı ve Oluşturma
 
     conts programmer = {
      name : "Ali Kemal",
      age : 25,
      langs : ["Java","Phyton"],
      address : {
        street: "Kaya Mah",
        no : 13
      },
      work: function(){
       console.log("Programcı çalışıyor");
      }
     }

     value = programmer;
     console.log(value);

     // Alanlar Erişim
     value = programmer.name
     value = programmer["email"]

     // Objenin obje elemanın alanına erişim
     value = programmer.address.city;

     // Metod Çağırma
     programmer.work();

    // Array içerisine obje koyma
    const programmers = [
        {name:"Ali Kemal",age:21},
        {name:"Veli Kemal",age:25}
    ]

    value = programmers[0].name; //Ali Kemal


## Js Zaman Objesi ve Metodları

    const now = new Date(); // Şu anki zamanı almamızı sağlar

    const date1 = new Date("9-19-1993 06:15:00");

    date2 = new Date("September 19 1993");

    date3 = new Date("9/19/1993");

    value = date1.getMonth(); // ay indeksini verir, Ocak 0'dan başlar

    date1.getDate(); // ayın kaçıncı günü olduğunu verir

    date1.getDay(); // gün indeksini verir, pazartesi 0 dan başlar

    date1.getHours(); // saati verir

    date1.getMinutes(); // dakikayı verir

    date1.getSeconds(); // saniyeyi verir

    date1.getMiliseconds(); // milisaniyeyi verir

- Bu metodların set hali de var.

        setDate(date:number) // ayın gününü belirler


# Js Temelleri (Bölüm 2)

## Karşılaştırma Operatörleri

    == Eşitlik (Değer) Operatörü
    === Eşitlik (Tip ve Değer) Operatörü

    != Eşit Değildir Operatörü
    !=== Eşit Değildir Operatörü

    > , < , >= , <= 

    2=2 true
    "js" == "java" false
    2=="2" true (2 yi stringe çevirir)
    2 === "2" false (değerleri gibi tipleri aynı olmalı)

## Mantıksal Bağlaçlar

    ! Not Operatörü

    && And Operatörü ( Bir false değer, sonucu false yapar)

    || Or Operatör ( Bir true değer, sonucu true yapar )

## If Statement (if ifadesi)

    if(koşul) {
        //işlemler
    } [else {
      // işlemler
    }] [else if (koşul){
        // işlemler
    }]


const error = false;

if(error==true){
    consolo.log("Hata oluştu");
}

- Kısa if

Tek işlemli if

    if(error==true) console.log("Hata oluştu");

- Ternary If

Ternary Operatörü ? kullanışı

    let sonuc = (number === 100 ? "Sayı 100":"Sayı 100 degil");





## Switch - Case Yapısı

    const = process = 1 ;

    switch(process){

    case 1:
    console.log("1")
    break;
    case 2:
    console.log("1")
    break;
    default:
    console.log("Varsayılan İşlem")
    //break;

    }


## Fonksiyonlar, IIFE ve Anonim Fonksiyonlar

    // Fonksiyon tanımlama
    function merhaba(name,age){
        console.log(`İsim ${name} Yaş: ${age}`);
    }

    // Fonksiyon çağrısı (function call)
    merhaba();

- varsayılan değer atamak istenirse

a. Yol 1

    function merhaba(name,age){
        if(typeof name === "undefined") name ="Bilgi Yok";
        console.log(`İsim ${name} Yaş: ${age}`);
    }

b.

    function merhaba(name= "Bilgi Yok",age){
        if(typeof name === "undefined") name ="Bilgi Yok";
        console.log(`İsim ${name} Yaş: ${age}`);
    }

- return kullanımı ,fonksiyon sonucunda bir değer veya obje döndürmesi

        function square(x){
            return x*x;
        }

return bir fonksiyonu sonlandıran da ifadedir.

- Function Expression

        const merhaba = function(name){
            console.log("Merhaba "+ name);
        }

        merhaba("Murat"); // Murat yazdırır konsole.

- Immediately Invoked Function Expression(IIFE) tanımlandığı yerde çalışan fonksiyon

        (function(name){
          console.log("Merhaba: "+ name);
        })("Murat"); // output: Merhaba: Murat

- objenin içindeyse fonksiyona metod denir, dışında ise fonksiyon denir.

        const database = {
            host: "localhost",
            add: function(){
                console.log("eklendi");
            }
            delete: function(id){
                console.log(`id: ${id} Silindi`);
            }
        }


        database.add()
        database.delete(10);


## Döngüler - While,Do While,For

- While Döngüsü

        let i = 0
        while(i<10){
            console.log(i);
            i++;
            if(i==2){
              continue;
            }
            if(i==8){
              break;
            }
        }

- break kullanırak döngü kırılabilir.

- continue bir sonraki döngüye geçiş yapılabilir.

- Do While Döngüsü

        let i = 0
        do {
          console.log(i)
          i++;
        }while(i<10)


        const langs = ["Phyton,"Javascript","Java"]
        let index = 0;
        while( index < langs.length){
            console.log(langs[index]);
            index++
        }


- For Döngüsü

        for(let index=0;index<langs.length;index++){
          console.log(langs[index]);
        }


- For Each 

        langs.forEach( function(lang){
            console.log(lang);
        });

        langs.forEach( function(lang,index){
            console.log(lang,index);
        });


        const users = [
         {name:"Ali",age:20}
         {name:"Kemal"iage:24}
         {name:"Veli"iage:22}
        ];

        const names = users.map(function(user){
            return user.name;
        });

        console.log(names); // [Ali,Kemal,Veli]

- for in döngüsü

        for( let user in users){
            console.log(
        }

        const = user {
            name:"Mustafa",
            age:25
        };

- **Objenin alanları içinde döngü**

        for ( let key in user){
          console.log(key,user[key]);
        }

        // output: 
        name Mustafa
        age 25


## Window Objesi

- javascript blogumuz window objesinin içerisinde çalışır

        console.log(this); // window objesini döner

        console.log(window); // window objesini döner


        window.location objesi
        window.confirm()
        window.prompt() kullanıcıdan veri almak için

- confirm

        const cevap = confirm("Emin misiniz?");
        console.log(cevap) // true ve false döner kullanıcının cevabına göre

- promp

        const cevap = prompt("2+2 = ?");

        console.log(cevap);

- window.location

        let value = window.location;
        console.log(value);


        window.location.host    // host adresi
        window.location.hostname
        window.location.port
        window.location.href
        window.location.reload() // sayfayı yeniler.

        window.outerHeight // pencere çubuğunu dahil edip yükseklik
        window.outerWidth //

        window.innerHeight // web sayfasının gösterilen panelin yüksekliği
        window.innerWidth

        window.scrollx // yatay scroll'un konumu
        window.scrolly // dikey scrol'un konumu


## Kapsam (Scope) Kavramı - Function Scope, Global Scope, Block Scope


Üç farklı kapsamımız bulunuyor.

Global scope : Herhangi bir fonksiyion için olmayan 

Function scope :

    function a(){
        // function scope
    }

    if(){
        // block scope
    }


- Örnek

        var value1 = 10;
        let value2 = 20;
        const value3= 30;

        function abc(){
            var value1 = 40;
            let value2 = 50;
            const value3= 60;

            console.log(value1,value2,value3); // 40,50,60
        }

        abc();
        console.log(value1,value2,value3); // 10,20,30



- Örnek 2

        if(true){
            var a = 10;
            let b = 20;
            const c=30;
        }

        // var değişkeni dışarıda da var olur.
        console.log(a); //10
        console.log(b); // hata
        console.log(c); // hata



# DOM

Document Object Model

                                                                   |-> Element <head>
    Document -> Root Element <html> -|
                                                                   |-> Element <body>
                                                

## Document Objesi (Part 1)

- Document objesi , window objesinin bir propertisidir / alanıdır.

        // ikis de aynı objesi gösterir
        console.log ( window.document )
        console.log ( this.document )

- Örnek 2

        let value;
        value= document;
        value= document.all;

        value = document.all.lenght // html de kaç element olduğunu gösterir
        value = document.all[0]; // html elementi gösterir
        value = document.all[6]; // 6 'nci elementi döner
        
        
        const elements = document.all; // html collection döner
        
        for ( let i=0; i <element.length;i++) {
            console.log(elements[i]); // bütün eleman tanımlarını gösterir
        }
        
        // elements.forEach xxx collection olduğu için kullanılamaz
        
        const collections = Array.from(document.all);
        
        collections.forEach( function(collection) {
            console.log (collection);
        })
        
        // body e erişmek için
        
        value = document.body;
        value = document.head;
        value = document.location; // location objesinin döner
        value = document.location.hostname //  127.0.0.1
        value = document.location.port // 5500
        value = document.URL; // http://.....
        value = document.characterSet // UTF-8
        
        console.log(value)
        
## Document Objesi (Part 2)

