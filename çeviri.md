# HTML ile İçeriği Yapılandırma

Bu belge, MDN Web Docs (Mozilla Developer Network) bünyesindeki **"Structuring content with HTML"** modülünün tüm derslerini, sınavlarını ve uygulama meydan okumalarını (challenges) orijinal sayfa yapısı, boşlukları, kod blokları, tabloları ve teknik sözdizimleri birebir korunarak Türkçeye aktarılmış eksiksiz başvuru kaynağıdır.

---

## İçindekiler

1. [Temel HTML sözdizimi](#1-temel-html-sözdizimi)
2. [Web sayfası meta verileri](#2-web-sayfası-meta-verileri)
3. [Başlıklar ve paragraflar](#3-başlıklar-ve-paragraflar)
4. [Vurgu ve önem derecesi](#4-vurgu-ve-önem-derecesi)
5. [Listeler](#5-listeler)
6. [Test: HTML metin temelleri](#6-test-html-metin-temelleri)
7. [İleri düzey metin özellikleri](#7-ileri-düzey-metin-özellikleri)
8. [Test: İleri düzey HTML metinleri](#8-test-ileri-düzey-html-metinleri)
9. [Uygulama Görevi: Mektup işaretleme](#9-uygulama-görevi-mektup-işaretleme)
10. [Belgeleri yapılandırma](#10-belgeleri-yapılandırma)
11. [Bağlantı oluşturma](#11-bağlantı-oluşturma)
12. [Test: Bağlantılar](#12-test-bağlantılar)
13. [Uygulama Görevi: Kuş gözlem sitesi](#13-uygulama-görevi-kuş-gözlem-sitesi)
14. [Görseller](#14-görseller)
15. [Test: Görseller](#15-test-görseller)
16. [Video ve ses](#16-video-ve-ses)
17. [Test: Ses ve video](#17-test-ses-ve-video)
18. [Uygulama Görevi: Tanıtım sayfası](#18-uygulama-görevi-tanıtım-sayfası)
19. [Tablo temelleri](#19-tablo-temelleri)
20. [Tablo erişilebilirliği](#20-tablo-erişilebilirliği)
21. [Uygulama Görevi: Gezegen veri tablosu](#21-uygulama-görevi-gezegen-veri-tablosu)
22. [Formlar ve butonlar](#22-formlar-ve-butonlar)
23. [Test: Formlar ve butonlar](#23-test-formlar-ve-butonlar)
24. [Uygulama Görevi: Geri bildirim formu](#24-uygulama-görevi-geri-bildirim-formu)
25. [HTML hata ayıklama](#25-html-hata-ayıklama)
26. [Test: HTML testleri indeksi](#26-test-html-testleri-indeksi)
27. [Ek kılavuzlar](#27-ek-kılavuzlar)
    * 27.1. [Vektör grafikleri](#271-vektör-grafikleri)
    * 27.2. [Gömme teknolojileri](#272-gömme-teknolojileri)

---

# 1. Temel HTML sözdizimi

**HTML** > **Basic HTML syntax** | English (US)

Bu makalede terminoloji, sözdizimi ve yapı dahil olmak üzere HTML'in temellerini ele alıyoruz. Bu süreçte, temel HTML yazma konusunda pratik kazanmanız için bazı etkileşimli görevleri tamamlayacaksınız.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | Temel yazılımların kurulu olması ve dosyalarla çalışma konusunda temel bilgiye sahip olunması. |
| **Learning outcomes (Öğrenim çıktıları):** | • Bir HTML elementinin anatomisi — element, açılış etiketi (opening tag), içerik (content), kapanış etiketi (closing tag), nitelikler (attributes).<br>• HTML body ve sayfa içeriği için bir kapsayıcı olarak üstlendiği amaç.<br>• Void (boş) elementlerin ne olduğu ve diğer elementlerden nasıl ayrıldıkları.<br>• HTML belgelerinin en üstünde bir doctype bulunmasının gerekliliği; bunun orijinal amacı ve günümüzde neden bir tarihsel kalıntı niteliğinde olduğu.<br>• HTML elementlerinin doğru bir şekilde iç içe (nested) yerleştirilmesi gerektiğinin kavranması. |

---

## HTML nedir?

HTML (**HyperText Markup Language**), ziyaret ettiğiniz web sayfalarını nasıl yapılandıracaklarını web tarayıcılarına bildiren bir *işaretleme dilidir (markup language)*. HTML; içeriğin belirli bir biçimde görünmesini veya davranmasını sağlamak amacıyla, içeriğin farklı kısımlarını içine almak, sarmak veya işaretlemek için kullandığınız bir dizi **element**ten oluşur. Kapsayan etiketler, bir içeriği başka bir sayfaya bağlanan bir köprüye (hyperlink) dönüştürebilir, sözcükleri italik yapabilir ve benzeri birçok işlevi gerçekleştirebilir. Örneğin, aşağıdaki metin satırını ele alalım:

```text
My cat is very grumpy
```

Bu metnin bir paragraf olduğunu, onu paragraf (`<p>`) etiketleri içine sararak belirtebiliriz:

```html
<p>My cat is very grumpy</p>
```

Veya bu metnin en üst düzey bir başlık olduğunu, onu `<h1>` etiketleri içine alarak belirtebiliriz:

```html
<h1>My cat is very grumpy</h1>
```

HTML, `.html` dosya uzantısına sahip ve **HTML belgeleri** (veya kısaca *belgeler / documents*) olarak adlandırılan metin dosyalarının içinde yaşar. Daha önce "web sayfaları" olarak adlandırdığımız şeylerin temelinde, web sayfasının içeriğini barındıran ve yapısını belirleyen bir HTML belgesi yer alır.

En sık karşılaşacağınız HTML dosyası `index.html` dosyasıdır; bu dosya genel olarak bir web sitesinin ana sayfa içeriğini barındırmak için kullanılır. Ayrıca kendi `index.html` dosyalarına sahip alt klasörlerin bulunması da yaygındır; bu sayede bir web sitesi farklı konumlarda birden çok dizin dosyasına sahip olabilir.

> **Note:** HTML'deki etiketler büyük/küçük harfe duyarlı değildir (case-insensitive). Bu, etiketlerin büyük veya küçük harfle yazılabileceği anlamına gelir. Örneğin bir `<title>` etiketi `<title>`, `<TITLE>`, `<Title>`, `<TiTlE>` vb. şekillerde yazılabilir ve çalışmaya devam eder. Ancak tutarlılık ve okunabilirlik açısından tüm etiketleri **küçük harfle** yazmak en iyi uygulamadır (best practice).

---

## Bir HTML elementinin anatomisi

Önceki bölümdeki paragraf elementimizi daha ayrıntılı inceleyelim:

```text
       Opening tag                                     Closing tag
     ┌─────────────┐                                 ┌─────────────┐
     │             │                                 │             │
     ▼             ▼                                 ▼             ▼
    <p>            My cat is very grumpy             </p>
    └──┬───────────┴─────────────────────────────────┴───────────┬──┘
       │                        Content                          │
       │                   ┌───────────────┐                     │
       │                   │               │                     │
       └───────────────────┤    Element    ├─────────────────────┘
                           │               │
                           └───────────────┘
```

Tam bir element şu parçalardan meydana gelir:

* **The opening tag (Açılış etiketi):** Elementin adından (bu örnekte paragraf için `p`) oluşur ve açılış ile kapanış açılı ayraçları (`<` ve `>`) içine sarılır. Bu açılış etiketi, elementin nereden başladığını veya nerede yürürlüğe girdiğini işaret eder. Bu örnekte paragraf metninin başlangıcından önce yer alır.
* **The content (İçerik):** Elementin içeriğidir. Bu örnekte paragraf metninin kendisidir: `"My cat is very grumpy"`.
* **The closing tag (Kapanış etiketi):** Açılış etiketiyle aynıdır; tek farkı, element adının önüne bir eğik çizgi (`/`) almasıdır. Bu etiket elementin nerede bittiğini belirler. Kapanış etiketini koymayı unutmak, yeni başlayanların sıkça yaptığı ve garip sonuçlara yol açabilen yaygın bir hatadır.
* **The element (Element):** Açılış etiketi, içerik ve kapanış etiketinin tamamının oluşturduğu yapıdır.

---

## İlk HTML elementinizi oluşturma

Kendi HTML elementlerinizi yazma konusunda pratik yapalım:

1. Örneği düzenlemek için kod bloğundaki adımları izleyin.
2. Metin satırını `<em>` ve `</em>` etiketleriyle sarın. Elementi açmak için açılış etiketini (`<em>`) satırın başına yerleştirin. Elementi kapatmak için kapanış etiketini (`</em>`) satırın sonuna yerleştirin. Bunu yapmak, ekranda gösterilen metni italik olarak biçimlendirmelidir.
3. Kendinizi cesur hissediyorsanız, daha fazla HTML elementi araştırıp bunları metin örneğine uygulamayı deneyin.

```html
This is my text.
```

Etiket uygulandıktan sonra:

```html
<em>This is my text.</em>
```

Tarayıcı çıktısı:

*This is my text.*

---

## Elementleri iç içe yerleştirme

Elementler başka elementlerin içine yerleştirilebilir. Buna **iç içe yerleştirme (nesting)** adı verilir. Kedimizin çok huysuz olduğunu vurgulamak isteseydik, `very` kelimesini bir `<strong>` elementi içine alabilirdik; bu da kelimeye daha güçlü bir metin biçimlendirmesi kazandırır:

```html
<p>My cat is <strong>very</strong> grumpy.</p>
```

Bu kod bloğunda `"My cat is very grumpy."` metninin tamamı bir paragraf olarak tanımlanmıştır. `"very"` kelimesi ise ayrıca güçlü bir öneme (strong importance) sahip olarak tanımlanmıştır.

İç içe yerleştirmenin doğru ve yanlış bir yolu vardır. Yukarıdaki kod bloğunda önce `<p>` elementini açtık, ardından `<strong>` elementini açtık. Doğru iç içe yerleştirme için önce `<strong>` elementini kapatmalı, ardından `<p>` elementini kapatmalıyız.

Aşağıdaki örnek iç içe yerleştirmenin **yanlış** yapılışına bir örnektir:

```html
<!-- YANLIŞ KULLANIM: Etiketler birbiriyle çakışıyor -->
<p>My cat is <strong>very grumpy.</p></strong>
```

Etiketler, birbirinin içinde ya da dışında olacak şekilde açılıp kapanmalıdır. Önceki kod bloğunda elementler birbiriyle çakıştığı için, tarayıcı sizin niyetinizi tahmin etmek zorunda kalır. Bu tür bir tahmin öngörülemeyen sonuçlara yol açabilir.

---

## Boş elementler

Tüm elementler açılış etiketi, içerik ve ardından kapanış etiketi düzenini takip etmez. Bazı elementler tek bir etiketten oluşur ve genellikle belgeye bir şey eklemek/gömmek amacıyla kullanılır. Bu tür elementlere **void elements (boş elementler)** adı verilir; bu terim "başka HTML içeriği barındıramayan elementler" anlamına gelir.

Örneğin, `<br>` elementi bir metin satırına satır sonu (line break) ekleyerek metnin birden fazla satıra bölünmesini sağlar:

```html
<p>
This is a single paragraph, but we are going to <br />break it onto two lines.
</p>
```

Bu kod şu şekilde işlenir (render edilir):

This is a single paragraph, but we are going to  
break it onto two lines.

> **Note:** Bazı HTML örneklerinde, boş bir element etiketinin sonuna bir `/` eklendiğini görebilirsiniz; örneğin `<br />`. Bu farklı bir biçimlendirme sözdizimi tarzıdır (XHTML kalıntısıdır); yanlış değildir, ancak bu "kapanış eğik çizgisi" HTML5 için gerekli değildir.

---

## Nitelikler

Elementler ayrıca **niteliklere (attributes)** sahip olabilir. Nitelikler şu şekilde görünür:

```text
                 Attribute
            ┌─────────────────┐
            │                 │
            ▼                 ▼
   <p class="editor-note">My cat is very grumpy</p>
```

Nitelikler, element hakkında içeriğinin parçası olmayan ek bilgiler barındırır. `class` niteliği, elementi stillerle (CSS) veya betik bilgileriyle (JavaScript) hedeflemek için kullanılabilecek tanımlayıcı bir ad sağlar.

Bir nitelik şunlara sahip olmalıdır:

* Nitelik ile element adı arasında bir boşluk. Bir element birden fazla niteliğe sahip olduğunda, nitelikler de birbirlerinden boşluklarla ayrılmalıdır.
* Nitelik adı, ardından gelen bir eşittir işareti (`=`).
* Açılış ve kapanış tırnak işaretleri içine alınmış bir nitelik değeri.

---

## Bir elemente nitelik ekleme

Sayfada bir görsel göstermek için kullanılan `<img>` elementini inceleyelim. `<img>` elementi aşağıdakiler de dahil olmak üzere birçok nitelik alabilir:

* `src`: Görselin URL'sini (web adresini) belirten **zorunlu** bir niteliktir. Örneğin:  
  `src="https://mdn.github.io/shared-assets/images/examples/fx-nightly-512.png"`
* `alt`: Görseli göremeyen kişiler için metin açıklaması belirtir. Örneğin: `alt="The Firefox Nightly icon"`. Bu nitelik teknik olarak zorunlu olmasa da, anlam ileten tüm görseller için (tamamen dekoratif olanların aksine) mutlaka bir metin açıklaması sağlamalısınız.
* `width`: Görselin genişliğini piksel cinsinden belirtir. Örneğin: `width="300"`.
* `height`: Görselin yüksekliğini piksel cinsinden belirtir. Örneğin: `height="300"`.

Örnek kullanım:

```html
<img src="https://mdn.github.io/shared-assets/images/examples/fx-nightly-512.png" 
     alt="The Firefox Nightly icon" 
     width="300" 
     height="300" />
```

---

## Boolean nitelikler

Bazen HTML niteliklerinin değer atanmadan yazıldığını görürsünüz. Bunlara **Boolean nitelikler (Boolean attributes)** denir. Bir boolean nitelik eklendiğinde, kendisine hangi değer atanırsa atansın (hatta hiçbir değer atanmasa bile) değeri `true` olarak kabul edilir. Bir nitelik HTML etiketinde yer almıyorsa, değeri `false` olarak kabul edilir.

Örneğin, kullanıcının form alanlarına veri girmesini engellemek için `<input>` elementlerine atayabileceğiniz `disabled` niteliğini ele alalım:

```html
<label for="first-input">This input is disabled</label>
<input id="first-input" type="text" disabled="disabled" />
<br />
```

Kısa yazım olarak, `disabled` niteliğini bir değer belirtmeden yazmak tamamen geçerlidir:

```html
<label for="second-input">This input is also disabled</label>
<input id="second-input" type="text" disabled />
<br />
```

Karşılaştırma amacıyla, devre dışı bırakılmamış bir `<input>` elementi de ekleyelim:

```html
<label for="third-input">This input isn't disabled; you can type into it</label>
<input id="third-input" type="text" />
```

> **Note:** Yukarıdaki koddaki `<label>` elementleri, açıklayıcı etiketleri form kontrolleriyle ilişkilendirmenin bir yolunu sağlar. Bunları en iyi uygulama olduğu ve form girdileri arasında bir miktar ayrım sağladığı için ekledik.

---

## Nitelik değerleri etrafındaki tırnak işaretlerini atlama

Belirli durumlarda nitelik değerlerinin etrafındaki tırnak işaretlerini atlamak mümkündür. Ancak bu durum başka koşullarda işaretlemenizi bozabileceğinden, **tırnak işaretlerini her zaman eklemenizi öneririz**. Nedenini inceleyelim.

Aşağıdaki kod parçacığında yer alan `<a>` elementi **bağlantı (anchor)** olarak adlandırılır. Bağlantılar metni sarar ve linke dönüştürür. `href` niteliği bağlantının işaret ettiği URL'yi belirtir. Aşağıda gösterilen `href` niteliği değerinin etrafındaki tırnak işaretlerini hiçbir olumsuz sonuç olmadan atlayabilirsiniz, çünkü içinde hiç boşluk karakteri yoktur:

```html
<a href=https://www.mozilla.org/>favorite website</a>
```

Ancak boşluk içeren nitelik değerlerinde tırnak işaretlerini atladığınızda sorunlarla karşılaşırsınız. Aşağıda gösterilen ve bağlantı üzerine fare imleci getirildiğinde bir ipucu (tooltip) olarak görünmesi gereken sayfa açıklamasını (`"The Mozilla homepage"`) sağlayan `title` niteliğini ele alalım:

```html
<!-- YANLIŞ KULLANIM: Tırnak işaretleri eksik -->
<a href=https://www.mozilla.org/ title=The Mozilla homepage>favorite website</a>
```

`title` niteliği değerinin etrafına tırnak işaretleri konulmadığı için tarayıcı bunu üç ayrı nitelik olarak yorumlar: değeri `The` olan bir `title` niteliği ve iki adet Boolean nitelik (`Mozilla` ve `homepage`). Doğal olarak amaçladığımız şey bu değildir!

**Kural:** Nitelik değerlerinin etrafına daima tırnak işaretleri koyun. Bu, hataları ve istenmeyen davranışları önler ve daha okunabilir kod sağlar.

---

## Tek tırnak mı yoksa çift tırnak mı?

Bu makalede tüm nitelik değerlerimizi çift tırnak (`"`) içine aldık. Ancak bazı HTML kodlarında tek tırnak (`'`) kullanıldığını da görebilirsiniz. Bu bir stil tercihidir; hangisini tercih edeceğinizi seçmekte özgürsünüz. Bu iki satır tamamen eşdeğerdir:

```html
<a href='https://www.example.com'>A link to my example.</a>
<a href="https://www.example.com">A link to my example.</a>
```

Tek tırnak ve çift tırnakları birbiriyle **karıştırmadığınızdan** emin olun. Aşağıdaki örnek tırnakları karıştırmaktadır; tarayıcı açısından `href` niteliği değeri henüz sonlandırılmadığı için bu durum hatalara yol açacaktır:

```html
<!-- HATALI KULLANIM -->
<a href="https://www.example.com'>A link to my example.</a>
```

Bir tür tırnak işareti kullanıyorsanız, diğer tür tırnak işaretini nitelik değerlerinizin içine sorunsuzca dahil edebilirsiniz:

```html
<a href="https://www.example.com" title="Isn't this fun?">A link to my example.</a>
```

Aynı türdeki tırnak işaretlerini (çift tırnak içinde çift tırnak gibi) kullanmak için **karakter referanslarını (character references)** kullanabilirsiniz. Örneğin şu kullanım yapıyı bozar:

```html
<!-- HATALI KULLANIM -->
<a href="https://www.example.com" title="An "interesting" reference">A link to my example.</a>
```

Bunun yerine şu şekilde yazmanız gerekir:

```html
<a href="https://www.example.com" title="An &quot;interesting&quot; reference">A link to my example.</a>
```

---

## Bir HTML belgesinin anatomisi

Tekil HTML elementleri tek başlarına pek kullanışlı değildir. Şimdi tek tek elementlerin bir araya gelerek bütün bir HTML sayfasını nasıl oluşturduğunu inceleyelim.

Aşağıdaki örnek çok basit, eksiksiz bir web sayfasıdır:

```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>
```

Bu örneğin parçaları şu şekildedir:

1. `<!doctype html>`: Doctype (belge türü tanımı). HTML'in ilk dönemlerinde (1991-1992), doctype'ların HTML sayfasının "iyi bir HTML" sayılması için uyması gereken bir kurallar kümesine bağlantı görevi görmesi amaçlanmıştı. Doctype'lar eskiden şuna benzer görünürdü:
   ```html
   <!doctype html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
   "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
   ```
   Modern zamanlarda doctype, diğer her şeyin doğru çalışması için dahil edilmesi gereken tarihsel bir kalıntıdır. `<!doctype html>`, geçerli bir doctype sayılan en kısa karakter dizisidir ve tüm web sayfalarının en üstüne eklenmelidir. Bilmeniz gereken tek şey budur!
2. `<html></html>`: `<html>` elementi. Bu element sayfadaki tüm içeriği sarar. Bazen **kök element (root element)** olarak da adlandırılır.
3. `<head></head>`: `<head>` elementi. Bu element, kullanıcıların göreceği içeriğin parçası olmayan, sayfayla ilgili bilgilerin yer aldığı bir kapsayıcı görevi görür. Bu alan arama sonuçlarında gösterilecek anahtar kelimeleri ve sayfa açıklamasını, içeriği stillendirmek için CSS'i, karakter seti bildirimlerini ve daha fazlasını içerebilir.
4. `<meta charset="utf-8">`: Bir `<meta>` elementi. Bu element sayfayı tanımlayan metadata'yı temsil eder. `charset` niteliği belgenizin kullanacağı karakter kodlamasını (character encoding) belirtir. `UTF-8`, insan tarafından yazılan dillerin büyük çoğunluğundaki çoğu karakteri kapsar; bu da sayfanın farklı dilleri başarıyla görüntüleyebileceği anlamına gelir. Bunu ayarlamamak için hiçbir neden yoktur ve ileride çıkabilecek sorunları önlemeye yardımcı olur.
5. `<title></title>`: `<title>` elementi. Sayfanın başlığını belirler; bu başlık, sayfanın yüklendiği tarayıcı sekmesinde görünen başlıktır. Sayfa başlığı ayrıca sayfaya yer işareti (bookmark) eklendiğinde onu tanımlamak için de kullanılır.
6. `<body></body>`: `<body>` elementi. Metin, görseller, videolar, oyunlar, oynatılabilir ses parçaları vb. dahil olmak üzere sayfada görüntülenen tüm içeriği barındırır.

---

## Bir HTML belgesine özellikler ekleme

Örnek kurulum ve yönergeler:

1. Önceki bölümde listelenen HTML sayfası örneğini kod editörünüzde yeni bir dosyaya kopyalayın.
2. `<body>` elementinin açılış etiketinin hemen altına belge için ana bir başlık ekleyin. Bu başlık `<h1></h1>` etiketleriyle sarılmalıdır.
3. İlginizi çeken bir konu hakkında metin içerecek şekilde paragraf içeriğini düzenleyin.
4. Önemli kelimeleri bir `<strong>` elementi içine alarak kalınlaştırın.
5. Paragrafınıza iki bağlantı ekleyin. Bu işlem `<a>` elementi kullanılarak gerçekleştirilir.
6. Belgenize paragrafın altına daha önce açıklandığı gibi bir görsel ekleyin. Eğer ekranda çok büyük görünüyorsa, boyutunu küçültmek için bir `width` niteliği ekleyin.
7. Dosyayı `index.html` olarak kaydedin ve sonuçları görmek için yeni bir tarayıcı sekmesinde açın.

---

## HTML'de boşluk kullanımı

Önceki örneklerde koda çok sayıda boşluk dahil ettik. Çoğu durumda bu tamamen isteğe bağlıdır ve esas olarak kodu daha okunabilir hale getirmek için dahil edilir. Örneğin, bu iki kod parçacığı tamamen eşdeğerdir:

```html
<p id="noWhitespace">Dogs are silly.</p>

<p id="whitespace">Dogs
are
silly.</p>
```

Her ikisi de tamamen aynı şekilde işlenir:

Dogs are silly.

Dogs are silly.

Hemen hemen tüm elementlerde (istisnalar mevcuttur; örneğin `<pre>`), HTML elementi içeriğinde ne kadar boşluk kullanırsanız kullanın, HTML ayrıştırıcısı (parser) kodu işlerken her ardışık boşluk dizisini tek bir boşluğa indirger.

Bir kod biçimlendirme stili seçmek size bağlıdır. Her iç içe yerleştirilmiş elemente, içinde bulunduğu elementten iki boşluk daha fazla girinti (indentation) vermek yaygın bir tercihtir; MDN'de kullandığımız stil de budur:

```html
<section>
  <div>
    <p>A paragraph of content.</p>
  </div>
</section>
```

---

## Karakter referansları: HTML'e özel karakterler dahil etme

HTML'de `<`, `>`, `"`, `'` ve `&` karakterleri özel karakterlerdir. Bunlar HTML sözdiziminin doğrudan birer parçasıdır. Peki bu özel karakterleri metninizin içine nasıl dahil edebilirsiniz? Örneğin, bir ampersand (`&`) veya küçüktür (`<`) işaretinin kod olarak yorumlanmadan içeriğinizde harfi harfine kullanılmasını nasıl sağlarsınız?

Bunu **karakter referansları (character references)** ile yaparsınız. Bunlar, tam olarak bu koşullarda kullanılmak üzere karakterleri temsil eden özel kodlardır. Her karakter referansı bir ampersand (`&`) ile başlar ve bir noktalı virgül (`;`) ile biter.

| Literal character (Düz karakter) | Character reference equivalent (Eşdeğer karakter referansı) | Anlamı / Kısaltma kökeni |
| :---: | :---: | :--- |
| `<` | `&lt;` | "less than" (küçüktür) |
| `>` | `&gt;` | "greater than" (büyüktür) |
| `"` | `&quot;` | "quotation" (tırnak işareti) |
| `'` | `&apos;` | "apostrophe" (kesme işareti) |
| `&` | `&amp;` | "ampersand" (ve işareti) |

Aşağıdaki örnekte iki paragraf bulunmaktadır:

```html
<p>In HTML, you define a paragraph using the <p> element.</p>
<p>In HTML, you define a paragraph using the &lt;p&gt; element.</p>
```

Bu kod şu şekilde işlenir:

In HTML, you define a paragraph using the  
element.  
In HTML, you define a paragraph using the `<p>` element.

İlk paragraf bozulmuştur; çünkü tarayıcı ikinci `<p>` ifadesini yeni bir paragrafın başlangıcı olarak yorumlamıştır. İkinci paragraf ise sorunsuz işlenir, çünkü `<p>` içeriğinin açılı ayraçları karakter referanslarıyla temsil edilmiştir.

> **Note:** HTML belgenizin karakter kodlaması `UTF-8` olarak ayarlandığı sürece diğer simgeler için entity referansları kullanmanıza gerek yoktur; modern tarayıcılar gerçek simgeleri sorunsuz bir şekilde işleyecektir.

---

## HTML yorumları

HTML, kodun içine yorum yazmak için bir mekanizmaya sahiptir. Tarayıcılar yorumları yoksayar, bu nedenle yorumlar kullanıcıya görünmez. Yorumların amacı, kodun nasıl çalıştığını açıklamak için koda notlar eklemenize izin vermektir. Bu, bir kod tabanına uzun bir süre ara verip hatırlayamadığınızda veya daha önce hiç görmemiş başka biri üzerinde çalışmaya başladığında son derece yararlıdır.

Bir HTML yorumu yazmak için, onu aşağıda gösterildiği gibi `<!--` ve `-->` özel işaretleyicileri içine sarın:

```html
<p>I'm not inside a comment</p>
<!-- <p>I am!</p> -->
```

Bu kod şu şekilde işlenir:

I'm not inside a comment

Canlı çıktıda yalnızca ilk paragraf görüntülenir; ikinci satır bir HTML yorumu olduğu için ekrana yansıtılmaz.

---

## Özet

Makalenin sonuna ulaştınız! HTML'in temellerini keşfetmekten keyif aldığınızı umuyoruz.

Bu noktada HTML'in neye benzediğini ve temel düzeyde nasıl çalıştığını anlamış olmalısınız. Ayrıca birkaç element ve nitelik yazabilecek durumda olmalısınız. Bu modülün sonraki makaleleri, burada tanıtılan bazı konuları daha derinlemesine ele alacak ve ek konular sunacaktır.

> **Note:** HTML hakkında daha fazla bilgi edinmeye başladıkça, web sayfalarını stillendirmek (örneğin renkleri, yazı tiplerini ve boşlukları değiştirmek) için kullanılan dil olan **CSS**'in temellerini de öğrenmeyi düşünebilirsiniz. HTML ve CSS çoğu web sayfasında birlikte kullanılır ve bunları aynı anda öğrenmek oldukça etkili olabilir.

---
# 2. Web sayfası meta verileri

**HTML** > **What's in the head? Web page metadata** | English (US)

Bir HTML belgesinin head kısmı, sayfa web tarayıcısında yüklendiğinde görüntülenmeyen kısımdır. Sayfa `<title>` elementi, CSS bağlantıları (HTML içeriğinizi CSS ile stillendirmek istiyorsanız), özel favicon bağlantıları ve diğer metadata (HTML hakkında yazar ve belgeyi tanımlayan önemli anahtar kelimeler gibi veriler) gibi bilgileri içerir.

Web tarayıcıları, HTML belgesini doğru şekilde işlemek için `head` içinde yer alan bilgileri kullanır. Bu makalede, işaretleme diliyle çalışırken sağlam bir temel oluşturmanız için yukarıdakilerin tümünü ve daha fazlasını ele alacağız.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | Önceki derste ele alındığı gibi temel HTML aşinalığı. |
| **Learning outcomes (Öğrenim çıktıları):** | • HTML head ve belgenin metadata kapsayıcısı olarak üstlendiği amaç.<br>• Belge karakter kodlamasını (character encoding) ve başlığını (`<title>`) ayarlama.<br>• Arama motorları için metadata sağlama.<br>• Tarayıcılarda ve mobil platformlarda kullanılmak üzere simgelere (icons/favicons) bağlantı verme.<br>• Stil sayfalarına (stylesheets) ve betik (script) dosyalarına bağlantı verme.<br>• Açılış `<html>` etiketinde `lang` niteliğini kullanarak belgenin dilini belirleme gerekliliği. |

---

## HTML head nedir?

Önceki makalede ele aldığımız basit HTML belgesine tekrar göz atalım:

```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>
```

HTML head, `<head>` elementinin içeriğidir. Bir tarayıcıda yüklendiğinde sayfada görüntülenen `<body>` elementinin içeriğinin aksine, head'in içeriği sayfada görüntülenmez. Bunun yerine head'in görevi, belge hakkında **metadata (üst veri)** barındırmaktır. Yukarıdaki örnekte head oldukça küçüktür:

```html
<head>
  <meta charset="utf-8" />
  <title>My test page</title>
</head>
```

Bununla birlikte, daha büyük sayfalarda head oldukça kapsamlı hale gelebilir. En sevdiğiniz web sitelerinden bazılarına giderek geliştirici araçlarını (developer tools) açıp head içeriklerini incelemeyi deneyin. Buradaki amacımız head içine konulabilecek her şeyi tek tek göstermek değil; head içine dahil etmek isteyeceğiniz başlıca elementleri nasıl kullanacağınızı öğretmek ve aşinalık kazandırmaktır.

---

## Bir başlık ekleme

`<title>` elementinin işlevini daha önce görmüştük — bu element belgeye bir başlık eklemek için kullanılır. Ancak bu element, gövde içeriğinize en üst düzey başlık eklemek için kullanılan ve bazen sayfa başlığı olarak da anılan `<h1>` elementi ile karıştırılabilir. Fakat ikisi tamamen farklı şeylerdir!

* `<h1>` elementi, tarayıcıda yüklendiğinde sayfanın içinde görünür — genel olarak sayfa içeriğinizin başlığını (makale başlığı, haber manşeti veya kullanımınıza uygun olan metin) işaretlemek için sayfa başına bir kez kullanılmalıdır.
* `<title>` elementi ise sayfa içeriğinin değil, bütün bir HTML belgesinin başlığını temsil eden bir metadata'dır.

### Bir örneği inceleme

1. Bu alıştırmada `title-example.html` sayfasını kod editörünüzde açın veya kodunu kopyalayıp yeni bir dosyaya yapıştırın.
2. Dosyayı tarayıcınızda açın. Tarayıcı sekmesinde `<title>` metnini, sayfa gövdesinde ise `<h1>` başlık metnini göreceksiniz.
3. Artık `<h1>` içeriğinin nerede, `<title>` içeriğinin nerede göründüğü son derece nettir!

`<title>` elementinin içeriği başka alanlarda da kullanılır. Örneğin, sayfayı yer imlerine eklemeye çalıştığınızda (Firefox'ta *Yer İmleri > Bu Sayfayı Yer İmlerine Ekle* veya adres çubuğundaki yıldız simgesi), yer imi adı olarak `<title>` içeriğinin önerildiğini görürsünüz. Ayrıca `<title>` içeriği arama motoru sonuçlarında da başlık olarak kullanılır.

---

## Meta veriler: `<meta>` elementi

Metadata, veriyi tanımlayan veridir ve HTML'in bir belgeye metadata eklemek için sunduğu resmi yöntem `<meta>` elementidir. Sayfanızın `<head>` bölümüne eklenebilecek pek çok farklı türde `<meta>` elementi vardır. Şimdi en yaygın kullanılanları inceleyelim.

### Belgenizin karakter kodlamasını belirtme

Yukarıda gördüğümüz örnekte şu satır yer alıyordu:

```html
<meta charset="utf-8" />
```

Bu element belgenin karakter kodlamasını —belgenin kullanmasına izin verilen karakter kümesini— belirtir. `utf-8`, insan dillerinin neredeyse tamamındaki tüm karakterleri içeren evrensel bir karakter kümesidir. Bu, web sayfanızın herhangi bir dili görüntüleyebileceği anlamına gelir; bu nedenle oluşturduğunuz her web sayfasına bunu eklemeniz önerilir! Örneğin sayfanız hem İngilizceyi hem de Japoncayı sorunsuz şekilde işleyebilir.

Eğer karakter kodlamanızı örneğin `ISO-8859-1` (Latin alfabesi için karakter kümesi) olarak ayarlarsanız, Japonca karakterler içeren sayfanız bozulabilir:

> [!NOTE]
> Chrome gibi bazı tarayıcılar hatalı kodlamaları otomatik olarak düzeltir, bu nedenle kullandığınız tarayıcıya bağlı olarak bu sorunu görmeyebilirsiniz. Yine de diğer tarayıcılarda olası sorunları önlemek için sayfanıza mutlaka `utf-8` kodlamasını eklemelisiniz.

Karakter kodlamasını test etmek için şu kodu deneyebilirsiniz:

```html
<p>Japanese example: ご飯が熱い。</p>
```

### Yazar ve açıklama ekleme

Pek çok `<meta>` elementi `name` ve `content` niteliklerini içerir:

* `name`: Meta elementinin türünü; ne tür bir bilgi barındırdığını belirtir.
* `content`: Gerçek meta içeriğini belirtir.

Sayfanıza eklenmesi faydalı olan iki meta element, sayfanın yazarını tanımlar ve sayfanın kısa bir açıklamasını sunar:

```html
<meta name="author" content="Chris Mills" />
<meta
  name="description"
  content="The MDN Web Docs Learning Area aims to provide
complete beginners to the Web with all they need to know to get
started with developing websites and applications." />
```

* **Yazar belirtmek** birçok açıdan faydalıdır: İçerikle ilgili bir sorunuz olduğunda sayfayı kimin yazdığını bilmek ve iletişime geçebilmek yararlıdır. Bazı içerik yönetim sistemleri yazar bilgilerini otomatik olarak ayıklayabilir.
* **Açıklama belirtmek**, sayfanızın içeriğiyle ilgili anahtar kelimeleri içermesi bakımından çok kullanışlıdır; çünkü sayfanızın arama motorlarında yapılan ilgili aramalarda daha üst sıralarda yer alma potansiyelini artırır (bu tür faaliyetlere **Arama Motoru Optimizasyonu** veya **SEO** denir).

Açıklama ayrıca arama motoru sonuç sayfalarında (SERP) snippet olarak gösterilir.

> [!NOTE]
> Artık kullanılmayan birçok `<meta>` özelliği bulunmaktadır. Örneğin, arama motorlarının sayfanın alaka düzeyini belirlemesi amacıyla anahtar kelimeler sağlaması beklenen anahtar kelime meta elementi (`<meta name="keywords" content="...">`), spam göndericilerin yüzlerce anahtar kelime doldurarak sonuçları manipüle etmesi nedeniyle artık arama motorları tarafından tamamen göz ardı edilmektedir.

### Diğer meta veri türleri

Web'de gezinirken başka metadata türleriyle de karşılaşırsınız. Web sitelerinde göreceğiniz özelliklerin çoğu, belirli platformlara (örneğin sosyal ağ sitelerine) kullanabilecekleri özel bilgiler sağlamak için tasarlanmış tescilli yapılardır.

Örneğin, **Open Graph Data (OGP)**, Facebook tarafından web siteleri için daha zengin metadata sağlamak amacıyla geliştirilmiş bir metadata protokolüdür. MDN Web Docs kaynak kodunda şunları bulabilirsiniz:

```html
<meta
  property="og:image"
  content="https://developer.mozilla.org/mdn-social-share.png" />
<meta
  property="og:description"
  content="The Mozilla Developer Network (MDN) provides
information about Open Web technologies including HTML, CSS, and APIs for both websites
and HTML Apps." />
<meta property="og:title" content="Mozilla Developer Network" />
```

Bu sayede Facebook veya diğer platformlarda MDN Web Docs bağlantısı paylaşıldığında, bağlantı bir görsel, başlık ve açıklama ile birlikte zengin bir kart görünümünde görüntülenir.

---

## Sitenize özel simgeler ekleme

Site tasarımınızı daha da zenginleştirmek için metadata'nıza özel simge referansları ekleyebilirsiniz; bunlar belirli bağlamlarda görüntülenir. Bunların en yaygın kullanılanı **favicon**'dur ("favorites icon" - favoriler simgesinin kısaltması; tarayıcılardaki "favoriler" veya "yer imleri" listelerinde kullanımına atıfta bulunur).

Favicon uzun yıllardır kullanılmaktadır. Bu türün ilk simgesidir: birden çok yerde kullanılan 16 piksellik kare bir simgedir. Açık olan her sayfayı içeren tarayıcı sekmesinde ve yer imleri panelinde yer imlerine eklenmiş sayfaların yanında gösterilir.

Bir favicon sayfaya şu şekilde eklenir:

1. `.ico`, `.gif` veya `.png` gibi desteklenen bir formatta web sitesi klasör yapınızın içine kaydedin.
2. HTML'inizin `<head>` bloğuna, favicon dosyasının yolunu referans veren bir `<link>` elementi ekleyin:

```html
<link rel="icon" href="/favicon.ico" type="image/x-icon" />
```

> [!NOTE]
> Bu örnekte favicon yolunun `/` ile başlaması, "dosyayı sitenizin en üst düzey (root / kök) dizininde ara" anlamına gelir. Modern tarayıcılar genellikle sitenin kök dizininde bulunan `favicon.ico` dosyasını otomatik olarak favicon kabul eder, bu nedenle birçok site `<link>` elementini yazma gereği bile duymaz. Ancak simgeyi başka bir konumda barındırmak istiyorsanız açık bir `<link>` elementi kullanışlıdır.

Farklı cihazlar ve bağlamlar için farklı simgeler de ekleyebilirsiniz:

```html
<!-- Yüksek çözünürlüklü Retina ekranlı iPad Pro için: -->
<link
  rel="apple-touch-icon"
  sizes="167x167"
  href="/apple-touch-icon-167x167.png" />
<!-- 3x çözünürlüklü iPhone için: -->
<link
  rel="apple-touch-icon"
  sizes="180x180"
  href="/apple-touch-icon-180x180.png" />
<!-- Retina olmayan iPad, iPad mini vb. için: -->
<link
  rel="apple-touch-icon"
  sizes="152x152"
  href="/apple-touch-icon-152x152.png" />
<!-- 2x çözünürlüklü iPhone ve diğer cihazlar için: -->
<link rel="apple-touch-icon" href="/apple-touch-icon-120x120.png" />
<!-- Temel favicon -->
<link rel="icon" href="/favicon.ico" />
```

---

## HTML'e CSS ve JavaScript uygulama

Modern çağda kullanacağınız hemen hemen tüm web siteleri, estetik bir görünüm için **CSS**'i; video oynatıcılar, haritalar ve oyunlar gibi etkileşimli işlevleri güçlendirmek içinse **JavaScript**'i kullanır. Bunlar bir web sayfasına çoğunlukla sırasıyla `<link>` ve `<script>` elementleri kullanılarak uygulanır.

* `<link>` elementi daima belgenizin head bölümüne yerleştirilmelidir. İki temel nitelik alır: belgenin stil sayfası olduğunu belirten `rel="stylesheet"` ve stil dosyasına giden yolu içeren `href`:

```html
<link rel="stylesheet" href="my-css-file.css" />
```

* `<script>` elementi de head içine yerleştirilebilir ve yüklemek istediğiniz JavaScript'in yolunu içeren bir `src` niteliği ile sayfa HTML'i ayrıştırmayı bitirdikten sonra JavaScript'i yüklemesini tarayıcıya bildiren bir boolean nitelik olan `defer` niteliğini içermelidir:

```html
<script src="my-js-file.js" defer></script>
```

`defer` niteliği, JavaScript henüz sayfada mevcut olmayan bir HTML elementine erişmeye çalışırken hata vermesin diye, JavaScript çalışmadan önce tüm HTML'in yüklenmesini garanti eder.

> [!NOTE]
> `<script>` elementi boş bir element (void element) gibi görünebilir, ancak **değildir**; bu yüzden mutlaka bir kapanış etiketine (`</script>`) ihtiyaç duyar. Harici bir betik dosyasına işaret etmek yerine betik kodunuzu doğrudan `<script>` etiketleri arasına da yazabilirsiniz.

---

## Belgenin birincil dilini ayarlama

Son olarak, sayfanızın dilini belirtebileceğinizi (ve kesinlikle belirtmeniz gerektiğini) belirtmek gerekir. Bu, açılış `<html>` etiketine `lang` niteliği eklenerek yapılır:

```html
<html lang="en-US">
  …
</html>
```

Bu ayar birçok açıdan yararlıdır:
1. Dil ayarlandığında HTML belgeniz arama motorları tarafından daha etkili indekslenir (örneğin dile özel sonuçlarda doğru görünür).
2. Ekran okuyucu kullanan görme engelli kişiler için faydalıdır (örneğin "six" kelimesi hem İngilizcede hem de Fransızcada vardır ancak tamamen farklı telaffuz edilir).

Belgenizin alt bölümlerinin farklı dillerde tanınmasını da sağlayabilirsiniz. Örneğin, Japonca bölümümüzün Japonca olarak tanınmasını şu şekilde sağlayabiliriz:

```html
<p>Japanese example: <span lang="ja">ご飯が熱い。</span>.</p>
```

Bu dil kodları **ISO 639-1** standardı tarafından tanımlanmıştır.

---

## Özet

Bu bölüm, HTML head konusundaki hızlı turumuzun sonunu işaret ediyor. Bir sonraki makalede HTML'de başlıklar ve paragraflara (**Headings and paragraphs**) bakacağız.

---

# 3. Başlıklar ve paragraflar

**HTML** > **Headings and paragraphs** | English (US)

HTML'in ana görevlerinden biri, bir tarayıcının bir HTML belgesini geliştiricisinin amaçladığı şekilde görüntüleyebilmesi için metne yapı kazandırmaktır. Bu makale, başlıkları ve paragrafları tanımlayarak temel sayfa yapısını sağlamak için HTML'in nasıl kullanılabileceğini açıklar.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | Basic HTML Syntax bölümünde ele alındığı gibi temel HTML aşinalığı. |
| **Learning outcomes (Öğrenim çıktıları):** | • Başlıklar ve bu başlıkların altındaki içeriklerle iyi bir belge yapısı oluşturma.<br>• Prezentasyonel (görsel) HTML yerine anlamsal (semantic) HTML kullanma ve bunun neden önemli olduğu.<br>• Başlık düzeylerinin mantıksal bir sırayla kullanılması gerekliliği (düzey atlamamak veya belirli bir yazı tipi boyutuna ulaşmak için gelişigüzel kullanmamak).<br>• SEO faydaları: örneğin anahtar kelimelerin başlıklarda daha fazla ağırlık kazanması.<br>• Erişilebilirlik faydaları: Ekran okuyucuların içerikte gezinmek için başlıkları işaret direkleri olarak kullanması. |

---

## Başlıklar ve paragraflar

Yapılandırılmış metinlerin çoğu; ister bir hikaye, gazete, ders kitabı veya dergi okuyor olun, başlıklardan ve paragraflardan oluşur. Yapılandırılmış içerik, okuma deneyimini kolaylaştırır ve daha keyifli hale getirir.

HTML'de her paragraf bir `<p>` elementi içine sarılmalıdır:

```html
<p>I am a paragraph, oh yes I am.</p>
```

Her başlık bir başlık elementi içine sarılmalıdır:

```html
<h1>I am the title of the story.</h1>
```

HTML'de altı başlık elementi bulunur: `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>` ve `<h6>`. Her element belgedeki farklı bir içerik düzeyini temsil eder: `<h1>` ana başlığı, `<h2>` alt başlıkları, `<h3>` alt-alt başlıkları temsil eder ve bu şekilde devam eder.

---

## Yapısal hiyerarşiyi uygulama

Örneğin bir hikayede `<h1>` hikayenin başlığını, `<h2>` her bölümün başlığını ve `<h3>` her bölümün alt kısımlarını temsil eder:

```html
<h1>The Crushing Bore</h1>

<p>By Chris Mills</p>

<h2>Chapter 1: The dark night</h2>

<p>
  It was a dark night. Somewhere, an owl hooted. The rain lashed down on the…
</p>

<h2>Chapter 2: The eternal silence</h2>

<p>Our protagonist could not so much as a whisper out of the shadowy figure…</p>

<h3>The specter speaks</h3>

<p>
  Several more hours had passed, when all of a sudden the specter sat bolt
  upright and exclaimed, "Please have mercy on my soul!"
</p>
```

Hiyerarşi mantıklı olduğu sürece ilgili elementlerin neyi temsil ettiği size bağlıdır. Bu tür yapıları oluştururken aklınızda bulundurmanız gereken birkaç en iyi uygulama şunlardır:

* **Tercihen sayfa başına tek bir `<h1>` kullanmalısınız** — bu en üst düzey başlıktır ve diğer tüm başlıklar hiyerarşide bunun altında yer alır.
* **Başlıkları hiyerarşide doğru sırada kullandığınızdan emin olun.** Alt başlıkları temsil etmek için `<h3>`, ardından alt-alt başlıkları temsil etmek için `<h2>` kullanmayın; bu anlamsızdır ve garip sonuçlara yol açar.
* **Kullanılabilir altı başlık düzeyinden, gerekli hissetmediğiniz sürece sayfa başına üçten fazlasını kullanmamayı hedeflemelisiniz.** Çok sayıda düzeye sahip belgeler hantal ve gezinmesi zor hale gelir.

---

## Neden yapıya ihtiyacımız var?

Bu soruyu yanıtlamak için biçimlendirilmemiş ham bir metni ele alalım. İçeriğe yapı kazandıracak hiçbir element olmadığında, tarayıcı neyin başlık neyin paragraf olduğunu bilemez ve tüm metni tek bir devasa blok olarak görüntüler.

Ayrıca:
* **Kullanıcılar** sayfayı hızla tarayarak ilgili içeriği bulma eğilimindedir; başlangıçta sadece başlıkları okurlar. Birkaç saniye içinde yararlı bir şey göremezlerse sayfayı terk ederler.
* Sayfanızı indeksleyen **arama motorları**, başlıkların içeriğini sayfanın arama sıralamasını etkileyen önemli anahtar kelimeler olarak değerlendirir. Başlıklar olmadan sayfanız SEO açısından zayıf kalır.
* **Ekran okuyucular**, başlıkları sesli okuyarak belgenin genel hatlarını sunar ve kullanıcıların ihtiyaç duydukları bilgiyi hızla bulmalarını sağlar. Başlıklar yoksa, kullanıcı tüm belgeyi baştan sona dinlemek zorunda kalır.
* İçeriği **CSS** ile stillendirmek veya **JavaScript** ile etkileşimli hale getirmek için, ilgili içeriği saran elementlere ihtiyacınız vardır.

Bu nedenle içeriğimize yapısal işaretleme (structural markup) kazandırmalıyız.

---

## İçeriğe yapı kazandırma alıştırması

Görev:
1. İçeriğin başındaki ana metni `<h1>` elementi içine sararak ana başlığa dönüştürün.
2. İki çift kelimeyi `<h2>` elementleri içine alarak ikinci düzey başlıklara dönüştürün.
3. Kalan cümleleri `<p>` elementleri içine alarak paragraflara dönüştürün. Her `<h2>` altına bir `<p>` gelmelidir.

```html
<h1>Favorite body parts</h1>

<h2>The brain</h2>

<p>Lovely shape and color. Also does thinkin' stuff.</p>

<h2>The feet</h2>

<p>Knobbly and ugly, but useful for getting about.</p>
```

---

## Neden anlambilime (semantiğe) ihtiyacımız var?

Çevremizdeki her yerde semantiğe (anlambilime) güveniriz. Örneğin kırmızı bir trafik ışığının "dur", yeşil bir trafik ışığının "geç" anlamına geldiğini biliriz. Yanlış semantik uygulandığında işler çok hızlı bir şekilde karışır.

Benzer şekilde, doğru elementleri kullandığımızdan, içeriğimize doğru anlamı, işlevi veya görünümü kazandırdığımızdan emin olmalıyız. `<h1>` elementi, sardığı metne "sayfanızdaki en üst düzey başlık" rolünü (veya anlamını) veren anlamsal bir elementtir:

```html
<h1>This is a top level heading</h1>
```

Varsayılan olarak tarayıcı başlık gibi görünmesi için ona büyük bir yazı tipi boyutu verir. Daha da önemlisi, anlamsal değeri arama motorları ve ekran okuyucular tarafından kullanılır.

Buna karşılık, herhangi bir elementi CSS ile en üst düzey başlık gibi *gösterebilirsiniz*:

```html
<span style="font-size: 32px; margin: 21px 0; display: block;">
  Is this a top level heading?
</span>
```

Bu bir `<span>` elementidir. Hiçbir anlamsal değeri yoktur. Ekstra bir anlam yüklemeden sadece CSS uygulamak için kullanılır. Başlık gibi görünse bile hiçbir anlamsal fayda sağlamaz. Bu nedenle her iş için ilgili HTML elementini kullanmak en doğrusudur.

---

## Özet

Bu bölümle birlikte HTML başlıkları ve paragrafları incelememizi tamamladık. Sırada kelimelere vurgu kazandırma (**Emphasis and importance**) konusu var.

---

# 4. Vurgu ve önem derecesi

**HTML** > **Emphasis and importance** | English (US)

Önceki makalede HTML'de semantiğin neden önemli olduğuna baktık ve başlıklara ile paragraflara odaklandık. Bu makale, metne vurgu ve önem kazandıran HTML elementlerini inceleyerek semantik temasını sürdürmektedir.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | Basic HTML Syntax bölümünde ele alındığı gibi temel HTML aşinalığı. |
| **Learning outcomes (Öğrenim çıktıları):** | • Vurgu (emphasis) ve önemin (importance) anlamı; bunları HTML'de uygulayan `<em>` ve `<strong>` gibi temel elementler.<br>• Artık kesinlikle kullanılmaması gereken prezentasyonel işaretlemeler (`<big>` ve `<font>` gibi kullanım dışı / deprecated etiketler).<br>• Yeni anlamsal anlamlar verilerek yeniden tanımlanmış prezentasyonel işaretlemeler (`<i>` ve `<b>`). |

---

## Vurgu ve önem nedir?

İnsan dilinde, bir cümlenin anlamını değiştirmek için genellikle belirli kelimeleri vurgularız ve belirli kelimeleri önemli veya farklı olarak işaretlemek isteriz. HTML, metinsel içeriği bu tür etkilerle işaretlememizi sağlayan çeşitli semantik elementler sunar.

### Vurgu

Konuşma dilinde vurgu eklemek istediğimizde belirli kelimeleri baskılı söyleriz ve söylediğimiz şeyin anlamını incelikle değiştiririz. Benzer şekilde, yazı dilinde kelimeleri italik yaparak vurgulama eğilimindeyizdir. Örneğin, aşağıdaki iki cümle farklı anlamlara sahiptir:

> I am glad you weren't late. (Geç kalmadığına sevindim.)
>
> I am *glad* you weren't *late*. (*Geç* kalmadığına *sevindim*.)

İlk cümle, kişinin geç kalmadığına gerçekten rahatlamış görünmektedir. Buna karşılık, hem "glad" hem de "late" kelimelerinin italik olduğu ikincisi, alaycı veya pasif-agresif bir ton taşır; kişinin biraz geç gelmesine duyulan rahatsızlığı ifade eder.

HTML'de bu tür durumları işaretlemek için `<em>` (emphasis) elementini kullanırız. Belgeyi okumayı daha ilginç kılmanın yanı sıra, bunlar ekran okuyucular tarafından tanınır ve farklı bir ses tonuyla seslendirilebilir. Tarayıcılar bunu varsayılan olarak italik biçimlendirir, ancak bu etiketi yalnızca italik stil elde etmek için kullanmamalısınız.

```html
<p>I am <em>glad</em> you weren't <em>late</em>.</p>
```

### Güçlü önem

Önemli kelimeleri vurgulamak için, konuşma dilinde onları baskılı söyler, yazı dilinde ise **kalın (bold)** yaparız. Örneğin:

> This liquid is **highly toxic**. (Bu sıvı **son derece zehirlidir**.)
>
> I am counting on you. **Do not** be late! (Sana güveniyorum. **Sakın** geç kalma!)

HTML'de bu tür durumları işaretlemek için `<strong>` (strong importance) elementini kullanırız. Bunlar da ekran okuyucular tarafından tanınır. Tarayıcılar bunu varsayılan olarak kalın metin şeklinde biçimlendirir. Yalnızca kalın stil elde etmek için bu etiketi kullanmamalısınız.

```html
<p>This liquid is <strong>highly toxic</strong>.</p>

<p>I am counting on you. <strong>Do not</strong> be late!</p>
```

İstenirse `<strong>` ve `<em>` birbirinin içine yerleştirilebilir:

```html
<p>This liquid is <strong>highly toxic</strong> — if you drink it, <strong>you may <em>die</em></strong>.</p>
```

---

## Vurgu ve önem alıştırması

Görev:
1. Ana başlıkta "Emphasis" kelimesine vurgu (`<em>`), "importance" kelimesine ise güçlü önem (`<strong>`) verin.
2. İlk paragrafta kahve makinesi adına güçlü önem verin ve kahveyi tanımlamak için kullanılan sıfatları vurgulayın.
3. İkinci paragrafta sıcaklık açıklamasına ("cold") ve yapılması gereken eyleme ("wrap up warm to avoid falling ill") güçlü önem verin. "falling ill" ifadesine ekstra işaretleme ekleyerek hem vurgulu hem de önemli olmasını sağlayın.

Çözüm:

```html
<h1><em>Emphasis</em> and <strong>importance</strong></h1>

<p>
  My new coffee machine is called <strong>The Percolator 2000</strong>. It
  produces the most <em>sublime</em> and <em>wonderful</em> brew.
</p>

<p>
  In the dead of winter, it will be <strong>cold</strong>. You should
  <strong>wrap up warm to avoid <em>falling ill</em></strong>.
</p>
```

---

## İtalik, kalın, altı çizili…

Şimdiye kadar tartıştığımız elementler net anlamsal karşılıklara sahiptir. `<b>`, `<i>` ve `<u>` etiketlerinin durumu ise biraz daha karmaşıktır. Bunlar, CSS'in henüz desteklenmediği veya zayıf desteklendiği bir dönemde insanların kalın, italik veya altı çizili metin yazabilmeleri için ortaya çıkmıştı. Yalnızca sunumu etkileyen ve semantiği etkilemeyen bu tür elementler **prezentasyonel elementler** olarak bilinir ve artık kullanılmamalıdır.

HTML5; `<b>`, `<i>` ve `<u>` etiketlerini yeni, biraz kafa karıştırıcı anlamsal rollerle yeniden tanımladı:

* `<i>`: Geleneksel olarak italik ile aktarılan anlamları iletmek için kullanılır: yabancı kelimeler, taksonomik adlandırmalar, teknik terimler, bir düşünce...
* `<b>`: Geleneksel olarak kalın ile aktarılan anlamları iletmek için kullanılır: anahtar kelimeler, ürün adları, giriş cümlesi...
* `<u>`: Geleneksel olarak altı çizili ile aktarılan anlamları iletmek için kullanılır: özel isim, yazım hatası...

> [!NOTE]
> İnsanlar altı çizili metni güçlü bir şekilde köprülerle (linklerle) ilişkilendirir. Bu nedenle web üzerinde yalnızca bağlantıların altını çizmek en iyi uygulamadır. `<u>` elementini yalnızca anlamsal olarak uygun olduğunda kullanın ve gerekirse alt çizgiyi CSS ile farklılaştırın.

Örnekler:

```html
<!-- Bilimsel adlar -->
<p>
  The Ruby-throated Hummingbird (<i>Archilochus colubris</i>) is the most common
  hummingbird in Eastern North America.
</p>

<!-- Yabancı kelimeler -->
<p>
  The menu was a sea of exotic words like <i lang="uk-latn">vatrushka</i>,
  <i lang="id">nasi goreng</i> and <i lang="fr">soupe à l'oignon</i>.
</p>

<!-- Bilinen bir yazım hatası -->
<p>Someday I'll learn how to <u class="spelling-error">spel</u> better.</p>

<!-- Bir tanım içinde tanımlanan terim -->
<dl>
  <dt>Semantic HTML</dt>
  <dd>
    Use the elements based on their <b>semantic</b> meaning, not their
    appearance.
  </dd>
</dl>
```

---

## Özet

Vurgu ve önem konusunu tamamladık. Sırada HTML'de listelerin nasıl temsil edildiğini inceleyeceğimiz **Lists** makalesi var.

---

# 5. Listeler

**HTML** > **Lists** | English (US)

Şimdi dikkatimizi listelere çevirelim. Listeler hayatın her yerindedir — alışveriş listenizden her gün evinize gitmek için bilinçaltınızda takip ettiğiniz yol tariflerine, bu eğitimlerde izlediğiniz talimat listelerine kadar! HTML'in farklı liste türlerini tanımlamamıza olanak tanıyan kullanışlı bir element kümesine sahip olması şaşırtıcı değildir. Web üzerinde üç tür liste bulunur: sırasız (unordered), sıralı (ordered) ve açıklama (description) listeleri.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | Basic HTML Syntax bölümünde ele alındığı gibi temel HTML aşinalığı. |
| **Learning outcomes (Öğrenim çıktıları):** | • Üç liste türü (sırasız, sıralı ve açıklama) için HTML yapısı.<br>• Her liste türü için doğru kullanım senaryoları.<br>• Gezinti menüleri (navigation menus) gibi listelerin daha geniş kullanım alanları. |

---

## Sırasız listeler

Sırasız listeler, öğelerin sırasının önemli olmadığı durumları işaretlemek için kullanılır. Alışveriş listesini ele alalım:

```plain
milk
eggs
bread
hummus
```

Bu örnekte öğelerin sırası fark etmez. HTML'de bu listeyi oluşturmak için önce listenin tamamını bir `<ul>` (unordered list) elementi içine sararız. Ardından her öğeyi bir `<li>` (list item) elementi içine sararız:

```html
<ul>
  <li>milk</li>
  <li>eggs</li>
  <li>bread</li>
  <li>hummus</li>
</ul>
```

---

## Sıralı listeler

Sıralı listeler, öğelerin sırasının *önemli olduğu* listelerdir. Bir yol tarifini ele alalım:

```plain
Drive to the end of the road
Turn right
Go straight across the first two roundabouts
Turn left at the third roundabout
The school is on your right, 300 meters up the road
```

İşaretleme yapısı, liste öğelerini `<ul>` yerine bir `<ol>` (ordered list) elementi içine sarmanız dışında sırasız listelerle tamamen aynıdır:

```html
<ol>
  <li>Drive to the end of the road</li>
  <li>Turn right</li>
  <li>Go straight across the first two roundabouts</li>
  <li>Turn left at the third roundabout</li>
  <li>The school is on your right, 300 meters up the road</li>
</ol>
```

---

## Tarif sayfamızı işaretleme

Hummus tarifi içeriğini doğru yapısal elementlerle işaretleyelim:

```html
<h1>Quick hummus recipe</h1>

<p>This recipe makes quick, tasty hummus, with no messing. It has been adapted from a number of different recipes that I have read over the years.</p>

<p>Hummus is a delicious thick paste used heavily in Greek and Middle Eastern dishes. It is very tasty with salad, grilled meats and pitta breads.</p>

<h2>Ingredients</h2>

<ul>
  <li>1 can (400g) of chick peas (garbanzo beans)</li>
  <li>175g of tahini</li>
  <li>6 sundried tomatoes</li>
  <li>Half a red pepper</li>
  <li>A pinch of cayenne pepper</li>
  <li>1 clove of garlic</li>
  <li>A dash of olive oil</li>
</ul>

<h2>Instructions</h2>

<ol>
  <li>Remove the skin from the garlic, and chop coarsely</li>
  <li>Remove all the seeds and stalk from the pepper, and chop coarsely</li>
  <li>Add all the ingredients into a food processor</li>
  <li>Process all the ingredients into a paste</li>
  <li>If you want a coarse "chunky" hummus, process it for a short time</li>
  <li>If you want a smooth hummus, process it for a longer time</li>
</ol>

<p>For a different flavor, you could try blending in a small measure of lemon and coriander, chili pepper, lime and chipotle, harissa and mint, or spinach and feta cheese. Experiment and see what works for you.</p>

<h2>Storage</h2>

<p>Refrigerate the finished hummus in a sealed container. You should be able to use it for about a week after you've made it. If it starts to become fizzy, you should definitely discard it.</p>

<p>Hummus is suitable for freezing; you should thaw it and use it within a couple of months.</p>
```

---

## Listeleri iç içe yerleştirme

Bir listeyi diğerinin içine yerleştirmek (nesting) tamamen geçerlidir. Örneğin, tarifimizin son iki maddesi bir önceki maddeyle yakından ilişkili seçenekler olduğundan, bunları dördüncü maddenin içine sırasız bir alt liste olarak yerleştirebiliriz:

```html
<ol>
  <li>Remove the skin from the garlic, and chop coarsely.</li>
  <li>Remove all the seeds and stalk from the pepper, and chop coarsely.</li>
  <li>Add all the ingredients into a food processor.</li>
  <li>
    Process all the ingredients into a paste.
    <ul>
      <li>
        If you want a coarse "chunky" hummus, process it for a short time.
      </li>
      <li>If you want a smooth hummus, process it for a longer time.</li>
    </ul>
  </li>
</ol>
```

---

## Açıklama listeleri

Açıklama listelerinin amacı, terimler ve tanımlar veya sorular ve yanıtlar gibi bir dizi öğeyi ve bunlarla ilişkili açıklamaları işaretlemektir. Bir dizi terim ve tanım örneğine bakalım:

```plain
soliloquy
In drama, where a character speaks to themselves...
monologue
In drama, where a character speaks their thoughts out loud...
aside
In drama, where a character shares a comment only with the audience...
```

Açıklama listeleri diğer liste türlerinden farklı bir kapsayıcı kullanır: `<dl>` (description list). Ayrıca her terim bir `<dt>` (description term) elementi içine sarılır ve her tanım/açıklama bir `<dd>` (description definition) elementi içine sarılır:

```html
<dl>
  <dt>soliloquy</dt>
  <dd>
    In drama, where a character speaks to themselves, representing their inner
    thoughts or feelings and in the process relaying them to the audience (but
    not to other characters.)
  </dd>
  <dt>monologue</dt>
  <dd>
    In drama, where a character speaks their thoughts out loud to share them
    with the audience and any other characters present.
  </dd>
  <dt>aside</dt>
  <dd>
    In drama, where a character shares a comment only with the audience for
    humorous or dramatic effect. This is usually a feeling, thought, or piece of
    additional background information.
  </dd>
</dl>
```

Tarayıcı varsayılan stilleri, açıklamaları terimlerden biraz daha içeriden (girintili olarak) görüntüler.

### Tek bir terim için birden fazla açıklama

Tek bir terimin birden fazla açıklamaya sahip olmasına izin verilir:

```html
<dl>
  <dt>aside</dt>
  <dd>
    In drama, where a character shares a comment only with the audience for
    humorous or dramatic effect. This is usually a feeling, thought, or piece of
    additional background information.
  </dd>
  <dd>
    In writing, a section of content that is related to the current topic, but
    doesn't fit directly into the main flow of content so is presented nearby
    (often in a box off to the side.)
  </dd>
</dl>
```

### Tanımlar kümesini işaretleme alıştırması

Görev:
Üç terimi ve dört açıklamayı işaretleyin. Üçüncü terimin iki açıklaması olduğunu unutmayın.

Çözüm:

```html
<dl>
  <dt>Love</dt>
  <dd>The glue that binds the world together.</dd>
  <dt>Eggs</dt>
  <dd>The glue that binds the cake together.</dd>
  <dt>Coffee</dt>
  <dd>The drink that gets the world running in the morning.</dd>
  <dd>A light brown color.</dd>
</dl>
```

---

## Özet

Listeler konusunu bitirdik. Bir sonraki bölümde, HTML metin temelleri konusunda öğrendiklerinizi pekiştirmek için hazırlanmış sınavı (**Test: HTML text basics**) ele alacağız.

---
# 6. Test: HTML metin temelleri

**HTML** > **Test your skills: HTML text basics** | English (US)

Bu beceri testinin amacı, metne yapı ve anlam kazandırmak için HTML'de metni nasıl işaretleyeceğinizi anlayıp anlamadığınızı değerlendirmenize yardımcı olmaktır.

> [!NOTE]
> Yardıma ihtiyaç duyarsanız MDN topluluk kanallarından veya ilgili konu rehberlerinden yararlanabilirsiniz.

---

## Metin temelleri 1

Bu görevde, sağlanan HTML metnini anlamsal başlık ve paragraf elementlerini kullanarak işaretlemenizi istiyoruz.

### Başlangıç Kodu:

```html
Basic HTML Animals

This is the first paragraph in our page. It introduces our animals.

The Llama

Our Llama is a big fan of list items. When she spies a patch of them on a web page, she will eat them like sweets, licking her lips as she goes.

The Anaconda

The crafty anaconda likes to slither around the page, traveling rapidly by way of anchors to sneak up on his prey.
```

### Görev Talimatı:
1. En üstteki metni `<h1>` ana başlığı yapın.
2. Açıklama metinlerini `<p>` paragraflarına sarın.
3. Hayvan adlarını (`The Llama`, `The Anaconda`) `<h2>` alt başlıklarına sarın.

### Çözüm:

```html
<h1>Basic HTML Animals</h1>

<p>This is the first paragraph in our page. It introduces our animals.</p>

<h2>The Llama</h2>

<p>
  Our Llama is a big fan of list items. When she spies a patch of them on a web
  page, she will eat them like sweets, licking her lips as she goes.
</p>

<h2>The Anaconda</h2>

<p>
  The crafty anaconda likes to slither around the page, traveling rapidly by way
  of anchors to sneak up on his prey.
</p>
```

---

## Metin temelleri 2

Bu görevde, ilk işaretlenmemiş listeyi sırasız bir listeye (`<ul>`), ikinci listeyi ise sıralı bir listeye (`<ol>`) dönüştürmenizi istiyoruz.

### Başlangıç Kodu:

```html
<h1>Looking at lists</h1>

<p>Turn the following list of my favorite vegetables into an unordered list.</p>

Cucumber
Broccoli
Asparagus
Pepper

<p>Turn the following directions into an ordered list.</p>

First knock on the door
When prompted, say the magic word
Wait for at least 5 seconds
Turn the handle and push
```

### Çözüm:

```html
<h1>Looking at lists</h1>

<p>Turn the following list of my favorite vegetables into an unordered list.</p>

<ul>
  <li>Cucumber</li>
  <li>Broccoli</li>
  <li>Asparagus</li>
  <li>Pepper</li>
</ul>

<p>Turn the following directions into an ordered list.</p>

<ol>
  <li>First knock on the door</li>
  <li>When prompted, say the magic word</li>
  <li>Wait for at least 5 seconds</li>
  <li>Turn the handle and push</li>
</ol>
```

---

## Metin temelleri 3

Bu görevde, sağlanan hayvanları ve tanımlarını bir açıklama listesine (`<dl>`) dönüştürmenizi istiyoruz.

### Başlangıç Kodu:

```html
<h1>Advanced HTML Animals</h1>

Llama
Tall, woolly quadruped, pointy ears. Sometimes rideable, but grumpy and spits a lot. Big fan of list items.
Anaconda
A very large constrictor snake; travels rapidly by way of anchors to sneak up on his prey.
Hippopotamus
His description is bottomless.
```

### Çözüm:

```html
<h1>Advanced HTML Animals</h1>

<dl>
  <dt>Llama</dt>
  <dd>
    Tall, woolly quadruped, pointy ears. Sometimes rideable, but grumpy and
    spits a lot. Big fan of list items.
  </dd>
  <dt>Anaconda</dt>
  <dd>
    A very large constrictor snake; travels rapidly by way of anchors to sneak
    up on his prey.
  </dd>
  <dt>Hippopotamus</dt>
  <dd>His description is bottomless.</dd>
</dl>
```

---

## Metin temelleri 4

Bu görevde size bir paragraf verilmiştir; amacınız uygun sözcüklerden birkaçını güçlü önemle (`<strong>`), birkaçını ise vurguyla (`<em>`) işaretlemek için satır içi (inline) elementleri kullanmaktır.

### Başlangıç Kodu:

```html
<h1>Emphasis and importance</h1>

<p>
  There are two things I care about — music and friends. Someday I might be able
  to get my friends interested in each other, and my music!
</p>
```

### Çözüm:

```html
<h1>Emphasis and importance</h1>

<p>
  There are <strong>two</strong> things I care about —
  <strong>music</strong> and <strong>friends</strong>. Someday I
  <em>might</em> be able to get my friends interested in each other,
  <em>and</em> my music!
</p>
```

---

# 7. İleri düzey metin özellikleri

**HTML** > **Advanced text features** | English (US)

HTML'de, Emphasis and importance makalesinde değinmediğimiz metin semantiğini tanımlayan başka birçok element bulunmaktadır. Bu makalede açıklanan elementler daha az bilinir, ancak yine de bilinmeleri oldukça faydalıdır. Burada alıntıları, bilgisayar kodunu ve diğer ilgili metinleri, alt simge ve üst simgeleri, iletişim bilgilerini ve daha fazlasını işaretlemeyi öğreneceksiniz.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | Basic HTML Syntax bölümünde ele alındığı gibi temel HTML aşinalığı. Başlıklar, paragraflar ve listeler gibi metin düzeyi anlambilim. |
| **Learning outcomes (Öğrenim çıktıları):** | • Alıntılar (Quotations).<br>• Kısaltmalar ve akronimler (Abbreviations and acronyms).<br>• Adresler ve iletişim bilgileri (Addresses).<br>• Saatler ve tarihler (Times and dates).<br>• Üst simge ve alt simge (Superscript and subscript). |

---

## Alıntılar

HTML, alıntıları işaretlemek için kullanışlı özellikler barındırır; hangi elementi kullanacağınız, bir blok alıntısı mı yoksa satır içi bir alıntı mı işaretlediğinize bağlıdır.

### Blok alıntıları

Blok düzeyindeki bir içerik bölümü (bir paragraf, birden çok paragraf, bir liste vb.) başka bir kaynaktan alıntılanmışsa, bunu belirtmek için içeriği bir `<blockquote>` elementi içine sarmalı ve alıntının kaynağını gösteren bir URL'yi `cite` niteliği içine dahil etmelisiniz:

```html
<p>Here is a blockquote:</p>
<blockquote
  cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/blockquote">
  <p>
    The <strong>HTML <code>&lt;blockquote&gt;</code> Element</strong> (or
    <em>HTML Block Quotation Element</em>) indicates that the enclosed text is
    an extended quotation.
  </p>
</blockquote>
```

Tarayıcı varsayılan stili, bunun bir alıntı olduğunu belirtmek amacıyla bu içeriği girintili bir paragraf olarak işleyecektir.

### Satır içi alıntılar

Satır içi alıntılar, `<q>` elementini kullanmaları dışında tamamen aynı şekilde çalışır:

```html
<p>
  The quote element — <code>&lt;q&gt;</code> — is
  <q
    cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/q">
    intended for short quotations that don't require paragraph breaks.
  </q>
</p>
```

Tarayıcı varsayılan stili, alıntıyı belirtmek için metni normal tırnak işaretleri içine alarak işler:
"intended for short quotations that don't require paragraph breaks."

### Kaynak gösterme: `<cite>`

`cite` niteliğinin içeriği faydalı gibi görünse de, ne yazık ki tarayıcılar ve ekran okuyucular bu nitelikle pek bir şey yapmaz. JavaScript veya CSS kullanarak kendi çözümünüzü yazmadığınız sürece, tarayıcının `cite` içeriğini doğrudan görüntülemesini sağlamanın bir yolu yoktur. Alıntının kaynağını sayfada görünür kılmak istiyorsanız, bunu bir bağlantı veya başka bir uygun yolla doğrudan metin içinde sunmanız gerekir.

Bir de alıntılanan kaynağın başlığını (örneğin kitabın adını) barındırması amaçlanan `<cite>` elementi mevcuttur. `<cite>` içindeki metni alıntı kaynağına bağlamak son derece yaygındır:

```html
<p>
  According to the
  <a href="/en-US/docs/Web/HTML/Reference/Elements/blockquote">
    <cite>MDN blockquote page</cite></a>:
</p>

<blockquote
  cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/blockquote">
  <p>
    The <strong>HTML <code>&lt;blockquote&gt;</code> Element</strong> (or
    <em>HTML Block Quotation Element</em>) indicates that the enclosed text is
    an extended quotation.
  </p>
</blockquote>

<p>
  The quote element — <code>&lt;q&gt;</code> — is
  <q cite="https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/q">
    intended for short quotations that don't require paragraph breaks.
  </q>
  — <a href="/en-US/docs/Web/HTML/Reference/Elements/q"><cite>MDN q page</cite></a>.
</p>
```

Kaynak gösterimleri (citations) varsayılan olarak italik yazı tipiyle stillendirilir.

### Bunu kim söyledi? Alıntı alıştırması

Görev:
1. Ortadaki paragrafı bir `cite` niteliği içeren bir `<blockquote>` haline getirin.
2. Üçüncü paragraftaki "The Need To Eliminate Negative Self Talk" ifadesini satır içi bir alıntıya (`<q>`) dönüştürün ve bir `cite` niteliği ekleyin.
3. Her kaynağın başlığını `<cite>` etiketleri içine sarın ve her birini ilgili kaynağa giden bir bağlantıya dönüştürün.

Çözüm:

```html
<p>
  Hello and welcome to my motivation page. As
  <a href="http://www.brainyquote.com/quotes/authors/c/confucius.html"
    ><cite>Confucius' quotes site</cite></a
  >
  says:
</p>

<blockquote cite="http://www.brainyquote.com/quotes/authors/c/confucius.html">
  <p>It does not matter how slowly you go as long as you do not stop.</p>
</blockquote>

<p>
  I also love the concept of positive thinking, and
  <q cite="http://example.com/affirmationsforpositivethinking"
    >The Need To Eliminate Negative Self Talk</q
  >
  (as mentioned in
  <a href="http://example.com/affirmationsforpositivethinking"
    ><cite>Affirmations for Positive Thinking</cite></a
  >.)
</p>
```

---

## Kısaltmalar: `<abbr>`

Web'de gezinirken karşılaşacağınız bir diğer oldukça yaygın element `<abbr>` elementidir — bu element bir kısaltmayı veya akronimi sarmak için kullanılır. İlk kullanımda terimin tam açılımını düz metin olarak sunmalı ve kısaltmayı işaretlemek için `<abbr>` kullanmalısınız.

Açılımı kısaltmanın yanına eklemek anlamlı değilse ve kısaltma oldukça yaygın bir terimse, terimin tam açılımını `title` niteliğinin değeri olarak sağlayabilirsiniz:

```html
<p>
  We use <abbr>HTML</abbr>, Hypertext Markup Language, to structure our web
  documents.
</p>

<p>
  I think <abbr title="Reverend">Rev.</abbr> Green did it in the kitchen with
  the chainsaw.
</p>
```

> **Note:** HTML'in önceki sürümlerinde `<acronym>` elementi de destekleniyordu, ancak hem kısaltmaları hem de akronimleri temsil etmek üzere `<abbr>` lehine HTML şartnamesinden çıkarılmıştır. `<acronym>` kesinlikle kullanılmamalıdır.

### Kısaltma İşaretleme Alıştırması:

```html
<p>
  <abbr>NASA</abbr> (the National Aeronautics and Space Administration) sure
  does some exciting work.
</p>

<p>The new user interface design <abbr title="Looks good to me">LGTM</abbr>!</p>
```

---

## İletişim bilgilerini işaretleme: `<address>`

HTML, iletişim bilgilerini işaretlemek için `<address>` elementine sahiptir:

```html
<address>Chris Mills, Manchester, The Grim North, UK</address>
```

Daha karmaşık işaretlemeler ve telefon/e-posta gibi diğer iletişim biçimlerini de içerebilir:

```html
<address>
  <p>
    Chris Mills<br />
    Manchester<br />
    The Grim North<br />
    UK
  </p>

  <ul>
    <li>Tel: 01234 567 890</li>
    <li>Email: me@grim-north.co.uk</li>
  </ul>
</address>
```

> **Note:** `<address>` elementi yalnızca en yakın `<article>` veya `<body>` elementinin barındırdığı belgenin iletişim bilgilerini sağlamak için kullanılmalıdır. Tüm sitenin iletişim bilgilerini eklemek için bir sitenin altbilgisinde (footer) veya yazarın iletişim bilgileri için bir makalenin içinde kullanılması doğrudur; ancak o sayfanın içeriğiyle ilgisi olmayan rastgele posta adresleri listesini işaretlemek için **kullanılmamalıdır**.

---

## Üst simge ve alt simge: `<sup>` ve `<sub>`

Tarihler, kimyasal formüller ve matematiksel denklemler gibi öğeleri işaretlerken üst simge ve alt simge kullanmanız gerekir. `<sup>` ve `<sub>` elementleri bu görevi yerine getirir:

```html
<p>My birthday is on the 25<sup>th</sup> of May 2001.</p>
<p>
  Caffeine's chemical formula is
  C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>.
</p>
<p>If x<sup>2</sup> is 9, x must equal 3 or -3.</p>
```

Tarayıcı çıktısı:
* My birthday is on the 25<sup>th</sup> of May 2001.
* Caffeine's chemical formula is C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>.
* If x<sup>2</sup> is 9, x must equal 3 or -3.

---

## Bilgisayar kodunu temsil etme

HTML kullanarak bilgisayar kodunu işaretlemek için kullanılabilecek bir dizi element mevcuttur:

* `<code>`: Genel bilgisayar kodu parçalarını işaretlemek için kullanılır.
* `<pre>`: Boşlukları ve girintileri korumak için kullanılır (genellikle kod blokları için). Metninizi `<pre></pre>` etiketleriyle sararsanız, boşluklarınız metin düzenleyicinizde gördüğünüz şekliyle birebir ekrana yansıtılır.
* `<var>`: Değişken adlarını özel olarak işaretlemek için kullanılır.
* `<kbd>`: Bilgisayara girilen klavye (ve diğer türdeki) girdileri işaretlemek için kullanılır.
* `<samp>`: Bir bilgisayar programının çıktısını işaretlemek için kullanılır.

Örnek kullanım:

```html
<pre><code>const para = document.querySelector('p');

para.onclick = function() {
  alert('Owww, stop poking me!');
}</code></pre>

<p>
  You shouldn't use presentational elements like <code>&lt;font&gt;</code> and
  <code>&lt;center&gt;</code>.
</p>

<p>
  In the above JavaScript example, <var>para</var> represents a paragraph
  element.
</p>

<p>Select all the text with <kbd>Ctrl</kbd>/<kbd>Cmd</kbd> + <kbd>A</kbd>.</p>

<pre>$ <kbd>ping mozilla.org</kbd>
<samp>PING mozilla.org (63.245.215.20): 56 data bytes
64 bytes from 63.245.215.20: icmp_seq=0 ttl=40 time=158.233 ms</samp></pre>
```

---

## Saatleri ve tarihleri işaretleme: `<time>`

HTML, saatleri ve tarihleri makine tarafından okunabilir bir formatta işaretlemek için `<time>` elementini sağlar:

```html
<time datetime="2016-01-20">20 January 2016</time>
```

İnsanlar tarihleri 20 January 2016, 20/01/16, 2016 年 1 月 20 日 gibi onlarca farklı şekilde yazabilir. Bilgisayarlar bu farklı biçimleri kolayca ayrıştıramaz. `<time>` elementi, `datetime` niteliği aracılığıyla net, standart ve makine tarafından okunabilir bir tarih/saat bağlamanıza olanak tanır.

Farklı biçim seçenekleri:

```html
<!-- Standart basit tarih -->
<time datetime="2016-01-20">20 January 2016</time>
<!-- Yalnızca yıl ve ay -->
<time datetime="2016-01">January 2016</time>
<!-- Yalnızca ay ve gün -->
<time datetime="01-20">20 January</time>
<!-- Yalnızca saat ve dakika -->
<time datetime="19:30">19:30</time>
<!-- Saniye ve milisaniye -->
<time datetime="19:30:01.856">19:30:01.856</time>
<!-- Tarih ve saat -->
<time datetime="2016-01-20T19:30">7.30pm, 20 January 2016</time>
<!-- Saat dilimi farkı (timezone offset) ile tarih ve saat -->
<time datetime="2016-01-20T19:30+01:00">
  7.30pm, 20 January 2016 is 8.30pm in France
</time>
<!-- Belirli bir hafta numarası -->
<time datetime="2016-W04">The fourth week of 2016</time>
```

---

## Özet

Daha az yaygın HTML metin anlambilimi incelememizin sonuna geldik. Sırada bu özellikleri pekiştirecek test makalesi (**Test: Advanced HTML text**) bulunmaktadır.

---

# 8. Test: İleri düzey HTML metinleri

**HTML** > **Test your skills: Advanced HTML text** | English (US)

Bu beceri testinin amacı, gelişmiş anlamsal özellikleri işaretlemek için daha az bilinen HTML elementlerini nasıl kullanacağınızı anlayıp anlamadığınızı değerlendirmenize yardımcı olmaktır.

---

## İleri düzey metin 1

Bu görevde, sağlanan HTML koduna anlamsal zenginlik katmanız gerekmektedir:

1. İkinci paragrafı blok düzeyinde bir alıntıya (`<blockquote>`) dönüştürün ve anlamsal olarak alıntının kaynağını belirtin.
2. "HTML" ve "CSS" ifadelerini ipucu (tooltip) içeren kısaltmalar (`<abbr>`) olarak işaretleyin.
3. Kimyasal formüller ve tarihler için alt simge (`<sub>`) ve üst simge (`<sup>`) kullanarak doğru anlamsal gösterimi sağlayın.
4. Metindeki tarihlerle makine tarafından okunabilir tarihleri anlamsal olarak ilişkilendirin (`<time>`).

### Başlangıç Kodu:

```html
<h1>Advanced text semantics</h1>

<p>Let's start with a quote:</p>

<p>
  HTML, Hypertext Markup Language is by default accessible, if used correctly.
</p>

<p>CSS can also be used to make web pages more, or less, accessible.</p>

<p>Chemical Formulae: H2O (Water), C2H6O (Ethanol).</p>

<p>
  Dates: December 25th 2019 (Christmas Day), November 2nd 2019 (Día de los
  Muertos).
</p>
```

### Çözüm:

```html
<h1>Advanced text semantics</h1>

<p>Let's start with a quote:</p>

<blockquote cite="https://developer.mozilla.org/en-US/docs/Learn/Accessibility">
  <p>
    <abbr title="HyperText Markup Language">HTML</abbr>, Hypertext Markup
    Language is by default accessible, if used correctly.
  </p>
</blockquote>

<p>
  <abbr title="Cascading Style Sheets">CSS</abbr>, Cascading Style Sheets, can
  also be used to make web pages more, or less, accessible.
</p>

<p>
  Chemical Formulae: H<sub>2</sub>O (Water), C<sub>2</sub>H<sub>6</sub>O
  (Ethanol).
</p>

<p>
  Dates:
  <time datetime="2019-12-25">December 25<sup>th</sup> 2019</time>
  (Christmas Day),
  <time datetime="2019-11-02">November 2<sup>nd</sup> 2019</time> (Día de los
  Muertos).
</p>
```

---

# 9. Uygulama Görevi: Mektup işaretleme

**HTML** > **Challenge: Marking up a letter** | English (US)

Hepimiz er ya da geç bir mektup yazmayı öğreniriz; bu, metin biçimlendirme becerilerimizi test etmek için de son derece yararlı bir örnektir. Bu meydan okumada, HTML metin biçimlendirme becerileriniz ve HTML `<head>` içeriği bilginiz için bir test olarak işaretlemeniz gereken bir mektup veriyoruz.

---

## Başlangıç noktası

İşaretlenmemiş ham metin:

```text
Dr. Eleanor Gaye
Awesome Science faculty
University of Awesome
Bobtown, CA 99999,
USA
Tel: 123-456-7890
Email: no_reply@example.com

20 January 2016

Miss Eileen Dover
4321 Cliff Top Edge
Dover, CT9 XXX
UK

Re: Eileen Dover university application

Dear Eileen,

Thank you for your recent application to join us at the University of
Awesome's science faculty to study as part of your
PhD (Doctor of Philosophy) next year. I will answer your
questions one by one, in the following sections.

Starting dates

We are happy to accommodate you starting your study with us at any time,
however it would suit us better if you could start at the beginning of a
semester; the start dates for each one are as follows:

First semester: 9 September 2016
Second semester: 15 January 2017
Third semester: 2 May 2017

Please let me know if this is ok, and if so which start date you would
prefer.

Subjects of study

At the Awesome Science Faculty, we have a pretty open-minded research
facility — as long as the subjects fall somewhere in the realm of science
and technology. You seem like an intelligent, dedicated researcher, and
just the kind of person we'd like to have on our team. Saying that, of the
ideas you submitted we were most intrigued by are as follows, in order of
priority:

Turning H2O into wine, and the health benefits of Resveratrol
(C14H12O3).
Measuring the effect on performance of funk bass players at temperatures
exceeding 30°C (86°F), when the audience size exponentially increases
(effect of 3 × 103 increasing to 3 × 104).
HTML, Hypertext Markup Language, and CSS,
Cascading Style Sheets, constructs for representing musical scores.

So please can you provide more information on each of these subjects,
including how long you'd expect the research to take, required staff and
other resources, and anything else you think we'd need to know? Thanks.

Exotic dance moves

Yes, you are right! As part of my post-doctorate work, I
did study exotic tribal dances. To answer your question, my
favorite dances are as follows, with definitions:

Polynesian chicken dance
    A little known but very influential dance dating back as far as
    300 BCE, a whole village would
    dance around in a circle like chickens, to encourage their livestock to
    be "fruitful".
Icelandic brownian shuffle
    Before the Icelanders developed fire as a means of getting warm, they
    used to practice this dance, which involved huddling close together in a
    circle on the floor, and shuffling their bodies around in imperceptibly
    tiny, very rapid movements. One of my fellow students used to say that
    he thought this dance inspired modern styles such as Twerking.
Arctic robot dance
    An interesting example of historic misinformation, English explorers in
    the 1960s believed to have discovered a new dance style characterized by
    "robotic", stilted movements, being practiced by inhabitants of Northern
    Alaska and Canada. Later on however it was discovered that they were
    just moving like this because they were really cold.

Yours sincerely,

Dr Eleanor Gaye

University of Awesome motto: Be awesome to each other. --
The memoirs of Bill S Preston, Esq.
```

---

## Proje özeti ve yönergeler

Bir üniversite intranetinde barındırılması gereken bir mektubu işaretlemeniz gerekmektedir. Mektup, bir araştırmacının üniversiteye başvuran aday bir doktora öğrencisine verdiği yanıttır.

### Blok / yapısal anlambilim:
* Doctype ile `<html>`, `<head>` ve `<body>` elementlerini içeren uygun bir HTML yapısı ekleyin.
* Genel olarak mektup başlıklar ve paragraflar olarak yapılandırılmalıdır. Bir adet en üst düzey başlık (`Re:` satırı) ve üç adet ikinci düzey başlık (`<h2>`) bulunmalıdır.
* İki adresi `<address>` elementleri içine yerleştirin. Adresin her satırı yeni bir satırda (`<br />`) olmalı, ancak yeni bir paragrafta olmamalıdır.
* Dönem başlangıç tarihleri (`<ul>`), çalışma konuları (`<ol>`) ve egzotik danslar (`<dl>`) için uygun liste türlerini kullanın.

### Satır içi anlambilim:
* Gönderen ve alıcının adları (ve *Tel*, *Email* etiketleri) `<strong>` ile işaretlenmelidir.
* Belgedeki dört tarih makine tarafından okunabilir tarihler barındıran `<time>` elementlerine sarılmalıdır.
* İlk adres ve ilk tarih `class="sender-column"` niteliğine sahip olmalıdır (sağa yaslanmaları için).
* Ana metindeki beş kısaltmayı/akronimi işaretleyin: "PhD", "HTML", "CSS", "BCE" ve "Esq.".
* Alt ve üst simgeleri (`<sub>` ve `<sup>`) kimyasal formüllerde ($H_2O$, $C_{14}H_{12}O_3$) ve $10^3$, $10^4$ sayılarında uygun şekilde işaretleyin.
* Üniversite sloganı alıntısını `<q>` ve kaynak gösterimini `<cite>` ile işaretleyin.

### Belgenin head bölümü:
* Karakter kümesi `<meta charset="utf-8" />` olmalıdır.
* Yazar `<meta name="author" content="Dr. Eleanor Gaye" />` olarak belirtilmelidir.
* Belgenin dili `<html lang="en-US">` olarak ayarlanmalıdır.
* Belge başlığı `<title>Awesome science application correspondence</title>` olmalıdır.
* Verilen CSS head içine bir `<style>` elementi içine eklenmelidir.

---

## Eksiksiz çözüm

```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <meta name="author" content="Dr. Eleanor Gaye" />
    <title>Awesome science application correspondence</title>
    <style>
      body {
        font: 1.2em / 1.5 system-ui;
      }

      .sender-column {
        text-align: right;
      }

      h1 {
        font-size: 1.5em;
      }

      h2 {
        font-size: 1.3em;
      }
    </style>
  </head>
  <body>
    <address class="sender-column">
      <strong>Dr. Eleanor Gaye</strong><br />
      Awesome Science faculty<br />
      University of Awesome<br />
      Bobtown, CA 99999,<br />
      USA<br />
      <strong>Tel</strong>: 123-456-7890<br />
      <strong>Email</strong>: no_reply@example.com
    </address>

    <p class="sender-column">
      <time datetime="2016-01-20">20 January 2016</time>
    </p>

    <address>
      <strong>Miss Eileen Dover</strong><br />
      4321 Cliff Top Edge<br />
      Dover, CT9 XXX<br />
      UK
    </address>

    <h1>Re: Eileen Dover university application</h1>

    <p>Dear Eileen,</p>

    <p>
      Thank you for your recent application to join us at the University of
      Awesome's science faculty to study as part of your
      <abbr>PhD</abbr> (Doctor of Philosophy) next year. I will answer your
      questions one by one, in the following sections.
    </p>

    <h2>Starting dates</h2>

    <p>
      We are happy to accommodate you starting your study with us at any time,
      however it would suit us better if you could start at the beginning of a
      semester; the start dates for each one are as follows:
    </p>

    <ul>
      <li>
        First semester: <time datetime="2016-09-09">9 September 2016</time>
      </li>
      <li>
        Second semester: <time datetime="2017-01-15">15 January 2017</time>
      </li>
      <li>Third semester: <time datetime="2017-05-02">2 May 2017</time></li>
    </ul>

    <p>
      Please let me know if this is ok, and if so which start date you would
      prefer.
    </p>

    <h2>Subjects of study</h2>

    <p>
      At the Awesome Science Faculty, we have a pretty open-minded research
      facility — as long as the subjects fall somewhere in the realm of science
      and technology. You seem like an intelligent, dedicated researcher, and
      just the kind of person we'd like to have on our team. Saying that, of the
      ideas you submitted we were most intrigued by are as follows, in order of
      priority:
    </p>

    <ol>
      <li>
        Turning H<sub>2</sub>O into wine, and the health benefits of Resveratrol
        (C<sub>14</sub>H<sub>12</sub>O<sub>3</sub>).
      </li>
      <li>
        Measuring the effect on performance of funk bass players at temperatures
        exceeding 30°C (86°F), when the audience size exponentially increases
        (effect of 3 × 10<sup>3</sup> increasing to 3 × 10<sup>4</sup>).
      </li>
      <li>
        <abbr>HTML</abbr>, Hypertext Markup Language, and <abbr>CSS</abbr>,
        Cascading Style Sheets, constructs for representing musical scores.
      </li>
    </ol>

    <p>
      So please can you provide more information on each of these subjects,
      including how long you'd expect the research to take, required staff and
      other resources, and anything else you think we'd need to know? Thanks.
    </p>

    <h2>Exotic dance moves</h2>

    <p>
      Yes, you are right! As part of my post-doctorate work, I
      <em>did</em> study exotic tribal dances. To answer your question, my
      favorite dances are as follows, with definitions:
    </p>

    <dl>
      <dt>Polynesian chicken dance</dt>
      <dd>
        A little known but <em>very</em> influential dance dating back as far as
        300 <abbr title="Before Common Era">BCE</abbr>, a whole village would
        dance around in a circle like chickens, to encourage their livestock to
        be "fruitful".
      </dd>
      <dt>Icelandic brownian shuffle</dt>
      <dd>
        Before the Icelanders developed fire as a means of getting warm, they
        used to practice this dance, which involved huddling close together in a
        circle on the floor, and shuffling their bodies around in imperceptibly
        tiny, very rapid movements. One of my fellow students used to say that
        he thought this dance inspired modern styles such as Twerking.
      </dd>
      <dt>Arctic robot dance</dt>
      <dd>
        An interesting example of historic misinformation, English explorers in
        the 1960s believed to have discovered a new dance style characterized by
        "robotic", stilted movements, being practiced by inhabitants of Northern
        Alaska and Canada. Later on however it was discovered that they were
        just moving like this because they were really cold.
      </dd>
    </dl>

    <p>Yours sincerely,</p>

    <p>Dr Eleanor Gaye</p>

    <p>
      University of Awesome motto: <q>Be awesome to each other.</q> --
      <cite
        >The memoirs of Bill S Preston, <abbr title="Esquire">Esq.</abbr></cite
      >
    </p>
  </body>
</html>
```

---
# 10. Belgeleri yapılandırma

**HTML** > **Structuring documents** | English (US)

HTML, sayfanızın tek tek parçalarını tanımlamanın yanı sıra (örneğin "bir paragraf" veya "bir görsel"), web sitenizin alanlarını (örneğin "header", "navigasyon menüsü", "ana içerik sütunu") tanımlamak için kullanılan bir dizi blok düzeyinde elemente de sahiptir. Bu makale, temel bir web sitesi yapısının nasıl planlanacağını ve bu yapıyı temsil eden HTML'in nasıl yazılacağını inceler.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | Basic HTML Syntax bölümünde ele alındığı gibi temel HTML aşinalığı. Başlıklar, paragraflar ve listeler gibi metin düzeyi anlambilim. |
| **Learning outcomes (Öğrenim çıktıları):** | • Yaygın HTML anlamsal yapısal elementleri (`<main>`, `<section>`, `<article>`, `<header>`, `<nav>` ve `<footer>`) ve bunların doğru kullanımı.<br>• Yalnızca `<div>` kullanmak yerine uygun yerlerde anlamsal elementleri kullanma gerekliliği ve bunun sağladığı faydalar (gelişmiş erişilebilirlik vb.). |

---

## Bir belgenin temel bölümleri

Web sayfaları birbirinden oldukça farklı görünebilir, ancak tam ekran bir video/oyun göstermedikleri veya kötü yapılandırılmadıkları sürece genellikle benzer standart bileşenleri paylaşırlar:

* **header (üstbilgi):** Genellikle büyük bir başlık, logo ve belki de bir slogan içeren, sayfanın en üstündeki geniş bir şerittir. Bu alan genellikle web sitesinin bir sayfasından diğerine aynı kalır.
* **navigation bar (gezinti çubuğu):** Sitenin ana bölümlerine bağlantılar içerir; genellikle menü butonları, linkler veya sekmelerle temsil edilir. Header gibi bu içerik de tutarlı kalmalıdır. Gezinti çubuğunu header'dan ayrı tutmak ekran okuyucuların iki özelliği daha iyi ayrıştırmasını sağlayarak erişilebilirliği artırır.
* **main content (ana içerik):** Sayfanın merkezindeki benzersiz içeriğin çoğunu barındıran büyük alandır (izlemek istediğiniz video, okuduğunuz ana hikaye, harita veya haber manşetleri). Sitede sayfadan sayfaya kesinlikle değişen tek bölümdür!
* **sidebar (kenar çubuğu):** Bazı ikincil bilgiler, bağlantılar, alıntılar veya reklamlar içerir. Genellikle ana içerikle bağlamsaldır (örneğin bir makale sayfasında yazarın biyografisi veya ilgili makalelere bağlantılar).
* **footer (altbilgi):** Sayfanın en altındaki şerittir; genellikle telif hakkı bildirimleri, yasal uyarılar veya iletişim bilgilerini içerir.

---

## İçeriği yapılandırmak için HTML

İçeriğimizi görsel olarak CSS ile istediğimiz gibi yerleştirebiliriz, ancak daha önce tartışıldığı gibi semantiğe saygı göstermeli ve **doğru iş için doğru elementi** kullanmalıyız. Görseller her şeyi anlatmaz; renk körlüğü veya görme engeli olan kullanıcılar için ekran okuyucular "ana navigasyonu bul" veya "ana içeriği bul" gibi işlemleri bu anlamsal etiketler sayesinde gerçekleştirir.

HTML şu anlamsal etiketleri sunar:

* **header:** `<header>`
* **navigation bar:** `<nav>`
* **main content:** `<main>`, alt bölümler için `<article>`, `<section>` ve `<div>`
* **sidebar:** `<aside>` (genellikle `<main>` içinde veya yanında yer alır)
* **footer:** `<footer>`

### Örnek Sayfa Kodu:

```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>My page title</title>
    <link rel="stylesheet" href="style.css" />
  </head>

  <body>
    <!-- Tüm sayfalarda kullanılan ana üstbilgi -->
    <header>
      <h1>Header</h1>
    </header>

    <!-- Gezinti menüsü -->
    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Our team</a></li>
        <li><a href="#">Projects</a></li>
        <li><a href="#">Contact</a></li>
      </ul>

      <!-- Arama formu -->
      <form>
        <input type="search" name="q" placeholder="Search query" />
        <input type="submit" value="Go!" />
      </form>
    </nav>

    <!-- Sayfanın ana içeriği -->
    <main>
      <!-- Bir makale -->
      <article>
        <h2>Article heading</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit...</p>

        <section>
          <h3>Subsection</h3>
          <p>Donec ut libero sed arcu vehicula ultricies a non tortor...</p>
        </section>

        <section>
          <h3>Another subsection</h3>
          <p>Vivamus fermentum semper porta. Nunc diam velit...</p>
        </section>
      </article>

      <!-- Kenar çubuğu içeriği -->
      <aside>
        <h2>Related</h2>
        <ul>
          <li><a href="#">Related link 1</a></li>
          <li><a href="#">Related link 2</a></li>
        </ul>
      </aside>
    </main>

    <!-- Tüm sayfalarda kullanılan altbilgi -->
    <footer>
      <p>©Copyright 2050 by nobody. All rights reserved.</p>
    </footer>
  </body>
</html>
```

---

## HTML düzen elementlerinin ayrıntılı tanımları

* `<main>`: *Bu sayfaya özgü* içerik içindir. Sayfa başına yalnızca **bir kez** kullanılmalı ve doğrudan `<body>` içine yerleştirilmelidir. Başka elementlerin içine yerleştirilmemelidir.
* `<article>`: Sayfanın geri kalanı olmadan da tek başına anlam ifade eden bağımsız bir içerik bloğunu sarar (örneğin tek bir blog yazısı veya haber makalesi).
* `<section>`: `<article>` elementine benzer, ancak sayfanın tek bir işlevsellik veya tema oluşturan belirli bir bölümünü gruplandırmak içindir (örneğin bir mini harita veya makale özetleri listesi). Her bölüme bir başlıkla başlamak en iyi uygulamadır.
* `<aside>`: Doğrudan ana içerikle ilgili olmayan ancak dolaylı olarak ek bilgi sağlayabilen içerikleri barındırır (sözlük maddeleri, yazar biyografisi, ilgili bağlantılar vb.).
* `<header>`: Bir grup tanıtıcı içeriği temsil eder. `<body>` elemanının çocuğuysa genel sayfa başlığını, bir `<article>` veya `<section>` elemanının çocuğuysa o bölüme özel başlığı tanımlar.
* `<nav>`: Sayfanın ana gezinti işlevini barındırır. İkincil bağlantılar navigasyon içine konulmamalıdır.
* `<footer>`: Bir sayfa veya bölüm için kapanış/son içerik grubunu temsil eder.

### Anlamsal olmayan kapsayıcılar: `<div>` ve `<span>`

Bazen bazı öğeleri gruplandırmak için ideal bir anlamsal element bulamazsınız; yalnızca CSS veya JavaScript ile hedeflemek için bir araya getirmek istersiniz. Bu durumlar için HTML `<div>` ve `<span>` elementlerini sağlar:

* `<span>`: Satır içi (inline) anlamsal olmayan elementtir. Anlamsal bir metin etiketi bulamadığınızda veya ekstra bir anlam eklemek istemediğinizde kullanılır:
  ```html
  <p>The King walked drunkenly... <span class="editor-note">[Editor's note: lights down].</span></p>
  ```
* `<div>`: Blok düzeyinde anlamsal olmayan elementtir. Uygun bir anlamsal blok elementi olmadığında kullanılır:
  ```html
  <div class="shopping-cart">
    <h2>Shopping cart</h2>
    <ul>
      <li>...</li>
    </ul>
  </div>
  ```

> [!WARNING]
> Div etiketlerini aşırı kullanmak ("div çorbası / div soup") kolaydır. Anlamsal değer taşımadıkları için kodunuzu gereksiz yere karmaşıklaştırırlar. Yalnızca daha iyi bir anlamsal çözüm olmadığında ve minimum düzeyde kullanın.

### Satır sonları ve yatay çizgiler: `<br>` ve `<hr>`

* `<br>`: Paragraf içinde satır sonu oluşturur. Şiir veya posta adresi gibi sabit kısa satırlar dizisi istediğiniz katı yapılar için kullanılır.
* `<hr>`: Belgede tematik bir değişimi (sahne veya konu değişikliği) simgeleyen yatay bir çizgi oluşturur.

---

## Özet

Bu noktada bir web sayfasını ve sitesini nasıl yapılandıracağınızı kavradınız. Sıradaki makalede web'in temel taşlarından olan köprüleri (**Creating links**) inceleyeceğiz.

---

# 11. Bağlantı oluşturma

**HTML** > **Creating links** | English (US)

Bağlantılar (köprüler / hyperlinks) web'i *Web* yapan temel özelliktir. Bu makale bir bağlantı oluşturmak için gereken sözdizimini gösterir ve bağlantı için en iyi uygulamaları tartışır.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | Basic HTML Syntax bölümünde ele alındığı gibi temel HTML aşinalığı. Başlıklar, paragraflar ve listeler. |
| **Learning outcomes (Öğrenim çıktıları):** | • Bağlantıların web için neden temel özellik olduğunu kavrama.<br>• `href` niteliği.<br>• Mutlak (absolute) ve göreceli (relative) yollar ve ne zaman kullanılacakları.<br>• Yol sözdizimi: eğik çizgiler (`/`), tek nokta (`.`), çift nokta (`..`).<br>• Bağlantı durumları (`:hover`, `:focus`, `:visited`, `:active`).<br>• Blok düzeyinde bağlantılar ve görsel bağlantıları.<br>• Erişilebilirlik ve SEO için iyi bağlantı metni yazmanın faydaları. |

---

## Bir bağlantının anatomisi

Temel bir bağlantı, metin veya diğer içeriğin bir `<a>` (anchor) elementi içine sarılması ve web adresini barındıran `href` (Hypertext Reference) niteliğinin kullanılmasıyla oluşturulur:

```html
<p>
  I'm creating a link to
  <a href="https://www.mozilla.org/en-US/">the Mozilla homepage</a>.
</p>
```

Çıktı: I'm creating a link to [the Mozilla homepage](https://www.mozilla.org/en-US/).

### Blok düzeyinde bağlantılar

Hemen hemen her içerik bir bağlantıya dönüştürülebilir; hatta blok düzeyindeki elementler bile:

```html
<a href="https://developer.mozilla.org/en-US/">
  <h1>MDN Web Docs</h1>
</a>
<p>
  Documenting web technologies, including CSS, HTML, and JavaScript, since 2005.
</p>
```

### Görsel bağlantıları

Bir görseli bağlantıya dönüştürmek için `<img>` elementini bir `<a>` elementiyle sarın:

```html
<a href="https://developer.mozilla.org/en-US/">
  <img src="mdn_logo.svg" alt="MDN Web Docs" />
</a>
```

### `title` niteliği ile ek bilgi sağlama

Bağlantılarınıza bir `title` niteliği ekleyebilirsiniz. Bu nitelik, bağlantı üzerine fare ile gelindiğinde ipucu (tooltip) olarak görünür:

```html
<p>
  I'm creating a link to
  <a
    href="https://www.mozilla.org/en-US/"
    title="The best place to find more information about Mozilla's mission and how to contribute">
    the Mozilla homepage</a
  >.
</p>
```

> [!NOTE]
> Link başlığı yalnızca fareyle üzerine gelindiğinde görünür; dokunmatik ekran veya klavye kullanıcıları bu bilgiye erişmekte zorlanabilir. Bu nedenle gerçekten kritik bilgileri doğrudan normal metin içinde sunmalısınız.

### Bağlantı Oluşturma Alıştırması:

```html
<h1>Squirrels</h1>

<p>
  Two of the most common and best-known squirrel species are the:
</p>

<ul>
  <li>
    <a
      href="https://en.wikipedia.org/wiki/Red_squirrel"
      title="Sciurus vulgaris">
      Red squirrel
    </a>
  </li>
  <li>
    <a
      href="https://en.wikipedia.org/wiki/Eastern_gray_squirrel"
      title="Sciurus carolinensis">
      Eastern gray squirrel
    </a>
  </li>
</ul>

<p>
  For a good starting point on squirrel information, see the
  <a href="https://en.wikipedia.org/wiki/Squirrel">Wikipedia Squirrel page</a>.
</p>
```

---

## URL'ler ve yollara hızlı giriş

Bağlantı hedefleri URL'lerdir (Uniform Resource Locator). URL'ler dosya yollarına benzer şekilde çalışır.

Bir proje dizini yapısını ele alalım:
* Kök dizin: `creating-hyperlinks/`
  * `index.html`
  * `contacts.html`
  * `pdfs/` -> `project-brief.pdf`
  * `projects/` -> `index.html`

### 1. Aynı dizin
Aynı dizindeki bir dosyaya bağlanmak için doğrudan dosya adını veya `./` ön ekini kullanabilirsiniz:
```html
<a href="contacts.html">contacts page</a>
<!-- Veya -->
<a href="./contacts.html">contacts page</a>
```

### 2. Alt dizinlere inme
Bir alt klasörün içindeki dosyaya bağlanmak için klasör adı, eğik çizgi ve dosya adı yazılır:
```html
<a href="projects/index.html">project homepage</a>
```

### 3. Üst dizinlere çıkma
Bir üst dizine çıkmak için iki nokta (`..`) kullanılır:
`projects/index.html` içinden `pdfs/project-brief.pdf` dosyasına gitmek için:
```html
<a href="../pdfs/project-brief.pdf">project brief</a>
```

### 4. Kök dizine göre bağlama
Başında tek bir eğik çizgi (`/`) bulunan yollar doğrudan sitenin kök dizininden başlar:
```html
<a href="/pdfs/project-brief.pdf">project brief</a>
```

### 5. Belge içi bölümlere bağlanma: `#`
Bir sayfadaki belirli bir başlığa veya bölüme (örneğin `<h2 id="mailing_address">`) bağlanmak için `#` işareti ve elemanın `id` değeri kullanılır:
```html
<!-- Başka bir sayfadaki bölüme bağlanma: -->
<a href="contacts.html#mailing_address">mailing address</a>

<!-- Aynı sayfa içinde bir bölüme kayma: -->
<a href="#mailing_address">company mailing address</a>
```

---

## Bağlantı en iyi uygulamaları

### 1. Açık ve açıklayıcı bağlantı metni kullanın
* **KÖTÜ:** Firefox'u indirmek için [buraya tıklayın](https://www.firefox.com).
* **İYİ:** [Firefox'u indirin](https://www.firefox.com).
* URL'yi metin olarak doğrudan yazmaktan kaçının (ekran okuyucular harf harf okur).
* Metinde "bağlantı" veya "link" kelimelerini kullanmayın; kullanıcı zaten onun link olduğunu bilir.

### 2. HTML dışı kaynaklara bağlantı verirken açık işaretler bırakın
Büyük bir PDF veya harici medya dosyasına bağlantı verirken dosya türünü ve boyutunu belirtin:
```html
<a href="/large-report.pdf" download>Download the sales report (PDF, 10MB)</a>
```

### 3. İndirme için `download` niteliğini kullanın
```html
<a href="installer.exe" download="firefox-installer.exe">Download Installer</a>
```

### 4. Bağlantıları yeni sekmede açma (`target="_blank"`)
Yeni sekmede açılan bağlantılar kullanıcıların geri butonunu kullanmasını zorlaştırabilir ve ekran okuyucu kullanıcılarının kafasını karıştırabilir. Genellikle harici bağlantılar için tercih edilir, ancak kullanıldığında bir simge veya uyarı ile belirtilmesi önerilir.

---

## E-posta bağlantıları: `mailto:`

Tıklandığında kullanıcının e-posta istemcisini açan bağlantılar `mailto:` şemasıyla oluşturulur:

```html
<a href="mailto:nowhere@mozilla.org">Send email to nowhere</a>
```

Konu, CC ve gövde parametreleri eklenebilir:

```html
<a href="mailto:nowhere@mozilla.org?cc=info@example.com&subject=Bilgi%20Talebi&body=Merhaba%2C">
  E-posta gönder
</a>
```

---

## Özet

Bağlantılar konusunu tamamladık. Sırada bu konudaki bilginizi ölçeceğiniz sınav (**Test: Links**) yer almaktadır.

---

# 12. Test: Bağlantılar

**HTML** > **Test your skills: Links** | English (US)

Bu beceri testinin amacı, HTML'de bağlantıların nasıl uygulanacağını anlayıp anlamadığınızı değerlendirmenize yardımcı olmaktır.

---

## Bağlantılar 1

Balinalar bilgi sayfasındaki bağlantıları tamamlayın:
1. İlk bağlantı aynı dizindeki `whales.html` sayfasına gitmeli ve fareyle üzerine gelindiğinde mavi balinalar ve ispermeçet balinaları hakkında bilgi içerdiğini belirten bir tooltip başlığına sahip olmalıdır.
2. İkinci bağlantı `whales@example.com` adresine giden bir e-posta bağlantısı olmalı ve konu satırı otomatik olarak "Question about Whales" olarak doldurulmalıdır.

### Çözüm:

```html
<h1>Information on Whales</h1>

<p>
  For more information on our conservation activities and which Whales we study,
  see our <a target="_blank" href="whales.html" title="Includes information on Blue Whales and Sperm Whales">
  Whales page</a>.
</p>

<p>
  If you want to ask our team more questions, feel free to
  <a target="_blank" href="mailto:whales@example.com?subject=Question%20about%20Whales">
  email us</a>.
</p>
```

---

## Bağlantılar 2

Dört bağlantıyı uygun konumlara bağlayın:
1. Geçerli dizin içindeki `blue` klasöründe bulunan `blue-whale.jpg` görseline bağlantı.
2. Geçerli dizinin bir üst düzeyinde bulunan `narwhal` klasöründeki `narwhal.jpg` görseline bağlantı.
3. UK Google Görsel Arama sayfasına (`https://www.google.co.uk/imghp`) bağlantı.
4. Sayfanın en altındaki `id="bottom"` olan paragrafa bağlantı.

### Çözüm:

```html
<h1>List path tests</h1>

<ul>
  <li><a target="_blank" href="blue/blue-whale.jpg">
    Link me to the blue whale image
  </a></li>
  <li><a target="_blank" href="../narwhal/narwhal.jpg">
    Link me to the narwhal image
  </a></li>
  <li><a target="_blank" href="https://www.google.co.uk/imghp">
    Link me to Google image search
  </a></li>
  <li><a href="#bottom">
    Link me to the paragraph at the bottom of the page
  </a></li>
</ul>

<div></div>

<p id="bottom">The bottom of the page!</p>
```

---

## Bağlantılar 3

Kötü yazılmış bağlantı metinlerini ("buraya tıklayın" gibi) düzeltin ve dosya indirme bağlantısına dosya türü ve boyut uyarısı ekleyin.

### Çözüm:

```html
<p>
  We do lots of work with Narwhals. <a href="narwhals.html" target="_blank">Find out more about this work</a>.
</p>

<p>
  You can <a href="mailto:whales@example.com">email our support team</a> if you have any more questions.
</p>

<p>
  You can also <a href="factfile.pdf" target="_blank">download
  our factfile</a> (PDF, 4MB), which contains lots more information, including an FAQ.
</p>
```

---

# 13. Uygulama Görevi: Kuş gözlem sitesi

**HTML** > **Challenge: Structuring a page of content** | English (US)

Bir içerik sayfasını CSS kullanarak düzenlemeye hazır şekilde yapılandırmak çok önemli bir beceridir. Bu meydan okumada, bir kuş gözlemciliği web sitesinin ana sayfa içeriğini alacak ve üzerine bir sayfa düzeni uygulanabilmesi için yapısal elementler ekleyeceksiniz.

---

## Proje özeti ve yönergeler

### 1. İçerik Eklemleri:
* `<h1>` elementi içine güvercin logosunu içeren bir `<img>` elementi ekleyin ve boş bir `alt=""` verin.
* "Home", "Get started", "Photos", "Gear" ve "Forum" metinlerini sırasız bir liste (`<ul>`) halinde navigasyon menüsüne dönüştürün ve `#` adresine bağlayın.
* Dört favori kuş görselinin küçük resimlerini (thumbnails) ekleyin; her birine uygun alternatif metin verin ve tam boyutlu görsellere bağlantı kurun.

### 2. Yapısal Gereksinimler:
* En üst düzey başlığı ve navigasyon menüsünü saran bir `<header>`.
* Navigasyon menüsünü saran bir `<nav>`.
* İki sütun içeren bir `<main>`: karşılama metnini barındıran bir `<article>` ve görsel küçük resimlerini barındıran bir `<aside>`.
* Telif hakkı ve teşekkür bilgilerini barındıran bir `<footer>`.

---

## Eksiksiz çözüm

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Birdwatching</title>
    <link
      href="https://fonts.googleapis.com/css?family=Roboto+Condensed:300%7CCinzel+Decorative:700"
      rel="stylesheet" />
    <link href="style.css" rel="stylesheet" />
  </head>

  <body>
    <header>
      <h1>
        Birdwatching
        <img
          src="https://mdn.github.io/shared-assets/images/examples/learn/birds/dove.png"
          alt="" />
      </h1>

      <nav>
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">Get started</a></li>
          <li><a href="#">Photos</a></li>
          <li><a href="#">Gear</a></li>
          <li><a href="#">Forum</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <article>
        <h2>Welcome</h2>

        <p>
          Welcome to our fake birdwatching site. If this were a real site, it
          would be the ideal place to come to learn more about birdwatching,
          whether you are a beginner looking to learn how to get into birding,
          or an expert wanting to share ideas, tips, and photos with other
          like-minded people.
        </p>

        <p>
          So don't waste time! Get what you need, then turn off that computer
          and get out into the great outdoors!
        </p>
      </article>

      <aside>
        <h2>Favorite photos</h2>

        <a
          href="https://mdn.github.io/shared-assets/images/examples/learn/birds/favorite-bird-1.jpg">
          <img
            src="https://mdn.github.io/shared-assets/images/examples/learn/birds/favorite-bird-1_th.jpg"
            alt="Small black bird, black claws, long black slender beak" />
        </a>
        <a
          href="https://mdn.github.io/shared-assets/images/examples/learn/birds/favorite-bird-2.jpg">
          <img
            src="https://mdn.github.io/shared-assets/images/examples/learn/birds/favorite-bird-2_th.jpg"
            alt="Top half of a pretty bird with bright blue plumage on neck, light colored beak, blue headdress" />
        </a>
        <a
          href="https://mdn.github.io/shared-assets/images/examples/learn/birds/favorite-bird-3.jpg">
          <img
            src="https://mdn.github.io/shared-assets/images/examples/learn/birds/favorite-bird-3_th.jpg"
            alt="Top half of a large bird with white plumage, very long curved narrow light colored break" />
        </a>
        <a
          href="https://mdn.github.io/shared-assets/images/examples/learn/birds/favorite-bird-4.jpg">
          <img
            src="https://mdn.github.io/shared-assets/images/examples/learn/birds/favorite-bird-4_th.jpg"
            alt="Large bird, mostly white plumage with black plumage on back and rear, long straight white beak" />
        </a>
      </aside>
    </main>

    <footer>
      <p>
        This fake website example is CC0 — any part of this code may be reused
        in any way you wish. Original example written by Chris Mills, 2016.
      </p>

      <p>
        <a href="http://game-icons.net/lorc/originals/dove.html">Dove icon</a>
        by Lorc.
      </p>
    </footer>
  </body>
</html>
```

---
# 14. Görseller

**HTML** > **HTML images** | English (US)

Başlangıçta web yalnızca metinden ibaretti ve oldukça sıkıcıydı. Neyse ki web sayfalarının içine görselleri (ve diğer daha ilginç içerik türlerini) gömme yeteneği çok geçmeden eklendi. Bu makalede, temelleri, `<figure>` kullanarak altyazılarla açıklama eklemeyi ve CSS arka plan görselleriyle ilişkisini içeren `<img>` elementini derinlemesine inceleyeceğiz.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | Basic HTML Syntax bölümünde ele alındığı gibi temel HTML aşinalığı. Başlıklar, paragraflar ve listeler. |
| **Learning outcomes (Öğrenim çıktıları):** | • "Replaced element" (değiştirilen element) teriminin anlamı.<br>• Temel `<img>` etiketi sözdizimi.<br>• Bir kaynağı işaret etmek için `src` kullanımı.<br>• Görsel yüklendiğinde kullanıcı arayüzündeki sarsıntıları (layout shift) önlemek için `width` ve `height` kullanımı.<br>• Web için medya varlıklarını optimize etme (küçük dosya boyutları sağlama).<br>• Medya lisans türlerini anlama (telif hakkı, serbest lisanslar, kamu malı/CC0). |

---

## Web sayfasına nasıl görsel ekleriz?

Bir web sayfasına görsel yerleştirmek için `<img>` elementini kullanırız. Bu bir **void element**'tir (yani alt içeriğe sahip olamaz ve kapanış etiketi bulunmaz) ve işlevsel olabilmesi için iki temel niteliğe ihtiyaç duyar: `src` ve `alt`.

* `src`: Sayfaya gömmek istediğiniz görseli işaret eden bir URL barındırır. Göreceli veya mutlak bir URL olabilir. `src` niteliği olmadan `img` elementi hiçbir görsel yükleyemez.

Örnekler:
* Görsel HTML sayfasıyla aynı dizindeyse:
  ```html
  <img src="dinosaur.jpg" alt="Dinosaur" />
  ```
* Görsel bir `images` alt klasöründeyse:
  ```html
  <img src="images/dinosaur.jpg" alt="Dinosaur" />
  ```

> [!WARNING]
> İzin almadan *asla* `src` niteliğini başka birinin web sitesinde barındırılan bir görsele doğrudan yönlendirmeyin. Buna **hotlinking** denir. Başkasına bant genişliği maliyeti yüklediği için etik dışı kabul edilir; ayrıca görselin kaldırılması ya da yerine uygunsuz bir görsel konması üzerinde hiçbir kontrolünüz kalmaz.

> [!NOTE]
> `<img>` ve `<video>` gibi elementlere bazen **replaced elements (değiştirilen elementler)** denir. Bunun nedeni, elementin içeriğinin ve boyutunun elementin kendisi tarafından değil, harici bir kaynak (görsel veya video dosyası) tarafından belirlenmesidir.

---

## Alternatif metin: `alt`

İnceleyeceğimiz bir sonraki nitelik `alt` niteliğidir. Değeri, görselin görülemediği/görüntülenemediği veya yavaş bir internet bağlantısı nedeniyle yüklenmesinin uzun sürdüğü durumlarda kullanılmak üzere görselin metinsel bir açıklaması olmalıdır:

```html
<img
  src="images/dinosaur.jpg"
  alt="The head and torso of a dinosaur skeleton;
          it has a large head with long sharp teeth" />
```

### Alt metin neden gereklidir?
* Görme engelli kullanıcılar web'i kendilerine seslendiren **ekran okuyucular** kullanır.
* Dosya adı veya yol adı yanlış yazılmış olabilir.
* Tarayıcı görsel türünü desteklemiyor olabilir (veya Lynx gibi salt metin tarayıcılar kullanılmaktadır).
* Arama motorları arama sorgularını eşleştirmek için alt metinleri dizine ekler.
* Kullanıcılar veri tasarrufu sağlamak için görselleri kapatmış olabilir.

### `alt` niteliğine ne yazılmalıdır?
* **Dekorasyon:** Görsel yalnızca dekoratif amaçlıysa, boş bir `alt=""` ekleyin. Ekran okuyucu boş alt metinli görselleri atlayarak zaman kaybetmez.
* **İçerik:** Görsel önemli bir bilgi sunuyorsa, aynı bilgiyi *kısa* bir `alt` metninde sağlayın. Ana metinde zaten tam olarak anlatılan bir görsel için gereksiz yere uzun alt metinler yazmayın (`alt=""` kullanabilirsiniz).
* **Bağlantı:** Bir görseli `<a>` içine koyarak linke dönüştürürseniz, erişilebilir bağlantı metnini mutlaka sağlamalısınız (bağlantı metni olarak veya `alt` içinde).
* **Metin:** Metinleri görsellerin içine gömmekten kaçının. Başlığın gölgeye ihtiyacı varsa bunu CSS ile yapın.

---

## Genişlik ve yükseklik

Görselin genişliğini ve yüksekliğini belirtmek için `width` ve `height` niteliklerini kullanabilirsiniz. Bunlar birim olmadan piksel cinsinden tam sayı olarak verilir:

```html
<img
  src="images/dinosaur.jpg"
  alt="The head and torso of a dinosaur skeleton"
  width="400"
  height="341" />
```

Bunu yapmanın çok önemli bir nedeni vardır: HTML belgesi ve görseller ayrı kaynaklardır. Tarayıcı HTML'i alır almaz ekranda göstermeye başlar. Görselin boyutları belirtilmemişse, görsel yüklendiğinde aniden yer kaplar ve altındaki metinleri aşağıya kaydırır (Layout Shift). Bu durum kullanıcıyı rahatsız eder ve tarayıcıyı sayfayı yeniden işlemeye (re-render) zorlayarak performansı düşürür. Boyutlar önceden verilirse tarayıcı gereken boşluğu en baştan ayırır.

> [!WARNING]
> Görselleri HTML nitelikleriyle *yeniden boyutlandırmayın*. Görseli olduğundan çok büyük ayarlarsanız bulanıklaşır ve gereksiz bant genişliği harcar. Görseli web sayfasına koymadan önce bir görsel düzenleyicide uygun boyuta getirin veya CSS kullanın.

---

## Görsel başlıkları

Bağlantılarda olduğu gibi görsellere de `title` niteliği ekleyebilirsiniz:

```html
<img
  src="images/dinosaur.jpg"
  alt="The head and torso of a dinosaur skeleton"
  width="400"
  height="341"
  title="A T-Rex on display in the Manchester University Museum" />
```

Ancak ekran okuyucu desteğinin öngörülemez olması ve klavye kullanıcıları tarafından erişilememesi nedeniyle `title` kullanımı önerilmez. Destekleyici bilgileri doğrudan makale metninde sunmak daha iyidir.

---

## Medya varlıkları ve lisanslama

* **All rights reserved (Tüm hakları saklıdır):** Telif hakkı sahibinin münhasır hakları vardır. Yazılı izin almalı veya lisans ücreti ödemelisiniz.
* **Permissive licenses (İzin verici lisanslar):** MIT, BSD veya Creative Commons (CC). Belirli koşullara (atıfta bulunma, değişiklikleri belirtme, aynı lisansla paylaşma / copyleft vb.) uymak kaydıyla ücretsiz kullanılabilir.
* **Public domain / CC0 (Kamu Malı):** Hiçbir telif hakkı geçerli değildir; izin almadan veya koşulsuz olarak kullanılabilir.

---

## Görsellere `<figure>` ve `<figcaption>` ile açıklama ekleme

Görselleri altyazılarla ilişkilendirmek için anlamsal `<figure>` ve `<figcaption>` elementleri kullanılır:

```html
<figure>
  <img
    src="images/dinosaur.jpg"
    alt="The head and torso of a dinosaur skeleton"
    width="400"
    height="341" />
  <figcaption>
    A T-Rex on display in the Manchester University Museum.
  </figcaption>
</figure>
```

`<figcaption>` elementi tarayıcılara ve yardımcı teknolojilere bu altyazının `<figure>` içindeki içeriği açıkladığını net bir şekilde bildirir.

---

## CSS arka plan görselleri

Görseller CSS ile de gömülebilir (`background-image: url(...)`). CSS arka plan görselleri **yalnızca dekorasyon** içindir; hiçbir anlamsal değer taşımazlar ve ekran okuyucular tarafından görülemezler. İçeriğin parçası olan ve anlam taşıyan görseller için mutlaka HTML `<img>` elementi kullanılmalıdır.

---

# 15. Test: Görseller

**HTML** > **Test your skills: HTML images** | English (US)

Bu beceri testinin amacı, resimleri ve bunların HTML'e nasıl gömüleceğini anlayıp anlamadığınızı değerlendirmenize yardımcı olmaktır.

---

## Görseller 1

Yaban mersini görselini sayfaya gömün:
* `src`: `https://github.com/mdn/learning-area/blob/main/html/multimedia-and-embedding/tasks/images/blueberries.jpg?raw=true`
* `alt`: Açıklayıcı alternatif metin.
* `width="400"` ve orijinal en-boy oranını (615x419) koruyacak şekilde hesaplanan `height="273"`.

### Çözüm:

```html
<h1>Basic image embed</h1>

<img src="https://github.com/mdn/learning-area/blob/main/html/multimedia-and-embedding/tasks/images/blueberries.jpg?raw=true"
     alt="blueberries" width="400" height="273" />

<p>You should see a picture of some blueberries above.</p>
```

---

## Görseller 2

Görsele fareyle üzerine gelindiğinde görünen bir `title` ipucu başlığı ekleyin.

### Çözüm:

```html
<h1>Basic image title</h1>

<img
  src="https://github.com/mdn/learning-area/blob/main/html/multimedia-and-embedding/tasks/images/larch.jpg?raw=true"
  alt="Several tall evergreen trees called larches"
  title="And now, Number 1, The Larch" />
```

---

## Görseller 3

Görseli ve altyazıyı anlamsal olarak birbirine bağlayan `<figure>` ve `<figcaption>` elementlerini ekleyin.

### Çözüm:

```html
<h1>Image and caption</h1>

<figure>
  <img
    src="https://github.com/mdn/learning-area/blob/main/html/multimedia-and-embedding/tasks/images/firefox.png?raw=true"
    alt="An abstract flaming fox wrapping around a blue sphere"
    width="446"
    height="460" />
  <figcaption>The 2019 Firefox logo</figcaption>
</figure>
```

---

# 16. Video ve ses

**HTML** > **HTML video and audio** | English (US)

HTML5 ile birlikte Flash ve Silverlight gibi eklenti tabanlı eski teknolojiler terk edilmiş, yerel `<video>` ve `<audio>` elementleri standart hale gelmiştir. Bu makale video ve ses oynatıcılarını ve altyazı/metin parçalarını (`<track>`) incelemektedir.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | Basic HTML Syntax bölümünde ele alındığı gibi temel HTML aşinalığı. Başlıklar, paragraflar ve listeler. |
| **Learning outcomes (Öğrenim çıktıları):** | • Temel `<video>` ve `<audio>` sözdizimi.<br>• `controls`, `autoplay`, `loop`, `muted` gibi medyaya özgü nitelikler.<br>• Farklı medya kaynakları sağlamak için `<source>` elementlerinin kullanımı.<br>• Altyazılar (captions/subtitles) için WebVTT ve `<track>` kullanımı. |

---

## `<video>` elementi

Temel bir video oynatıcı:

```html
<video src="rabbit320.webm" controls>
  <p>
    Your browser doesn't support HTML video. Here is a
    <a href="rabbit320.webm">link to the video</a> instead.
  </p>
</video>
```

* `src`: Gömülecek videonun yolunu belirtir.
* `controls`: Kullanıcının oynatma/durdurma ve ses kontrolü yapabilmesi için tarayıcının yerleşik kontrollerini gösterir (erişilebilirlik ve epilepsi hastaları için hayati önem taşır).
* `<p>` içeriği: Tarayıcı `<video>` elementini desteklemiyorsa görüntülenecek **yedek içeriktir (fallback content)**.

---

## Uyumluluğu artırmak için çoklu kaynak formatları kullanma

Farklı tarayıcılar farklı video ve ses formatlarını/kodeklerini destekler.
* **Konteyner formatları:** MP4, WebM, OGG.
* **Kodekler:** H.264, VP8/VP9, AV1 (video için); AAC, MP3, Opus, Vorbis (ses için).

Birden çok format sunmak için `src` niteliği yerine `<source>` elementleri kullanılır:

```html
<video controls>
  <source src="rabbit320.mp4" type="video/mp4" />
  <source src="rabbit320.webm" type="video/webm" />
  <p>
    Your browser doesn't support this video. Here is a
    <a href="rabbit320.mp4">link to the video</a> instead.
  </p>
</video>
```

`type` niteliği dosyanın MIME türünü belirtir; bu sayede tarayıcı desteklemediği formatı indirmeye çalışmadan hemen atlar.

---

## Diğer `<video>` özellikleri

```html
<video
  controls
  width="400"
  height="400"
  autoplay
  loop
  muted
  preload="auto"
  poster="poster.png">
  <source src="rabbit320.mp4" type="video/mp4" />
  <source src="rabbit320.webm" type="video/webm" />
  <p>Your browser doesn't support this video.</p>
</video>
```

* `width` ve `height`: Oynatıcı boyutlarını belirler.
* `autoplay`: Sayfa yüklenir yüklenmez oynatmayı başlatır (kullanıcıyı rahatsız edebileceği için genellikle önerilmez; birçok tarayıcı yalnızca `muted` ile birlikte izin verir).
* `loop`: Video bittiğinde başa sarıp tekrar oynatır.
* `muted`: Sesi varsayılan olarak kapalı başlatır.
* `poster`: Video oynatılmadan önce gösterilecek kapak görselidir.
* `preload`: Büyük dosyaların önbelleğe alınmasını yönetir (`"none"`, `"auto"`, `"metadata"`).

---

## `<audio>` elementi

`<audio>` elementi görsel bir bileşeni olmadığı için `width`, `height` ve `poster` niteliklerini desteklememesi dışında `<video>` ile tamamen aynı mantıkla çalışır:

```html
<audio controls>
  <source src="viper.mp3" type="audio/mp3" />
  <source src="viper.ogg" type="audio/ogg" />
  <p>
    Your browser doesn't support HTML audio. Here is a
    <a href="viper.mp3">link to the audio</a> instead.
  </p>
</audio>
```

---

## Video metin parçalarını ve altyazıları görüntüleme

İşitme engelli kullanıcılar, gürültülü ortamlarda bulunanlar veya videonun dilini bilmeyenler için altyazı sağlamak amacıyla **WebVTT** (`.vtt`) formatı ve `<track>` elementi kullanılır:

```html
<video controls>
  <source src="example.mp4" type="video/mp4" />
  <source src="example.webm" type="video/webm" />
  <track kind="subtitles" src="subtitles_en.vtt" srclang="en" label="English" default />
  <track kind="subtitles" src="subtitles_tr.vtt" srclang="tr" label="Türkçe" />
</video>
```

* `kind`: `subtitles` (altyazı), `captions` (işitme engelliler için ses efektleri içeren açıklamalı altyazı) veya `descriptions` (sesli betimleme).
* `srclang`: Altyazının dil kodu.
* `label`: Kullanıcıya gösterilecek dil adı.
* `default`: Varsayılan olarak etkinleştirilecek parça.

---

# 17. Test: Ses ve video

**HTML** > **Test your skills: Audio and video** | English (US)

Bu beceri testinin amacı, HTML'de video ve ses içeriğini nasıl gömeceğinizi anlayıp anlamadığınızı değerlendirmenize yardımcı olmaktır.

---

## Ses ve video 1

Verilen adresteki ses dosyasını varsayılan tarayıcı kontrolleriyle sayfaya gömün.

### Çözüm:

```html
<h1>Basic audio embed</h1>

<audio
  controls
  src="https://github.com/mdn/learning-area/raw/refs/heads/main/html/multimedia-and-embedding/tasks/audio-video/audio.mp3"></audio>
```

---

## Ses ve video 2

Çoklu kaynaklara, altyazıya ve ek özelliklere sahip bir video oynatıcı oluşturun:
1. Varsayılan kontroller (`controls`).
2. MP4 ve WebM kaynakları (`<source>` etiketleri ve `type` nitelikleri ile).
3. Orijinal boyutlar (`width="320"` `height="240"`).
4. Varsayılan olarak sessiz (`muted`).
5. İngilizce altyazı (`<track kind="subtitles" src="subtitles_en.vtt" srclang="en" label="English" default />`).

### Çözüm:

```html
<h1>Video embed</h1>

<video controls width="320" height="240" muted>
  <source
    src="https://github.com/mdn/learning-area/raw/refs/heads/main/html/multimedia-and-embedding/tasks/audio-video/video.mp4"
    type="video/mp4" />
  <source
    src="https://github.com/mdn/learning-area/raw/refs/heads/main/html/multimedia-and-embedding/tasks/audio-video/video.webm"
    type="video/webm" />
  <track
    kind="subtitles"
    src="subtitles_en.vtt"
    srclang="en"
    label="English"
    default />
</video>
```

---

# 18. Uygulama Görevi: Tanıtım sayfası

**HTML** > **Challenge: Creepy-crawly splash page** | English (US)

Bu meydan okumada, böcekler ve diğer sürüngen canlılar hakkındaki bir açılış sayfasına (splash page) görseller ve video ekleyerek medya gömme becerilerinizi test edeceksiniz.

---

## Proje özeti ve yönergeler

### 1. Üstbilgiye video ekleme:
`<h1>` başlığının hemen altına header videosunu gömen bir `<video>` elementi ekleyin:
* Sayfa yüklenir yüklenmez otomatik oynatılmalı (`autoplay`).
* Otomatik oynatmanın çalışması için sessiz olmalı (`muted`).
* Sonsuz döngüde oynatılmalı (`loop`).
* İçerik önceden yüklenmeli (`preload="auto"`).
* Hiçbir kontrol gösterilmemelidir (yani `controls` niteliği **eklenmemelidir**).

### 2. Bölüm görsellerini ekleme:
Her böcek bölümündeki `<h2>` etiketinin altına uygun görseli ekleyin:
* Her görsel ekran okuyucular için uygun bir `alt` metnine sahip olmalı ve `width="250"` ile `height="180"` boyutlarıyla sınırlandırılmalıdır.
* Her görseli ve altyazısını semantik olarak bağlamak için `<figure>` ve `<figcaption>` kullanılmalıdır. Altyazı, `alt` metnini aynen tekrarlamamalıdır.

### 3. Gezinti menüsüne ve başlıklara emojiler ekleme:
Her navigasyon listesi öğesinin başına ve karşılık gelen `<h2>` başlığının başına ilgili böcek emojilerini ekleyin:
* 🪲 Beetles
* 🪳 True bugs
* 🦋 Butterflies and moths
* 🦟 Flies and mosquitos
* 🐝 Bees, wasps, and ants
* 🕷️ Spiders

---

## Eksiksiz çözüm

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Creepy crawlies!</title>
    <link href="style.css" rel="stylesheet" />
  </head>
  <body>
    <header>
      <nav>
        <ul>
          <li><a href="#beetles">🪲 Beetles</a></li>
          <li><a href="#true_bugs">🪳 True bugs</a></li>
          <li><a href="#butterflies_moths">🦋 Butterflies and moths</a></li>
          <li><a href="#flies_mosquitos">🦟 Flies and mosquitos</a></li>
          <li><a href="#bees_wasps_ants">🐝 Bees, wasps, and ants</a></li>
          <li><a href="#spiders">🕷️ Spiders</a></li>
        </ul>
      </nav>
      <section>
        <h1>Creepy-crawlies splash page!</h1>

        <video
          src="https://mdn.github.io/shared-assets/videos/learn/bug_video_640.mp4"
          autoplay
          loop
          muted
          preload="auto"></video>

        <p>
          In casual language, people use "bugs" to mean all sorts of small
          creepy-crawlies: insects, spiders, etc. However, "Bugs" (true bugs)
          are actually just one order of insects (Hemiptera). This page provides
          a summary of the main classes or groups of creepy-crawlies.
        </p>
      </section>
    </header>
    <main>
      <section id="beetles">
        <h2>🪲 Beetles (Coleoptera)</h2>

        <figure>
          <img
            src="https://mdn.github.io/shared-assets/images/examples/learn/crawlies/beetle.png"
            alt="A black six-legged beetle with a shield-shaped body and long antennae"
            width="250"
            height="180" />
          <figcaption>A shiny, black beetle.</figcaption>
        </figure>

        <p>
          Beetles make up the largest order of insects, with more than 350,000
          known species. They are recognized by their hardened forewings
          (elytra) that cover and protect the delicate hindwings and abdomen.
          This feature gives them a tough, armored look and helps them survive
          in many environments, from forests to deserts. Beetles can vary
          greatly in size, color, and habits, ranging from tiny grain beetles to
          massive stag beetles with impressive jaws.
        </p>
        <p>
          Many beetles play important ecological roles. Some, like ladybugs, are
          beneficial predators that feed on crop pests such as aphids. Others,
          such as dung beetles, recycle nutrients by breaking down animal waste.
          However, certain species like the Colorado potato beetle or Japanese
          beetle are major agricultural pests. Their diversity and adaptability
          make beetles one of the most successful groups of insects on Earth.
        </p>

        <p class="copyright">
          Image by URSchmidt - Own work, CC BY-SA 4.0,
          <a href="https://commons.wikimedia.org/w/index.php?curid=70137401"
            >https://commons.wikimedia.org/w/index.php?curid=70137401</a
          >.
        </p>
      </section>
      <section id="true_bugs">
        <h2>🪳 True Bugs (Hemiptera)</h2>

        <figure>
          <img
            src="https://mdn.github.io/shared-assets/images/examples/learn/crawlies/true_bug.jpg"
            alt="A green, six-legged beetle with fairly long antennae and stripy markings"
            width="250"
            height="180" />
          <figcaption>A green stripey bug.</figcaption>
        </figure>

        <p>
          True bugs include a wide range of insects such as stink bugs, cicadas,
          aphids, and water striders. Unlike beetles, their forewings are partly
          hardened and partly membranous, and they possess distinctive
          piercing-sucking mouthparts. These mouthparts are adapted for feeding
          on plant sap, blood, or other insects. Many true bugs have scent
          glands that produce strong odors as a defense mechanism, which is why
          some are called "stink bugs."
        </p>

        <p>
          True bugs are found worldwide and occupy a variety of habitats,
          including plants, soil, and water. While some species are harmless or
          even beneficial predators, others are destructive agricultural pests
          that weaken plants by draining their sap. Certain bugs, like bed bugs
          and kissing bugs, can also affect humans directly by biting or
          transmitting diseases.
        </p>

        <p class="copyright">
          Image created by user B. Schoenmakers at Waarneming.nl, a source of
          nature observations in the Netherlands. - This image is uploaded as
          image number 29046158 at Waarneming.nl, a source of nature
          observations in the Netherlands.This tag does not indicate the
          copyright status of the attached work. A normal copyright tag is
          still required. See Commons:Licensing for more information. This
          site now requires authentication, however, the same image and
          copyright information is also available via
          <a href="https://world.observation.org/foto/view/29046158"
            >https://world.observation.org/foto/view/29046158</a
          >
          since it uses the same data, CC BY 3.0,
          <a href="https://commons.wikimedia.org/w/index.php?curid=92410673"
            >https://commons.wikimedia.org/w/index.php?curid=92410673</a
          >.
        </p>
      </section>
      <section id="butterflies_moths">
        <h2>🦋 Butterflies & Moths (Lepidoptera)</h2>

        <figure>
          <img
            src="https://mdn.github.io/shared-assets/images/examples/learn/crawlies/butterfly.jpg"
            alt="A colorful butterfly resting on a flower"
            width="250"
            height="180" />
          <figcaption>A shimmering patterned butterfly.</figcaption>
        </figure>

        <p>
          Butterflies and moths are some of the most recognizable insects
          thanks to their large, often colorful wings covered in tiny scales.
          These scales give their wings shimmering, patterned appearances and
          are one of the defining traits of this group. Butterflies are
          usually active by day, while moths are mostly nocturnal, though
          there are exceptions. Both undergo complete metamorphosis, with a
          dramatic transformation from caterpillar to winged adult.
        </p>

        <p>
          As caterpillars, they primarily feed on leaves, sometimes causing
          damage to crops and plants. As adults, butterflies and many moths
          are important pollinators, transferring pollen as they sip nectar
          from flowers. They are also ecologically vital as food sources for
          birds, bats, and other animals. Their beauty and ecological
          importance make them a favorite group for nature enthusiasts and
          scientists alike.
        </p>

        <p class="copyright">
          Image by Didier Descouens - Own work, CC BY-SA 4.0,
          <a href="https://commons.wikimedia.org/w/index.php?curid=19303857"
            >https://commons.wikimedia.org/w/index.php?curid=19303857</a
          >.
        </p>
      </section>
      <section id="flies_mosquitos">
        <h2>🦟 Flies & Mosquitoes (Diptera)</h2>

        <figure>
          <img
            src="https://mdn.github.io/shared-assets/images/examples/learn/crawlies/fly.jpg"
            alt="A fly perched on a green leaf with clear wings"
            width="250"
            height="180" />
          <figcaption>An agile flying insect.</figcaption>
        </figure>

        <p>
          Flies and mosquitoes belong to the order Diptera, meaning "two
          wings." Unlike most other insects, they have only one functional
          pair of wings; the hind pair has evolved into tiny balancing organs
          called halteres. This adaptation gives them incredible agility in
          flight. Their mouthparts vary widely: some species have sponging
          mouthparts (like houseflies), while others have piercing-sucking
          ones (like mosquitoes).
        </p>

        <p>
          These insects are among the most ecologically and medically
          significant. Many flies are decomposers, helping break down waste
          and recycle nutrients. Mosquitoes, however, are infamous as disease
          vectors, spreading malaria, dengue, and other illnesses. Despite
          their negative reputation, flies and mosquitoes are essential in
          ecosystems, serving as pollinators and as a major food source for
          many animals.
        </p>

        <p class="copyright">
          Image created by user Dick Belgers at Waarneming.nl, a source of
          nature observations in the Netherlands. - This image is uploaded as
          image number 5105758 at Waarneming.nl, a source of nature
          observations in the Netherlands.This tag does not indicate the
          copyright status of the attached work. A normal copyright tag is
          still required. See Commons:Licensing for more information. CC BY
          3.0,
          <a href="https://commons.wikimedia.org/w/index.php?curid=27659589"
            >https://commons.wikimedia.org/w/index.php?curid=27659589</a
          >.
        </p>
      </section>
      <section id="bees_wasps_ants">
        <h2>🐝 Bees, Wasps, Ants (Hymenoptera)</h2>

        <figure>
          <img
            src="https://mdn.github.io/shared-assets/images/examples/learn/crawlies/bee.jpg"
            alt="A honeybee gathering pollen on a bright yellow flower"
            width="250"
            height="180" />
          <figcaption>A hardworking pollinator.</figcaption>
        </figure>

        <p>
          Bees, wasps, and ants are a diverse group known for their complex
          behaviors and social structures. Many species live in colonies with
          distinct roles for workers, queens, and males. Bees are especially
          famous for pollination, producing honey, and communicating with
          each other through dances. Wasps are often predators or
          parasitoids, while ants are skilled builders and cooperative
          foragers.
        </p>

        <p>
          This group has a huge ecological impact. Bees and wasps contribute
          to pollination, supporting food crops and wild plants. Some wasps
          help control pest populations by preying on or parasitizing other
          insects. Ants are critical soil engineers, aerating the ground and
          recycling nutrients. While stings and aggressive behaviors make
          some species feared, they are vital players in natural and
          agricultural systems.
        </p>

        <p class="copyright">
          Image by Trounce - Own work, CC BY-SA 2.5,
          <a href="https://commons.wikimedia.org/w/index.php?curid=1997709"
            >https://commons.wikimedia.org/w/index.php?curid=1997709</a
          >.
        </p>
      </section>
      <section id="spiders">
        <h2>🕷️ Spiders (Araneae)</h2>

        <figure>
          <img
            src="https://mdn.github.io/shared-assets/images/examples/learn/crawlies/spider.jpg"
            alt="An eight-legged spider waiting in the center of its web"
            width="250"
            height="180" />
          <figcaption>An eight-legged predator.</figcaption>
        </figure>

        <p>
          Spiders are arachnids, not insects, and are easily distinguished by
          their eight legs and lack of antennae. Almost all spiders are
          predators, using venom and silk to capture prey. Many build
          intricate webs to trap insects, while others are active hunters
          that chase or ambush their food. Their silk is an incredibly strong
          and versatile material, used for webs, egg sacs, or safety lines.
        </p>

        <p>
          Spiders are found in nearly every habitat on Earth, from deserts to
          caves to homes. While some people fear them, very few species pose
          a danger to humans. In fact, spiders are highly beneficial because
          they help control insect populations, including pests. They play a
          crucial role in balancing ecosystems, making them one of the most
          important non-insect "bugs" people commonly encounter.
        </p>

        <p class="copyright">
          Image by AJC ajcann.wordpress.com from UK, CC BY-SA 2.0
          <a href="https://creativecommons.org/licenses/by-sa/2.0"
            >https://creativecommons.org/licenses/by-sa/2.0</a
          >, via Wikimedia Commons.
        </p>
      </section>
    </main>
  </body>
</html>
```

---

---

# 19. Tablo temelleri

**HTML** > **Table basics** (HTML table basics) | English (US)

Bu makale, satırlar (rows), hücreler (cells), başlıklar (headings), hücrelerin birden fazla sütun ve satıra yayılması (spanning multiple columns and rows) ve bir sütundaki tüm hücrelerin tek bir öğeymiş gibi stillendirilmesi gibi temel konuları ele alarak HTML tablolarına giriş yapmanızı sağlar.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | [Basic HTML syntax](#1-basic-html-syntax) bölümünde ele alındığı gibi temel HTML aşinalığı. |
| **Learning outcomes (Öğrenim çıktıları):** | • Tablolar ne içindir? — Tablosal verileri (tabular data) yapılandırmak.<br>• Tablolar ne için değildir? — Sayfa düzeni (layout) veya *başka herhangi bir şey* için değildir.<br>• Temel tablo sözdizimi — `<table>`, `<tr>` ve `<td>`.<br>• `<th>` ile tablo başlıklarını tanımlama.<br>• `colspan` ve `rowspan` ile birden çok sütun ve satıra yayılma.<br>• `<colgroup>` ve `<col>` ile sütunları gruplama. |

---

## Tablo nedir?

Tablo; satırlar ve sütunlardan oluşan yapılandırılmış bir veri kümesidir (**tablosal veri / tabular data**). Bir tablo, farklı veri türleri arasındaki bağlantıyı gösteren değerleri hızlı ve kolay bir şekilde aramanıza olanak tanır; örneğin bir kişi ile yaşı, haftanın bir günü veya yerel bir yüzme havuzunun saat tarifesi.

Tablolar insan toplumunda çok yaygın olarak kullanılır ve uzun süredir hayatımızdadır; 1800 yılına ait bu ABD Nüfus Sayımı (US Census) belgesinin de kanıtladığı gibi:

Tabloların bu kadar yaygın kullanılmasının nedeni **kolay anlaşılır** olmalarıdır. Bilgiyi satır ve sütun başlıkları arasındaki görsel çağrışımlar kurarak okuruz. Örneğin aşağıdaki tabloya bakıldığında, Ghent'te Ağustos 2016'da kaç yüzük (rings) satıldığını bulmak yalnızca birkaç saniye sürer:

| Clothes (Giysiler) | Clothes (Giysiler) | Accessories (Aksesuarlar) | Accessories (Aksesuarlar) |
| :--- | :--- | :--- | :--- |
| **Trousers** | **Skirts** | **Dresses** | **Bracelets** | **Rings** |
| 120 | 42 | 87 | 12 | 24 |

### Bir tablo nasıl çalışır?

Bir tablonun temel amacı tablosal verileri sunmaktır. Peki tablosal veri nedir? Tablosal veri, satırlar ve sütunlardan oluşan bir ızgara (grid) içinde temsil edilen veridir. Bu veride satırlar bir kaydı (record), sütunlar ise o kayda ait belirli bir özelliği (attribute) temsil eder.

### Tablo stillendirme

Tablolara stil uygulamak (arka plan renkleri, kenarlıklar, yazı tipleri, hizalamalar) CSS kullanılarak yapılır. Varsayılan olarak HTML tabloları oldukça sade ve kenarlıksız görünebilir. CSS ile tabloları görsel olarak çekici, net ve kolay okunur hale getirebilirsiniz.

### HTML tablolarından ne zaman kaçınmalısınız?

HTML tabloları **yalnızca tablosal veriler için kullanılmalıdır**. Geçmişte web tasarımcıları web sayfalarının genel düzenini (örneğin üstbilgi, kenar çubuğu, ana içerik alanı) oluşturmak için tabloları kullanırlardı. Bu **kötü bir uygulamadır** ve kesinlikle kaçınılmalıdır çünkü:

1. **Erişilebilirlik sorunları yaratır:** Ekran okuyucu kullanan görme engelli kullanıcılar için sayfa düzeni tabloları kafa karıştırıcıdır; ekran okuyucu satır ve sütunları okumaya çalışır ve içerik akışı bozulur.
2. **Kod karmaşası (Tag soup):** Sayfa düzeni için tablolar kullanmak son derece karmaşık, iç içe geçmiş `<table>`, `<tr>`, `<td>` etiket yığınlarına yol açar.
3. **Duyarlılık (Responsiveness) eksikliği:** Tablolar esnek değildir; mobil cihaz ekranlarına uyum sağlamakta zorlanırlar. Modern web geliştirmede sayfa düzenleri için **CSS Flexbox** ve **CSS Grid** kullanılmalıdır.

---

## İlk tablonuzu oluşturma

Teoriden sonra pratik bir örneğe geçelim. Burada basit bir tablo inşa edeceksiniz.

1. Her tablo **`<table></table>`** etiketleri ile çevrelenir.
2. Bir tablonun içindeki en küçük kapsayıcı bir tablo hücresidir ve bu hücre **`<td>`** elementi ("td" = "table data") ile oluşturulur.
3. Hücrelerin doğrudan `<table>` içine yerleştirilmesi geçerli değildir. Hücreler satırlar halinde düzenlenmelidir. Bir tablo satırı **`<tr>`** elementi ("tr" = "table row") ile oluşturulur.

Örnek bir satır ve hücre yapısı:

```html
<table>
  <tr>
    <td>Hi, I'm your first cell.</td>
    <td>I'm your second cell.</td>
    <td>I'm your third cell.</td>
    <td>I'm your fourth cell.</td>
  </tr>
</table>
```

Birden fazla satır oluşturmak için yeni `<tr>` blokları eklersiniz:

```html
<table>
  <tr>
    <td>Hi, I'm your first cell.</td>
    <td>I'm your second cell.</td>
    <td>I'm your third cell.</td>
    <td>I'm your fourth cell.</td>
  </tr>
  <tr>
    <td>Second row, first cell.</td>
    <td>Second row, second cell.</td>
    <td>Second row, third cell.</td>
    <td>Second row, fourth cell.</td>
  </tr>
</table>
```

---

## <th> elementleri ile başlık ekleme

Tablo başlıkları (`<th>` — "table header"), bir satırın veya sütunun başında yer alan ve o satır ya da sütunun ne tür veri içerdiğini tanımlayan özel hücrelerdir.

Başlık hücrelerini tanımlamak için `<td>` yerine **`<th>`** kullanılır:

```html
<table>
  <tr>
    <td>&nbsp;</td>
    <th>Knocky</th>
    <th>Flor</th>
    <th>Ella</th>
    <th>Juan</th>
  </tr>
  <tr>
    <th>Breed</th>
    <td>Jack Russell</td>
    <td>Poodle</td>
    <td>Streetdog</td>
    <td>Cocker Spaniel</td>
  </tr>
  <tr>
    <th>Age</th>
    <td>16</td>
    <td>9</td>
    <td>10</td>
    <td>5</td>
  </tr>
  <tr>
    <th>Owner</th>
    <td>Jessica</td>
    <td>Effie</td>
    <td>Michael</td>
    <td>Albert</td>
  </tr>
  <tr>
    <th>Eating Habits</th>
    <td>Eats everyone's leftovers</td>
    <td>Nibbles at food</td>
    <td>Hearty eater</td>
    <td>Will eat bite-sized scraps</td>
  </tr>
</table>
```

### Başlıklar neden faydalıdır?

- **Görsel ayrım:** Tarayıcılar varsayılan olarak `<th>` elementlerini kalın (bold) ve ortalanmış olarak görüntüler, bu da veriler ile başlıkların görsel olarak kolayca ayırt edilmesini sağlar.
- **Erişilebilirlik (Accessibility):** Ekran okuyucular başlıkları tanır ve her bir veri hücresini okurken ilişkili olduğu başlığı seslendirir. Bu, görme engelli bir kullanıcının tablodaki bir sayının veya metnin ne anlama geldiğini kavramasını mümkün kılar.

---

## Hücrelerin birden fazla satır ve sütuna yayılmasına izin verme

Bazen bir hücrenin birden fazla sütuna veya birden fazla satıra yayılmasını isteriz. Bunun için iki özel nitelik kullanılır:

- **`colspan` (Column span):** Bir hücrenin kaç sütun genişliğinde olacağını belirtir.
- **`rowspan` (Row span):** Bir hücrenin kaç satır yüksekliğinde olacağını belirtir.

### `colspan` örneği

Aşağıdaki örnekte `Animals` başlığı iki sütun boyunca uzanır:

```html
<table>
  <tr>
    <th colspan="2">Animals</th>
  </tr>
  <tr>
    <th colspan="2">Hippopotamus</th>
  </tr>
  <tr>
    <th rowspan="2">Horse</th>
    <td>Mare</td>
  </tr>
  <tr>
    <td>Stallion</td>
  </tr>
  <tr>
    <th colspan="2">Crocodile</th>
  </tr>
  <tr>
    <th rowspan="2">Chicken</th>
    <td>Rooster</td>
  </tr>
  <tr>
    <td>Hen</td>
  </tr>
</table>
```

> [!NOTE]
> Bir hücre `colspan="2"` aldığında, o satırdaki bir sonraki hücrenin kaplayacağı alanı devralır; bu nedenle o satırdan bir hücre çıkarmanız gerekir. Benzer şekilde `rowspan="2"` alan bir hücre altındaki satırın alanını kaplar, bu yüzden alttaki satırda bir hücre eksik tanımlanmalıdır.

---

## `<colgroup>` ve `<col>` ile sütunları gruplama

HTML'de tablonun tüm bir sütununu tek bir birim olarak hedeflemek ve stillendirmek için **`<colgroup>`** ve **`<col>`** elementleri kullanılır.

Normal şartlarda HTML hücreleri satır bazlı tanımlandığından (`<tr>`), belirli bir sütundaki tüm hücrelere örneğin arka plan rengi vermek zahmetlidir. `<colgroup>` ve `<col>` bu sorunu çözer.

`<colgroup>` elementi açılış `<table>` etiketinin hemen ardına yerleştirilir:

```html
<table>
  <colgroup>
    <col />
    <col style="background-color: #0f0" />
    <col style="background-color: #f00" />
  </colgroup>
  <tr>
    <th>Data 1</th>
    <th>Data 2</th>
    <th>Data 3</th>
  </tr>
  <tr>
    <td>Cal 1</td>
    <td>Cal 2</td>
    <td>Cal 3</td>
  </tr>
</table>
```

`span` niteliği ile bir `<col>` elementinin birden fazla sütuna uygulanmasını sağlayabilirsiniz:

```html
<colgroup>
  <col style="background-color: #97DB9A" />
  <col span="2" />
  <col style="background-color: #DCC48E" />
  <col style="border: 2px solid #C1437A" />
</colgroup>
```

---

## Tablo kavramlarının etkileşimli özeti

Tablolar; yapılandırılmış verileri net bir ızgara düzeninde sunarak insan zihninin satır ve sütun kesişimlerini zahmetsizce ilişkilendirmesini sağlar. Temel yapı taşları `<table>`, `<tr>`, `<th>` ve `<td>` etiketleridir; karmaşık veri düzenleri için `colspan`, `rowspan` ve sütun stillendirmesi için `<colgroup>` / `<col>` kullanılır.

## Özet

Bu makalede HTML tablolarının temellerini tamamladık. Satırlar, hücreler, başlıklar, hücre yayılmaları (`colspan`/`rowspan`) ve sütun gruplama tekniklerini öğrendiniz. Bir sonraki makalede, tabloları görme engelli kullanıcılar ve ekran okuyucular için nasıl daha erişilebilir hale getireceğimizi inceleyeceğiz.

---

# 20. Tablo erişilebilirliği

**HTML** > **Table accessibility** (HTML table accessibility) | English (US)

Bu makalede, HTML tablolarını ekran okuyucu kullananlar da dahil olmak üzere tüm kullanıcılar için tamamen erişilebilir hale getirmeye yönelik gelişmiş yapısal elementler (`<caption>`, `<thead>`, `<tbody>`, `<tfoot>`) ile `scope`, `id` ve `headers` nitelikleri ele alınmaktadır.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | [Table basics](#19-table-basics) bölümünde ele alındığı gibi HTML tablolarının temelleri. |
| **Learning outcomes (Öğrenim çıktıları):** | • Görme engelli kullanıcıların tablolarda nasıl gezindiğini anlama.<br>• `<caption>` ile tabloya başlık/açıklama ekleme.<br>• `<thead>`, `<tbody>` ve `<tfoot>` ile tablo bölümlerini yapılandırma.<br>• `<th>` üzerinde `scope` niteliğini doğru kullanma.<br>• Karmaşık tablolarda `id` ve `headers` nitelikleri ile açık ilişkilendirmeler kurma. |

---

## Özet: Görme engelli kullanıcılar için tablolar

Gören kullanıcılar bir tabloya baktıklarında satır ve sütun başlıkları ile veri hücreleri arasındaki ilişkiyi anında görsel olarak kavrarlar. Ancak ekran okuyucu (screen reader) kullanan bir kullanıcı tablonun tamamını aynı anda göremez; hücreleri teker teker, sırayla dinler.

Erişilebilirlik özellikleri eklenmemiş bir tabloda, ekran okuyucu kullanıcıya yalnızca "120", "42", "24" gibi sayılar okur. Kullanıcı bu sayıların hangi ürüne, hangi aya veya hangi şehre ait olduğunu bilemez.

İşte bu yüzden tablo başlıklarını doğru etiketlemek ve veri hücreleri ile olan ilişkilerini netleştirmek hayati önem taşır.

---

## <caption> ile tablonuza başlık ekleme

Tablonuza bir başlık veya açıklayıcı bir etiket vermek için **`<caption>`** elementi kullanılır. Bu element, açılış `<table>` etiketinin hemen altına yerleştirilmelidir:

```html
<table>
  <caption>
    Dinosaurs in the Jurassic period
  </caption>
  <tr>
    <th>Name</th>
    <th>Diet</th>
    <th>Period</th>
  </tr>
  <tr>
    <td>Brachiosaurus</td>
    <td>Herbivore</td>
    <td>Late Jurassic</td>
  </tr>
</table>
```

`<caption>` elementi bir tablonun ne hakkında olduğunu özetler. Ekran okuyucu kullanıcıları sayfadaki bir tabloya ulaştıklarında ilk olarak başlığı duyarlar ve tablonun içeriğini okumaya devam edip etmeyeceklerine bu sayede karar verebilirler.

---

## <thead>, <tbody> ve <tfoot> ile yapı kazandırma

Tablolar büyüdükçe ve karmaşıklaştıkça, onları mantıksal bölümlere ayırmak hem kod düzeni hem de CSS/yazdırma stilleri açısından büyük avantaj sağlar:

- **`<thead>` (Table Head):** Tablonun başlık satırını veya satırlarını sarmalar (genellikle sütun başlıklarını içeren ilk satır). Varsa `<colgroup>`/`<col>` elementlerinin hemen ardından gelmelidir.
- **`<tbody>` (Table Body):** Tablonun ana veri içeriğini sarmalar. `<thead>` elementinden sonra gelir.
- **`<tfoot>` (Table Foot):** Tablonun alt bilgi/özet satırını sarmalar (örneğin toplam değerler, genel toplamlar). `<tbody>` elementinden sonra gelir.

### Harcama tablosu örneği

```html
<table>
  <caption>How I spent my money this month</caption>
  <thead>
    <tr>
      <th>Purchase</th>
      <th>Location</th>
      <th>Date</th>
      <th>Evaluation</th>
      <th>Cost (€)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Haircut</td>
      <td>Hairdresser</td>
      <td>12/09</td>
      <td>Great idea</td>
      <td>30</td>
    </tr>
    <tr>
      <td>Lasagna</td>
      <td>Restaurant</td>
      <td>12/09</td>
      <td>Regrets</td>
      <td>18</td>
    </tr>
    <tr>
      <td>Shoes</td>
      <td>Shoeshop</td>
      <td>13/09</td>
      <td>Big regrets</td>
      <td>65</td>
    </tr>
    <tr>
      <td>Pancake mix</td>
      <td>Supermarket</td>
      <td>16/09</td>
      <td>Great idea</td>
      <td>3</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th colspan="4">SUM</th>
      <td>116</td>
    </tr>
  </tfoot>
</table>
```

> [!NOTE]
> `<thead>`, `<tbody>` ve `<tfoot>` elementleri doğrudan tarayıcıda görsel bir değişiklik yapmaz; ancak CSS ile başlık ve altbilgileri sabitlemek (sticky headers) veya yazdırma çıktısında her sayfada tablo başlığının yinelenmesini sağlamak için standarttır.

---

## `scope` niteliği

**`scope`** niteliği `<th>` elementine eklenerek, o başlığın hangi hücrelerin başlığı olduğunu ekran okuyuculara açıkça bildirir. Olası değerleri şunlardır:

- **`col`:** Başlığın bulunduğu sütundaki tüm hücreler için geçerli olduğunu belirtir.
- **`row`:** Başlığın bulunduğu satırdaki tüm hücreler için geçerli olduğunu belirtir.
- **`colgroup`:** Bir sütun grubundaki tüm sütunlar için başlık olduğunu belirtir (birden fazla sütuna yayılan başlıklar için).
- **`rowgroup`:** Bir satır grubundaki tüm satırlar için başlık olduğunu belirtir (birden fazla satıra yayılan başlıklar için).

Örnek kullanım:

```html
<thead>
  <tr>
    <th scope="col">Purchase</th>
    <th scope="col">Location</th>
    <th scope="col">Date</th>
    <th scope="col">Evaluation</th>
    <th scope="col">Cost (€)</th>
  </tr>
</thead>
<tbody>
  <tr>
    <th scope="row">Haircut</th>
    <td>Hairdresser</td>
    <td>12/09</td>
    <td>Great idea</td>
    <td>30</td>
  </tr>
</tbody>
```

Bu sayede ekran okuyucu `Hairdresser` hücresine geldiğinde şunu seslendirebilir: *"Location, Haircut, Hairdresser"*. Kullanıcı verinin hangi başlık altında olduğunu hiçbir şüpheye yer bırakmadan anlar.

---

## `id` ve `headers` nitelikleri

Çok karmaşık veya çok katmanlı tablolarda `scope` niteliği yetersiz kalabilir. Bu gibi durumlarda **`id`** ve **`headers`** nitelikleri kullanılarak veri hücreleri ile başlık hücreleri arasında doğrudan, birebir bağlantılar kurulur:

1. Her `<th>` elementine benzersiz bir `id` atanır.
2. Her `<td>` elementine bir `headers` niteliği verilir ve bu niteliğe, o hücreyle ilişkili tüm `<th>` elementlerinin `id` değerleri boşluklarla ayrılarak yazılır.

Örnek:

```html
<table>
  <caption>Items Sold August 2016</caption>
  <thead>
    <tr>
      <td colspan="2" rowspan="2"></td>
      <th id="clothes" colspan="3">Clothes</th>
      <th id="accessories" colspan="2">Accessories</th>
    </tr>
    <tr>
      <th id="trousers" headers="clothes">Trousers</th>
      <th id="skirts" headers="clothes">Skirts</th>
      <th id="dresses" headers="clothes">Dresses</th>
      <th id="bracelets" headers="accessories">Bracelets</th>
      <th id="rings" headers="accessories">Rings</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th id="belgium" rowspan="3">Belgium</th>
      <th id="antwerp" headers="belgium">Antwerp</th>
      <td headers="clothes trousers belgium antwerp">56</td>
      <td headers="clothes skirts belgium antwerp">22</td>
      <td headers="clothes dresses belgium antwerp">43</td>
      <td headers="accessories bracelets belgium antwerp">72</td>
      <td headers="accessories rings belgium antwerp">23</td>
    </tr>
  </tbody>
</table>
```

---

## Özet

Bu makalede HTML tablolarını erişilebilir kılmanın yollarını öğrendiniz:
- `<caption>` ile tabloya açıklayıcı başlık sağlamak,
- `<thead>`, `<tbody>` ve `<tfoot>` ile yapısal bölümler oluşturmak,
- `scope` niteliğiyle sütun ve satır başlıklarını netleştirmek,
- Karmaşık tablolarda `id` ve `headers` nitelikleriyle veri ve başlık ilişkisini tam olarak tanımlamak.

---

# 21. Uygulama Görevi: Gezegen veri tablosu

**HTML** > **Challenge: Planet data table** (Challenge: Structuring a planet data table) | English (US)

Bu meydan okumada, güneş sistemimizdeki gezegenlere ilişkin ham veriler sunulmaktadır. Göreviniz, bu verileri erişilebilir, anlamsal açıdan zengin ve tam yapılandırılmış bir HTML tablosu haline getirmektir.

---

## Başlangıç noktası

1. Bilgisayarınızda `planet-data-table` adında yeni bir klasör oluşturun.
2. Klasörünüzün içinde `index.html` adlı bir dosya oluşturun ve aşağıdaki HTML iskeletini kaydedin:

```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>Planet data table</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
  </head>
  <body>
    <h1>Planet data table</h1>
  </body>
</html>
```

3. Klasörünüzün içinde `style.css` adlı bir dosya oluşturun ve aşağıdaki CSS kodlarını içine yapıştırın:

```css
html {
  font-family: sans-serif;
}

table {
  border-collapse: collapse;
  border: 2px solid rgb(200 200 200);
  letter-spacing: 1px;
  font-size: 0.8rem;
}

td,
th {
  border: 1px solid rgb(190 190 190);
  padding: 10px 20px;
}

th {
  background-color: rgb(235 235 235);
}

td {
  text-align: center;
}

tr:nth-child(even) td {
  background-color: rgb(250 250 250);
}

tr:nth-child(odd) td {
  background-color: rgb(245 245 245);
}

caption {
  padding: 10px;
}
```

4. Tabloya dönüştürmeniz gereken ham veri aşağıda verilmiştir:

```text
Data about the planets in our solar system (Planetary facts taken from NASA's Planetary Fact Sheet - Metric).

Name, Mass (10^24kg), Diameter (km), Density (kg/m^3), Gravity (m/s^2), Length of day (hours), Distance from Sun (10^6km), Mean temp (°C), Number of moons, Notes

Terrestrial planets
Mercury, 0.330, 4879, 5427, 3.7, 4222.6, 57.9, 167, 0, Closest to the Sun
Venus, 4.87, 12104, 5243, 8.9, 2802.0, 108.2, 464, 0, 
Earth, 5.97, 12756, 5514, 9.8, 24.0, 149.6, 15, 1, Our world
Mars, 0.642, 6792, 3933, 3.7, 24.7, 227.9, -65, 2, The red planet

Jovian planets
Gas giants
Jupiter, 1898, 142984, 1326, 23.1, 9.9, 778.6, -110, 67, The largest planet
Saturn, 568, 120536, 687, 9.0, 10.7, 1433.5, -140, 62, 

Ice giants
Uranus, 86.8, 51118, 1271, 8.7, 17.2, 2872.5, -195, 27, 
Neptune, 102, 49528, 1638, 11.0, 16.1, 4495.1, -200, 14, 

Dwarf planets
Pluto, 0.0146, 2370, 2095, 0.7, 153.3, 5906.4, -225, 5, Declassified as a planet in 2006, but this <a href="https://www.usatoday.com/story/tech/2014/10/02/pluto-planet-solar-system/16578957/">remains controversial</a>.
```

---

## Proje özeti ve yönergeler

Bir okulda çalıştığınızı ve öğrencilerinizin güneş sistemindeki gezegenleri incelediğini hayal edin. Öğrencilerinize gerçekleri ve rakamları kolayca arayabilecekleri net bir kaynak sunmak istiyorsunuz. Bir HTML tablosu bunun için idealdir:

1. Tablonuzu bir dış `<table>`, bir tablo başlığı `<thead>` ve bir tablo gövdesi `<tbody>` ile başlatın. Bu örnekte tablo altbilgisine (`<tfoot>`) gerek yoktur.
2. Sağlanan tablo açıklamasını (`<caption>`) ekleyin: `Data about the planets in our solar system (Planetary facts taken from NASA's Planetary Fact Sheet - Metric).`
3. `<thead>` içine tüm sütun başlıklarını içeren bir satır ekleyin.
4. İlk başlık hücresi boş olmalı ve 2 sütuna yayılmalıdır (`colspan="2"`).
5. Tüm gezegen verisi satırlarını `<tbody>` içine oluşturun. Gezegen adlarını ve grup adlarını semantik olarak `<th>` başlık hücreleri yapmayı unutmayın.
6. Gezegen grupları için satır başlıklarını (`Terrestrial planets`, `Jovian planets`, `Gas giants`, `Ice giants`, `Dwarf planets`) doğru sayıda satır ve sütuna yayılacak şekilde (`rowspan` ve `colspan`) yapılandırın:
   - `Terrestrial planets`: 4 satıra yayılır (`rowspan="4"`), 1 sütun kaplar.
   - `Jovian planets`: 4 satıra yayılır (`rowspan="4"`).
   - `Gas giants`: 2 satıra yayılır (`rowspan="2"`).
   - `Ice giants`: 2 satıra yayılır (`rowspan="2"`).
   - `Dwarf planets`: 1 satır kaplar, yanındaki gezegen adı sütunuyla birleşmek üzere `colspan="2"` alabilir.
7. Tüm `<th>` elementlerine uygun `scope` niteliklerini (`col`, `row`, `colgroup`, `rowgroup`) ekleyin.

---

## İpuçları ve püf noktaları

- Başlık satırının ilk hücresi boştur ve iki sütuna yayılır: `<td colspan="2">&nbsp;</td>` veya `<th colspan="2">&nbsp;</th>`.
- Gezegen grupları solda yer aldığı için her grup hücresinin kapsadığı gezegen sayısına göre `rowspan` değerini dikkatlice sayın.
- Başlıkları ilişkilendirmede `scope` niteliği bu tablo için en pratik ve temiz yöntemdir.

---

## Çözüm ve tam kod

<details>
<summary>Çözümü görmek için buraya tıklayın</summary>

Tamamlanmış `index.html` dosyanız şu şekilde görünmelidir:

```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>Planet data table</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
  </head>
  <body>
    <h1>Planet data table</h1>

    <table>
      <caption>
        Data about the planets in our solar system (Planetary facts taken from
        <a href="https://nssdc.gsfc.nasa.gov/planetary/factsheet/">NASA's Planetary Fact Sheet - Metric</a>).
      </caption>
      <colgroup>
        <col span="2" />
        <col style="border: 2px solid black" />
      </colgroup>
      <thead>
        <tr>
          <td colspan="2">&nbsp;</td>
          <th scope="col">Name</th>
          <th scope="col">Mass (10<sup>24</sup>kg)</th>
          <th scope="col">Diameter (km)</th>
          <th scope="col">Density (kg/m<sup>3</sup>)</th>
          <th scope="col">Gravity (m/s<sup>2</sup>)</th>
          <th scope="col">Length of day (hours)</th>
          <th scope="col">Distance from Sun (10<sup>6</sup>km)</th>
          <th scope="col">Mean temp (°C)</th>
          <th scope="col">Number of moons</th>
          <th scope="col">Notes</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th rowspan="4" colspan="2" scope="rowgroup">Terrestrial planets</th>
          <th scope="row">Mercury</th>
          <td>0.330</td>
          <td>4879</td>
          <td>5427</td>
          <td>3.7</td>
          <td>4222.6</td>
          <td>57.9</td>
          <td>167</td>
          <td>0</td>
          <td>Closest to the Sun</td>
        </tr>
        <tr>
          <th scope="row">Venus</th>
          <td>4.87</td>
          <td>12104</td>
          <td>5243</td>
          <td>8.9</td>
          <td>2802.0</td>
          <td>108.2</td>
          <td>464</td>
          <td>0</td>
          <td></td>
        </tr>
        <tr>
          <th scope="row">Earth</th>
          <td>5.97</td>
          <td>12756</td>
          <td>5514</td>
          <td>9.8</td>
          <td>24.0</td>
          <td>149.6</td>
          <td>15</td>
          <td>1</td>
          <td>Our world</td>
        </tr>
        <tr>
          <th scope="row">Mars</th>
          <td>0.642</td>
          <td>6792</td>
          <td>3933</td>
          <td>3.7</td>
          <td>24.7</td>
          <td>227.9</td>
          <td>-65</td>
          <td>2</td>
          <td>The red planet</td>
        </tr>
        <tr>
          <th rowspan="4" scope="rowgroup">Jovian planets</th>
          <th rowspan="2" scope="rowgroup">Gas giants</th>
          <th scope="row">Jupiter</th>
          <td>1898</td>
          <td>142984</td>
          <td>1326</td>
          <td>23.1</td>
          <td>9.9</td>
          <td>778.6</td>
          <td>-110</td>
          <td>67</td>
          <td>The largest planet</td>
        </tr>
        <tr>
          <th scope="row">Saturn</th>
          <td>568</td>
          <td>120536</td>
          <td>687</td>
          <td>9.0</td>
          <td>10.7</td>
          <td>1433.5</td>
          <td>-140</td>
          <td>62</td>
          <td></td>
        </tr>
        <tr>
          <th rowspan="2" scope="rowgroup">Ice giants</th>
          <th scope="row">Uranus</th>
          <td>86.8</td>
          <td>51118</td>
          <td>1271</td>
          <td>8.7</td>
          <td>17.2</td>
          <td>2872.5</td>
          <td>-195</td>
          <td>27</td>
          <td></td>
        </tr>
        <tr>
          <th scope="row">Neptune</th>
          <td>102</td>
          <td>49528</td>
          <td>1638</td>
          <td>11.0</td>
          <td>16.1</td>
          <td>4495.1</td>
          <td>-200</td>
          <td>14</td>
          <td></td>
        </tr>
        <tr>
          <th colspan="2" scope="row">Dwarf planets</th>
          <th scope="row">Pluto</th>
          <td>0.0146</td>
          <td>2370</td>
          <td>2095</td>
          <td>0.7</td>
          <td>153.3</td>
          <td>5906.4</td>
          <td>-225</td>
          <td>5</td>
          <td>Declassified as a planet in 2006, but this <a href="https://www.usatoday.com/story/tech/2014/10/02/pluto-planet-solar-system/16578957/">remains controversial</a>.</td>
        </tr>
      </tbody>
    </table>
  </body>
</html>
```

</details>

---

# 22. Formlar ve butonlar

**HTML** > **Forms and buttons** (Forms and buttons in HTML) | English (US)

HTML formları, web sitelerinin kullanıcılarla etkileşim kurmasının ve veri toplamasının temel yoludur. Bu makalede; form kontrolleri (`<input>`, `<textarea>`, `<select>`, `<button>`), bu kontrolleri etiketleme (`<label>`), form verilerini yapılandırma ve gönderme mekanizmaları ile temel istemci tarafı form doğrulaması (form validation) ayrıntılı olarak ele alınmaktadır.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | [Basic HTML syntax](#1-basic-html-syntax) bölümünde açıklandığı gibi temel HTML aşinalığı. |
| **Learning outcomes (Öğrenim çıktıları):** | • Formların ne olduğunu ve ne amaçla kullanıldığını anlama.<br>• Temel form elementleri: `<form>`, `<input>`, `<label>`, `<button>`.<br>• `<input>` elementinin yaygın türleri (`text`, `email`, `password`, `radio`, `checkbox` vb.).<br>• Diğer kontrol tipleri: çok satırlı metin alanları (`<textarea>`) ve açılır menüler (`<select>`, `<option>`).<br>• `<fieldset>` ve `<legend>` ile form kontrollerini gruplandırma.<br>• `required`, `minlength`, `maxlength` gibi niteliklerle temel form doğrulaması. |

---

## Kullanıcılarla etkileşim

Şimdiye kadar kursta kullanıcıların web ile etkileşim kurmasının birkaç yolunu gördünüz:
- **Bağlantılar (Links):** Aynı sayfada veya farklı sayfalarda farklı içerik bölümlerine gitmek için kullanılır.
- **`<video>` ve `<audio>`:** Medyayı oynatmak, duraklatmak ve ses düzeyini ayarlamak için tarayıcının yerleşik kontrollerini sunar.

Bununla birlikte, kullanıcıların sayfayla daha doğrudan etkileşime girmesi gereken pek çok senaryo vardır:
- Bir arama motorunda arama yapmak,
- Bir web sitesine giriş yapmak (login) veya kayıt olmak (register),
- Bir anketi doldurmak veya geri bildirim göndermek,
- Bir ürün satın almak veya kişiselleştirmek.

Bu tür zengin etkileşimlerin tümü **HTML Formları (HTML Forms)** ve **Düğmeler (Buttons)** aracılığıyla gerçekleştirilir.

---

## Butonlar (Düğmeler)

Web üzerinde düğmelerin iki ana kullanım alanı vardır. İlk olarak, bir kullanıcı arayüzü kontrolü oluştururken belirli bir işlevi (genellikle JavaScript ile) tetiklemek için kullanılırlar. En basit düğme şu kodla oluşturulur:

```html
<button>Press me</button>
```

Varsayılan olarak bir düğme tıklandığında tıklandığı hissini veren standart bir tarayıcı stiliyle işlenir. Düğmelerin içine metin veya simge yerleştirilebilir. İkinci ve çok kritik bir kullanım alanı ise **form verilerini bir sunucuya göndermek (submit etmek)** tir.

---

## Bir formun anatomisi

Temel bir form üç temel bileşenden oluşur:

1. **`<form>` elementi:** Diğer tüm form içeriğini saran dış kapsayıcıdır. `<form></form>` etiketleri içindeki herhangi bir form kontrolü aynı formun bir parçasıdır ve form gönderildiğinde verileri dahil edilir.
2. **`<label>` ve form kontrolü çiftleri:** Kullanıcıdan veri toplamak için kullanılan kontroller (çoğunlukla `<input>`) ve bu kontrollerin ne amaçla veri topladığını açıklayan metin etiketleri (`<label>`).
3. **Gönderme düğmesi (`<button type="submit">`):** Kullanıcının formu tamamladığında verileri göndermesini sağlayan düğme.

### `<form>` elementi

`<form>` elementi formun nasıl ve nereye gönderileceğini belirleyen iki temel niteliğe sahiptir:

- **`action`:** Form verilerinin gönderileceği sunucu tarafı işleyicinin (URL) adresidir.
- **`method`:** Verilerin hangi HTTP yöntemiyle gönderileceğini belirtir (genellikle verileri URL'ye ekleyen `GET` veya verileri istek gövdesinde güvenle taşıyan `POST`).

Örnek temel form:

```html
<form action="https://httpbin.org/post" method="post">
  <label for="name">Name:</label>
  <input type="text" id="name" name="user_name" required />

  <button type="submit">Submit</button>
</form>
```

#### Gönderilen verileri inceleme

Bir form gönderildiğinde, tarayıcı verileri **anahtar/değer çiftleri (key/value pairs)** olarak paketler:
- **Anahtar (Key):** Form kontrolünün `name` niteliğidir (örneğin `user_name`).
- **Değer (Value):** Kullanıcının alana girdiği metindir.

> [!IMPORTANT]
> Bir form kontrolünün verisinin sunucuya gönderilebilmesi için mutlaka bir **`name`** niteliğine sahip olması gerekir! `name` niteliği olmayan alanların verisi gönderilmez.

#### Formları yapılandırma

Form elementlerini düzenli tutmak için liste elementleri (`<ul>`, `<li>`) veya yapısal `<div>` kutuları kullanmak yaygın bir pratiktir:

```html
<form action="https://httpbin.org/post" method="post">
  <ul>
    <li>
      <label for="name">Name:</label>
      <input type="text" id="name" name="user_name" />
    </li>
    <li>
      <label for="mail">Email:</label>
      <input type="email" id="mail" name="user_email" />
    </li>
    <li class="button">
      <button type="submit">Send your message</button>
    </li>
  </ul>
</form>
```

### `<input>` elementleri

`<input>` en çok yönlü form elementidir. Ne tür bir veri toplayacağı **`type`** niteliği ile belirlenir:
- `type="text"`: Tek satırlı genel metin alanı.
- `type="password"`: Girilen karakterleri gizleyen (nokta veya yıldız olarak gösteren) şifre alanı.
- `type="email"`: E-posta adresi biçimini otomatik doğrulayan alan.
- `type="number"`: Sayısal giriş alanı.
- `type="tel"`: Telefon numarası alanı.
- `type="url"`: Web adresi (URL) alanı.

Önemli nitelikler:
- **`id`:** Giriş alanını `<label>` elementiyle eşleştirmek için kullanılan benzersiz kimlik.
- **`name`:** Form gönderildiğinde sunucuya gidecek veri anahtarı.
- **`value`:** Giriş alanının varsayılan veya geçerli değeri.
- **`required`:** Alanın boş bırakılamayacağını belirten boolean nitelik.
- **`placeholder`:** Alan boşken içinde görünen soluk ipucu metni.

### `<label>` elementleri

`<label>` elementi, görme engelli kullanıcıların ekran okuyucuları için form kontrollerini seslendirilmesini sağlar ve tıklanabilir alanı genişleterek fare veya dokunmatik ekran kullanıcılarına büyük kolaylık sunar.

İlişkilendirme iki şekilde yapılır:

1. **Açık ilişkilendirme (Explicit association - Tavsiye edilen):** `<label>` elementine `for` niteliği verilir ve bu değer, ilgili `<input>` elementinin `id` değeriyle eşleştirilir:
   ```html
   <label for="username">Username:</label>
   <input type="text" id="username" name="username" />
   ```
2. **Örtük ilişkilendirme (Implicit association):** `<input>` doğrudan `<label>` etiketinin içine sarılır:
   ```html
   <label>
     Username:
     <input type="text" name="username" />
   </label>
   ```

---

## Diğer kontrol tipleri

### Radyo düğmeleri

Kullanıcının önceden tanımlanmış bir seçenek kümesinden **yalnızca birini** seçmesini istediğinizde `type="radio"` kullanılır. Aynı gruptaki radyo düğmelerinin birbiriyle yarışması ve tek bir seçime izin vermesi için **aynı `name` niteliğini** paylaşmaları gerekir:

```html
<fieldset>
  <legend>Select your favorite pet</legend>
  <input type="radio" id="cat" name="pet" value="cat" checked />
  <label for="cat">Cat</label>

  <input type="radio" id="dog" name="pet" value="dog" />
  <label for="dog">Dog</label>

  <input type="radio" id="hamster" name="pet" value="hamster" />
  <label for="hamster">Hamster</label>
</fieldset>
```

> [!NOTE]
> `<fieldset>` elementi mantıksal olarak ilişkili bir form kontrolleri grubunu çevreler; `<legend>` elementi ise bu grubun başlığı veya açıklamasıdır.
> Sayfa yüklendiğinde bir seçeneğin seçili gelmesi için **`checked`** niteliği eklenir.

### Onay kutuları

Kullanıcının **sıfır, bir veya birden fazla** seçeneği bağımsız olarak seçmesine izin vermek istediğinizde `type="checkbox"` kullanılır:

```html
<fieldset>
  <legend>Choose your toppings</legend>
  <input type="checkbox" id="cheese" name="topping" value="cheese" checked />
  <label for="cheese">Extra cheese</label>

  <input type="checkbox" id="onion" name="topping" value="onion" />
  <label for="onion">Onion</label>

  <input type="checkbox" id="mushroom" name="topping" value="mushroom" />
  <label for="mushroom">Mushrooms</label>
</fieldset>
```

### Açılır menüler: `<select>` ve `<option>`

Açılır bir seçim menüsü oluşturmak için **`<select>`** ve içine yerleştirilen **`<option>`** etiketleri kullanılır:

```html
<label for="car-choice">Choose a car:</label>
<select id="car-choice" name="car">
  <option value="volvo">Volvo</option>
  <option value="saab">Saab</option>
  <option value="fiat" selected>Fiat</option>
  <option value="audi">Audi</option>
</select>
```

Seçenekleri mantıksal alt başlıklara bölmek için **`<optgroup>`** elementi kullanılır:

```html
<select id="food" name="food">
  <optgroup label="Mains">
    <option value="burger">Burger</option>
    <option value="pizza">Pizza</option>
  </optgroup>
  <optgroup label="Snacks">
    <option value="chips">Chips</option>
    <option value="salad">Salad</option>
  </optgroup>
</select>
```

### Çok satırlı metin alanları: `<textarea>`

Kullanıcının yorumlar, mesajlar veya uzun paragraflar yazmasına izin vermek için **`<textarea>`** elementi kullanılır. Bu element bir kapanış etiketine sahiptir (`</textarea>`):

```html
<label for="feedback">Your comments:</label>
<textarea id="feedback" name="feedback" rows="5" cols="30">
Please enter your comments here...
</textarea>
```

---

## Form doğrulaması

Tarayıcılar, kullanıcı bir formu göndermeye çalıştığında temel kuralları kontrol eden yerleşik istemci tarafı doğrulama mekanizmalarına sahiptir:
- **`required`:** Alanın doldurulmasını zorunlu kılar.
- **`minlength` ve `maxlength`:** Girilebilecek metnin minimum ve maksimum karakter uzunluğunu belirler.
- **`type="email"`:** Girilen metnin geçerli bir e-posta sözdizimine sahip olup olmadığını denetler.
- **`type="number"` (min, max):** Sayısal giriş için alt ve üst limitler koyar.

Geçersiz bir durumda tarayıcı formun gönderilmesini engeller ve kullanıcıya uygun bir hata mesajı balonu gösterir.

---

## Özet

Bu makalede HTML formlarının ve düğmelerinin yapısını öğrendiniz:
- Veri toplamak için `<form>`, `<input>`, `<label>`, `<textarea>`, `<select>` ve `<button>` elementlerinin nasıl kullanıldığını,
- `<fieldset>` ve `<legend>` ile kontrollerin nasıl mantıksal gruplara ayrıldığını,
- Temel erişilebilirlik gereksinimlerini ve istemci tarafı doğrulamayı kavradınız.

---

# 23. Test: Formlar ve butonlar

**HTML** > **Test: Forms and buttons** (Test your skills: Forms and buttons) | English (US)

Bu test sayfası, HTML formları ve düğmeleri hakkındaki bilginizi sınamak için 6 farklı pratik görev sunmaktadır.

---

## Görev 1: Giriş alanları ve gönderme butonu

Bu görev sizden kullanıcı kimliği (user ID) ve şifre (password) için iki `<input>` alanı oluşturmanızı ve bunları metin etiketleriyle semantik olarak ilişkilendirmenizi istemektedir.

### Yönergeler:
1. Kullanıcı kimliği ve şifre için uygun giriş alanları oluşturun.
2. Bunları sağlanan metin etiketleriyle (`<label>`) semantik olarak eşleştirin.
3. Kalan liste öğesinin içine metni "Log in" olan bir gönderme düğmesi ekleyin.

```html
<form>
  <h2>Log in to your account</h2>
  <ul>
    <li>
      <label for="user-id">User ID:</label>
      <input type="text" id="user-id" name="user_id" />
    </li>
    <li>
      <label for="pwd">Password:</label>
      <input type="password" id="pwd" name="password" />
    </li>
    <li>
      <button type="submit">Log in</button>
    </li>
  </ul>
</form>
```

---

## Görev 2: Radyo düğmeleri ve onay kutuları

Bu görev çalışan radyo düğmeleri ve onay kutuları oluşturmanızı gerektirir.

### Yönergeler:
1. İlk `<fieldset>` içeriğini bir radyo düğmesi kümesine dönüştürün; her biri için uygun `value` belirleyin ve aynı `name` niteliğini paylaşmalarını sağlayın.
2. Sayfa yüklendiğinde ilk radyo düğmesinin seçili olmasını sağlayın (`checked`).
3. İkinci `<fieldset>` içeriğini onay kutularına dönüştürün.
4. Kendi sosisli sandviç (hotdog) seçeneklerinizden birkaç tane daha ekleyin.

```html
<form>
  <h2>Hot dog order form</h2>
  <fieldset>
    <legend>Choose your dog</legend>
    <ul>
      <li>
        <input type="radio" id="beef" name="dog" value="beef" checked />
        <label for="beef">Beef</label>
      </li>
      <li>
        <input type="radio" id="pork" name="dog" value="pork" />
        <label for="pork">Pork</label>
      </li>
      <li>
        <input type="radio" id="turkey" name="dog" value="turkey" />
        <label for="turkey">Turkey</label>
      </li>
      <li>
        <input type="radio" id="veggie" name="dog" value="veggie" />
        <label for="veggie">Vegan</label>
      </li>
    </ul>
  </fieldset>
  <fieldset>
    <legend>Choose your toppings</legend>
    <ul>
      <li>
        <input type="checkbox" id="sauerkraut" name="topping" value="sauerkraut" />
        <label for="sauerkraut">Sauerkraut</label>
      </li>
      <li>
        <input type="checkbox" id="mustard" name="topping" value="mustard" />
        <label for="mustard">Yellow mustard</label>
      </li>
      <li>
        <input type="checkbox" id="ketchup" name="topping" value="ketchup" />
        <label for="ketchup">Ketchup</label>
      </li>
      <li>
        <input type="checkbox" id="onions" name="topping" value="onions" />
        <label for="onions">Crispy onions</label>
      </li>
    </ul>
  </fieldset>
</form>
```

---

## Görev 3: Özel giriş tipleri

Bu görevde özel input türlerini uygulayacaksınız:
1. Email (`type="email"`)
2. Website (`type="url"`)
3. Phone number (`type="tel"`)
4. Favorite color (`type="color"`)

```html
<form>
  <h2>Personal profile</h2>
  <ul>
    <li>
      <label for="mail">Email:</label>
      <input type="email" id="mail" name="user_email" />
    </li>
    <li>
      <label for="site">Website:</label>
      <input type="url" id="site" name="user_website" />
    </li>
    <li>
      <label for="tel">Phone number:</label>
      <input type="tel" id="tel" name="user_phone" />
    </li>
    <li>
      <label for="color">Favorite color:</label>
      <input type="color" id="color" name="fav_color" />
    </li>
  </ul>
</form>
```

---

## Görev 4: Açılır seçim menüsü

Bu görevde kullanıcıların yemek seçmesini sağlayacak bir `<select>` menüsü oluşturacaksınız.

### Yönergeler:
1. Temel bir `<select>` kutusu yapısı kurun.
2. "food" etiketiyle semantik olarak ilişkilendirin (`for`/`id`).
3. Menü içindeki seçenekleri "Mains" ve "Snacks" olarak iki alt gruba ayırın (`<optgroup>`).

```html
<form>
  <h2>Pick your dinner</h2>
  <label for="food">Select your food:</label>
  <select id="food" name="food_choice">
    <optgroup label="Mains">
      <option value="curry">Curry</option>
      <option value="pizza">Pizza</option>
      <option value="fajitas">Fajitas</option>
    </optgroup>
    <optgroup label="Snacks">
      <option value="chips">Chips</option>
      <option value="salad">Salad</option>
      <option value="garlic-bread">Garlic bread</option>
    </optgroup>
  </select>
</form>
```

---

## Görev 5: Yapısal form gruplaması

Bu görevde sağlanan form kontrollerini yapılandırmanız istenmektedir.

### Yönergeler:
1. İlk iki ve sonraki iki form alanını iki ayrı `<fieldset>` içine ayırın ve uygun `<legend>` başlıkları verin.
2. Her metin etiketini semantik olarak `<label>` elementiyle işaretleyin.
3. Etiket/alan çiftlerinin alt alta düzgün hizalanması için her birini birer liste öğesi (`<li>`) veya yapısal `<div>` içine sarın.

```html
<form>
  <h2>Customer feedback</h2>
  <fieldset>
    <legend>Your personal details</legend>
    <div>
      <label for="cust-name">Name:</label>
      <input type="text" id="cust-name" name="name" />
    </div>
    <div>
      <label for="cust-email">Email:</label>
      <input type="email" id="cust-email" name="email" />
    </div>
  </fieldset>
  <fieldset>
    <legend>Your comments</legend>
    <div>
      <label for="comments">Comments:</label>
      <textarea id="comments" name="comments" rows="4" cols="30"></textarea>
    </div>
  </fieldset>
</form>
```

---

## Görev 6: Form doğrulaması

Bu görevde basit bir destek sorgusu formuna istemci tarafı doğrulama kuralları eklemeniz istenmektedir.

### Yönergeler:
1. Tüm giriş alanlarını form gönderilmeden önce zorunlu kılın (`required`).
2. "Email address" alanının türünü `email`, "Phone number" alanının türünü `tel` yapın.
3. "User name" alanına 5 ile 20 karakter arası geçerli bir uzunluk sınırlaması koyun (`minlength="5"` `maxlength="20"`).

```html
<form>
  <h2>Support query</h2>
  <ul>
    <li>
      <label for="uname">User name:</label>
      <input type="text" id="uname" name="user_name" minlength="5" maxlength="20" required />
    </li>
    <li>
      <label for="uemail">Email address:</label>
      <input type="email" id="uemail" name="user_email" required />
    </li>
    <li>
      <label for="uphone">Phone number:</label>
      <input type="tel" id="uphone" name="user_phone" required />
    </li>
    <li>
      <label for="ucomment">Comment:</label>
      <textarea id="ucomment" name="user_comment" required></textarea>
    </li>
    <li>
      <button type="submit">Submit query</button>
    </li>
  </ul>
</form>
```

---

# 24. Uygulama Görevi: Geri bildirim formu

**HTML** > **Challenge: Feedback form** (Challenge: Structuring a feedback form) | English (US)

Bu meydan okumada, bir otel için kurgulanmış bir geri bildirim formunu (`feedback form`) anlamsal açıdan zengin, doğru yapılandırılmış ve stilize edilmiş bir HTML formuna dönüştürme yeteneğiniz test edilmektedir.

---

## Başlangıç noktası

1. Bilgisayarınızda `forms-challenge` adında yeni bir klasör oluşturun.
2. Klasörünüzün içinde `index.html` adlı bir dosya oluşturun ve aşağıdaki başlangıç HTML kodunu kaydedin:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Forms challenge</title>
    <link href="style.css" rel="stylesheet" />
    <script defer src="index.js"></script>
  </head>
  <body>
    We want your feedback!

    We're very excited that you visited the little house in the woods,
    and we want to hear what you thought of it! Please fill in the below
    sections. You don't need to provide your name or contact details, but
    if you do, we'll enter you into a prize draw where you'll have a chance
    to win prizes.

    --

    Facilities

    Was the porridge
    Too hot?
    Too cold?
    Just right?

    Were the beds
    Too hard?
    Too soft?
    Just right?

    Describe the chairs (select all you agree with)
    Comfy
    Luxurious
    Hi-tech
    Pretty
    Majestic

    --

    About your hosts

    Who's your favorite bear?
    Papa bear
    Mama bear
    Junior
    Dozer

    Which greeting did you prefer?
    Wave
    Friendly greeting
    Growl
    Claw marks in the door

    --

    Any other feedback?

    Give us your comments

    --

    Your details

    Name
    Email
    Phone

    --

    Submit
  </body>
</html>
```

3. Klasörünüzün içinde `style.css` adlı bir dosya oluşturun ve aşağıdaki CSS kodunu içine yapıştırın:

```css
/* Basic font styles */

body {
  background-color: white;
  color: #333333;
  font: 1em / 1.4 system-ui;
  padding: 1em;
  max-width: 800px;
  margin: 0 auto;
}

h1 {
  font-size: 2rem;
}

h2 {
  font-size: 1.6rem;
}

h1,
h2 {
  margin: 0 0 20px;
  color: purple;
}

* {
  box-sizing: border-box;
}

p {
  color: gray;
  margin: 0.5em 0;
}

/* Form structure */

fieldset {
  border: 0;
  padding: 0;
}

legend {
  padding-bottom: 10px;
  font-weight: bold;
}

fieldset,
.separator {
  margin-bottom: 20px;
}

.form-section {
  margin-bottom: 20px;
  padding: 20px;
}

img {
  max-width: 100%;
  height: 50px;
  margin: 20px 0;
}

/* Individual form items */

fieldset input {
  margin: 0 10px 0 0;
}

label {
  margin-right: 40px;
}

textarea {
  margin-top: 10px;
  padding: 5px;
  width: 100%;
  height: 200px;
}

.separator {
  display: flex;
}

.separator label {
  flex: 2;
}

.separator input,
.separator select {
  flex: 3;
  padding: 5px;
}

button {
  padding: 10px 20px;
  border-radius: 10px;
  border: 1px solid grey;
  background-color: #dddddd;
  width: 50%;
  margin: 0 auto;
  display: block;
}

button:hover,
button:focus {
  background-color: #eeeeee;
  cursor: pointer;
}
```

---

## Proje yönergeleri

Ormandaki küçük evde (little house in the woods) kaldığınızı hayal edin. Bu otel için bir geri bildirim formu oluşturacaksınız.

### 1. Form kontrollerini uygulama
1. **"Facilities" bölümünde:** İlk iki satır kümesini radyo düğmelerine (`radio`) dönüştürün; her biri için bir `<label>` ve tüm grubu tanımlayan bir `<legend>` ekleyin. Her iki grupta da ilk radyo düğmesini varsayılan olarak seçili (`checked`) yapın.
2. **"Facilities" bölümünde:** Üçüncü satır kümesini onay kutularına (`checkbox`) dönüştürün; her biri için `<label>` ve grup için `<legend>` ekleyin.
3. **"About your hosts" bölümünde:** Her iki satır kümesini açılır seçenekler menüsüne (`<select>`) ve her biri için açıklayıcı bir `<label>` etiketine dönüştürün.
4. **"Any other feedback?" bölümünde:** Çok satırlı bir metin giriş alanı (`<textarea>`) ekleyin ve var olan metni onun açıklayıcı etiketi (`<label>`) yapın.
5. **"Your details" bölümünde:** Listelenen üç değer için uygun türde giriş alanları (`<input>`) ekleyin (`text`, `email`, `tel`). Var olan metinleri etiketlere (`<label>`) dönüştürün.
6. "Submit" metnini form için bir gönderme düğmesine (`<button type="submit">`) dönüştürün.

### 2. Formu yapılandırma
1. Formun tamamını bir `<form>` elementi ile sarın.
2. Formun içine, her form bölümünü sarmak için tekrarlayan yapısal elementler ekleyin (örneğin `<section>` veya `<div>`). Her bölüme `class="form-section"` sınıfını verin (başlangıç metnindeki çift tire `--` işaretlerini kaldırın).
3. Bazı kontrol/etiket çiftlerinin kendi ayrı satırlarında durmasını sağlamak için bunları sarmalayan elementlere `class="separator"` sınıfı ekleyin.
4. Çok satırlı metin kutusu ile etiketi arasına iki öğenin ayrı satırlara oturması için bir satır sonu etiketi (`<br>`) ekleyin.

### 3. Ek HTML özellikleri
1. Başlıkları uygun etiketlerle işaretleyin:
   - En üst düzey başlık: `<h1>We want your feedback!</h1>`
   - İkinci düzey başlıklar (`<h2>`): "Facilities", "About your hosts", "Any other feedback?", ve "Your details".
2. En üst düzey başlığın altındaki açılış paragrafını `<p>` etiketi içine alın.
3. Açılış paragrafında "little house in the woods" ve "prize draw" metinlerini bağlantılara dönüştürün (`href="#"`).
4. Açılış paragrafının altına dekoratif bir görsel ekleyin:
   `https://mdn.github.io/shared-assets/images/examples/learn/woodland-strip.jpg`
   Görsel tamamen dekoratif olduğu için `alt=""` boş bırakılmalıdır.

---

## İpuçları ve püf noktaları

- Kodunuzu denetlemek için [W3C HTML validator](https://validator.w3.org/) aracını kullanın.
- Hangi elemanın nereye geleceğini hayal etmekte zorlanırsanız basit bir blok şeması çizin.

---

## Çözüm ve tam kod

<details>
<summary>Çözümü görmek için buraya tıklayın</summary>

Tamamlanmış `index.html` dosyanız şu şekilde görünmelidir:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Forms challenge</title>
    <link href="style.css" rel="stylesheet" />
    <script defer src="index.js"></script>
  </head>
  <body>
    <h1>We want your feedback!</h1>

    <p>
      We're very excited that you visited the
      <a href="#">little house in the woods</a>, and we want to hear what you
      thought of it! Please fill in the below sections. You don't need to
      provide your name or contact details, but if you do, we'll enter you into
      a <a href="#">prize draw</a> where you'll have a chance to win prizes.
    </p>

    <img
      src="https://mdn.github.io/shared-assets/images/examples/learn/woodland-strip.jpg"
      alt="" />

    <form>
      <section class="form-section">
        <h2>Facilities</h2>

        <fieldset>
          <legend>Was the porridge</legend>
          <input type="radio" id="porridge-hot" name="porridge" value="hot" checked />
          <label for="porridge-hot">Too hot?</label>
          <input type="radio" id="porridge-cold" name="porridge" value="cold" />
          <label for="porridge-cold">Too cold?</label>
          <input type="radio" id="porridge-right" name="porridge" value="right" />
          <label for="porridge-right">Just right?</label>
        </fieldset>

        <fieldset>
          <legend>Were the beds</legend>
          <input type="radio" id="beds-hard" name="beds" value="hard" checked />
          <label for="beds-hard">Too hard?</label>
          <input type="radio" id="beds-soft" name="beds" value="soft" />
          <label for="beds-soft">Too soft?</label>
          <input type="radio" id="beds-right" name="beds" value="right" />
          <label for="beds-right">Just right?</label>
        </fieldset>

        <fieldset>
          <legend>Describe the chairs (select all you agree with)</legend>
          <input type="checkbox" id="chairs-comfy" name="chairs" value="comfy" />
          <label for="chairs-comfy">Comfy</label>
          <input type="checkbox" id="chairs-luxurious" name="chairs" value="luxurious" />
          <label for="chairs-luxurious">Luxurious</label>
          <input type="checkbox" id="chairs-hitech" name="chairs" value="hitech" />
          <label for="chairs-hitech">Hi-tech</label>
          <input type="checkbox" id="chairs-pretty" name="chairs" value="pretty" />
          <label for="chairs-pretty">Pretty</label>
          <input type="checkbox" id="chairs-majestic" name="chairs" value="majestic" />
          <label for="chairs-majestic">Majestic</label>
        </fieldset>
      </section>

      <section class="form-section">
        <h2>About your hosts</h2>

        <div class="separator">
          <label for="bear">Who's your favorite bear?</label>
          <select id="bear" name="bear">
            <option value="papa">Papa bear</option>
            <option value="mama">Mama bear</option>
            <option value="junior">Junior</option>
            <option value="dozer">Dozer</option>
          </select>
        </div>

        <div class="separator">
          <label for="greeting">Which greeting did you prefer?</label>
          <select id="greeting" name="greeting">
            <option value="wave">Wave</option>
            <option value="friendly">Friendly greeting</option>
            <option value="growl">Growl</option>
            <option value="claw">Claw marks in the door</option>
          </select>
        </div>
      </section>

      <section class="form-section">
        <h2>Any other feedback?</h2>

        <label for="comments">Give us your comments</label><br />
        <textarea id="comments" name="comments"></textarea>
      </section>

      <section class="form-section">
        <h2>Your details</h2>

        <div class="separator">
          <label for="name">Name</label>
          <input type="text" id="name" name="name" />
        </div>

        <div class="separator">
          <label for="email">Email</label>
          <input type="email" id="email" name="email" />
        </div>

        <div class="separator">
          <label for="phone">Phone</label>
          <input type="tel" id="phone" name="phone" />
        </div>
      </section>

      <button type="submit">Submit</button>
    </form>
  </body>
</html>
```

</details>

---

# 25. HTML hata ayıklama

**HTML** > **Debugging HTML** (Debugging HTML) | English (US)

Kod yazmak harika bir histir; ancak bir hata (bug) ortaya çıktığında ve sayfanız beklediğiniz gibi çalışmadığında veya görüntülenmediğinde ne yapacaksınız? Bu makale, HTML belgelerindeki yaygın hataları nasıl teşhis edeceğinizi, tarayıcı Geliştirici Araçları'ndaki (DevTools) DOM Denetçisini (DOM Inspector) nasıl kullanacağınızı ve W3C Doğrulayıcısı (Validator) ile geçerli ve hatasız HTML yazmayı öğretir.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | [Basic HTML syntax](#1-basic-html-syntax) bölümünde açıklandığı gibi temel HTML aşinalığı. |
| **Learning outcomes (Öğrenim çıktıları):** | • Hata ayıklamanın (debugging) geliştirme sürecinin doğal bir parçası olduğunu anlama.<br>• HTML'in tarayıcılar tarafından nasıl "bağışlayıcı" (permissive) bir şekilde yorumlandığını ve bunun neden sinsi hatalara yol açabileceğini kavrama.<br>• Tarayıcı DOM Denetçisini (DOM Inspector) kullanarak oluşturulan DOM ağacını inceleme.<br>• W3C HTML Validation servisini kullanarak HTML sözdizimi hatalarını tespit etme ve düzeltme. |

---

## Hata ayıklama korkutucu değildir

Hangi dilde kod yazarsanız yazın, her şey yolunda giderken aniden o korkulan an gelir: bir hata (error) meydana gelir. Bir şeyi yanlış yapmışsınızdır; kodunuz ya hiç çalışmaz ya da tam olarak istediğiniz gibi davranmaz.

Örneğin derlenen dillerde (örneğin Rust), derleyici hatanın yerini ve nedenini açıkça gösterir ve düzeltilmeden programın çalışmasına izin vermez. Ancak web geliştirmede ve özellikle HTML'de durum oldukça farklıdır.

---

## HTML ve hata ayıklama

HTML, derlenen bir programlama dili değildir; **yorumlanan (interpreted)** bir biçimlendirme dilidir. Tarayıcı HTML dosyasını yukarıdan aşağıya okur ve doğrudan ekrana çizer.

En önemli özellik ise şudur: **Tarayıcılar son derece bağışlayıcıdır (permissive).** Bir HTML dosyasında bir etiketi kapatmayı unutsanız, etiketleri yanlış iç içe koysanız veya geçersiz bir nitelik yazsanız bile tarayıcı bir hata ekranı fırlatıp durmaz! Bunun yerine, ne demek istediğinizi tahmin etmeye çalışır ve içeriği elinden geldiğince çizmeye devam eder.

Bu durum ilk bakışta harika gibi görünse de aslında büyük bir tuzaktır:
- Kodunuz yanlış olsa bile sayfa bir şekilde çalışır.
- Farklı tarayıcılar bu hataları farklı şekillerde telafi etmeye çalışabilir; bu da sitenizin Chrome'da düzgün görünürken Safari veya Firefox'ta bozulmasına yol açar.
- Ekran okuyucular ve arama motorları bozuk HTML yapısını doğru çözümleyemeyebilir.

---

## DOM Denetçisini Kullanma

Tüm modern tarayıcılarda (Chrome, Firefox, Edge, Safari) dahili **Geliştirici Araçları (Developer Tools / DevTools)** bulunur. Bu araçların en önemlilerinden biri **Elements / Inspector (DOM Denetçisi)** sekmesidir.

DOM Denetçisi, tarayıcının bellekte oluşturduğu canlı **DOM (Belge Nesne Modeli / Document Object Model)** ağacını gösterir. Bu, kaynak koddaki ham HTML'iniz değil; tarayıcının hatalarınızı düzeltmeye çalıştıktan sonra yorumladığı gerçek yapıdır.

Tarayıcıda bir öğeye sağ tıklayıp **İncele (Inspect)** seçeneğini seçerek veya `F12` / `Ctrl + Shift + I` kısayollarıyla Geliştirici Araçlarını açabilirsiniz.

---

## Sıra sizde: DOM denetçisi ile HTML'i inceleme

Aşağıdaki kasıtlı olarak hatalı yazılmış HTML kodunu inceleyelim:

```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>HTML debugging examples</title>
  </head>
  <body>
    <h1>HTML debugging examples</h1>

    <p>What causes errors in HTML?

    <ul>
      <li>Unclosed elements: If an element is <strong>not closed properly,
          then its effect can spread into subsequent elements, and give you
          some strange results.

      <li>Badly nested elements: Nesting elements properly is also very important
          for code behaving neatly! <strong><span>famously wrote <q>A string of text</strong></span></q>.</li>

      <li>Unclosed attributes: Another common source of HTML problems. Let's look at an <a href="https://www.mozilla.org/>link to the Mozilla homepage</a>.</li>
    </ul>
  </body>
</html>
```

Bu sayfayı bir tarayıcıda açıp DOM Denetçisi ile incelediğinizde şunları görürsünüz:
1. **Kapatılmamış `<p>` etiketi:** Tarayıcı, `<ul>` etiketinin başladığı yerde paragrafın bittiğini tahmin edip kendi kendine bir `</p>` kapanış etiketi yerleştirmiştir.
2. **Kapatılmamış `<strong>` etiketi:** İlk liste öğesinde kapatılmayan `<strong>`, ikinci liste öğesine sızmış ve oradaki metinlerin de koyu görünmesine yol açmıştır.
3. **Kötü iç içe geçmiş etiketler (`<strong><span>...</strong></span>`):** Tarayıcı sırayı düzeltmeye çalışırken DOM ağacında fazladan kapanış ve açılış etiketleri oluşturmuştur.
4. **Kapatılmamış tırnak işareti (`href="https://www.mozilla.org/>`):** Tırnak kapatılmadığı için tarayıcı tırnaktan sonraki metinleri ve hatta `>` işaretini URL'in bir parçası sanmış ve bağlantıyı tamamen bozmuştur.

---

## HTML doğrulaması

Küçük bir belgede hataları gözle bulmak kolay olabilir; ancak binlerce satırlık karmaşık bir web sayfasında hataları tek tek aramak imkansızdır.

İşte bu noktada **HTML Doğrulayıcıları (HTML Validators)** devreye girer. Resmi web standartlarını belirleyen konsorsiyum olan W3C, ücretsiz bir doğrulama hizmeti sunar:
- **[W3C Markup Validation Service](https://validator.w3.org/)**

Doğrulayıcı üç yöntemle kontrol yapabilir:
1. **Validate by URI:** Canlı yayındaki bir web sayfasının adresini girerek.
2. **Validate by File Upload:** Bilgisayarınızdaki `.html` dosyasını yükleyerek.
3. **Validate by Direct Input:** HTML kodunuzu doğrudan bir metin kutusuna yapıştırarak.

### Hata mesajlarını yorumlama

Doğrulayıcı bir hata bulduğunda:
- Hatanın oluştuğu **satır (Line)** ve **sütun (Column)** numarasını bildirir.
- Hatanın teknik açıklamasını sunar (örneğin: *"End tag strong seen, but there were open elements"* veya *"Unclosed element"*).
- Bazen bir tek kapatılmamış etiket, sonraki satırlarda art arda 10 farklı hata çıkmasına yol açabilir. Bu nedenle **her zaman listenin en başındaki ilk hatadan başlayarak düzeltin** ve ardından sayfayı tekrar doğrulayın.

---

## Özet

Bu makalede HTML hata ayıklamanın temel prensiplerini öğrendiniz:
- HTML'in yorumlanan ve hataları gizleyen bağışlayıcı yapısını,
- Tarayıcı DOM Denetçisi ile oluşturulan gerçek öğe ağacını incelemeyi,
- W3C Markup Validation Service ile profesyonel, standartlara uygun ve hatasız kod yazmayı kavradınız.

---

# 26. Test: HTML testleri indeksi

**HTML** > **Test: HTML tests index** (Test your skills: Structuring content with HTML) | English (US)

Bu sayfa, "Structuring content with HTML" modülünde öğrendiğiniz konuları pekiştirmek ve bilginizi ölçmek amacıyla hazırlanmış olan tüm konu bazlı testlerin dizinini sunmaktadır.

---

## Konulara göre HTML testleri

Bu modül boyunca yer alan pratik beceri testlerine aşağıdaki bağlantılardan ulaşabilirsiniz:

1. **[Test: HTML text basics](#6-test-html-text-basics):** Temel HTML metin biçimlendirmesi, başlıklar, paragraflar, vurgulama (`<em>`, `<strong>`) ve listeler (`<ul>`, `<ol>`).
2. **[Test: Advanced HTML text](#8-test-advanced-html-text):** Alıntılar (`<blockquote>`, `<q>`, `<cite>`), kısaltmalar (`<abbr>`), adresler (`<address>`) ve kod etiketleri (`<code>`, `<pre>`).
3. **[Test: Links](#12-test-links):** Kök/bağıl bağlantılar (`<a>`, `href`), belge içi çıpalar, e-posta bağlantıları (`mailto:`) ve `target="_blank"`.
4. **[Test: Images](#15-test-images):** Görsel ekleme (`<img>`), `src`, `alt` metni, boyutlandırma ve `<picture>` / `srcset` ile duyarlı görseller.
5. **[Test: Audio and video](#17-test-audio-and-video):** `<video>` ve `<audio>` etiketleri, çoklu kaynaklar (`<source>`), kontroller ve altyazılar (`<track>`).
6. **[Test: Forms and buttons](#23-test-forms-and-buttons):** Form kontrolleri (`<input>`, `<select>`, `<textarea>`), etiketleme (`<label>`), gruplama (`<fieldset>`, `<legend>`) ve istemci doğrulaması.

---

## Ayrıca bakınız

- [Structuring content with HTML (Modül Özeti)](#structuring-content-with-html)
- [W3C HTML5 Specification](https://www.w3.org/TR/html52/)

---

# 27. Ek kılavuzlar

Bu bölüm, temel HTML eğitiminin ötesine geçerek modern web sayfalarında sıklıkla kullanılan vektör grafikleri (SVG) ve gelişmiş ortam yerleştirme teknolojilerini (iframes, embed, object) ele alan ek kılavuzları içermektedir.

---

## 27.1. Vektör grafikleri

**HTML** > **Additional tutorials** > **Vector graphics** (Adding vector graphics to the web) | English (US)

Vektör grafikleri web üzerinde son derece kullanışlıdır. Bu makalede vektör grafiklerinin ne olduğu, popüler XML tabanlı SVG (Ölçeklenebilir Vektör Grafikleri) formatı ve SVG grafiklerinin web sayfalarına nasıl dahil edileceği açıklanmaktadır.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | Temel HTML aşinalığı ve [Images](#14-images) bölümünde açıklandığı gibi raster görsellerin çalışma mantığı. |
| **Learning outcomes (Öğrenim çıktıları):** | • Raster (piksel tabanlı) ve Vektör görseller arasındaki farkları kavrama.<br>• SVG formatının ne olduğunu ve XML yapısını anlama.<br>• SVG dosyalarını `<img>` elementi ile sayfaya ekleme.<br>• Satır içi (inline) `<svg>` kodunu doğrudan HTML içine yerleştirme ve avantajları.<br>• `<iframe>` ile SVG gömme yöntemleri. |

---

### Vektör grafikleri nedir?

Web üzerinde iki ana görsel türüyle çalışırsınız:

1. **Raster görseller (Piksel tabanlı):** PNG, JPG, GIF ve WebP gibi formatlardır. Bir piksel ızgarası kullanılarak tanımlanırlar. Dosya, her bir pikselin tam olarak nerede durduğunu ve hangi renge sahip olduğunu saklar.
   - **Sorun:** Bir raster görseli orijinal boyutundan daha fazla büyüttüğünüzde veya yüksek çözünürlüklü (Retina) ekranlarda görüntülediğinizde piksellenme (bulanıklaşma) oluşur.
2. **Vektör görseller:** Görseli piksellerle değil; yollar (paths), çizgiler, eğriler, daireler ve çokgenler gibi matematiksel şekil tanımlarıyla saklar.
   - **Büyük Avantaj:** Vektör görseller kalitelerinden zerre ödün vermeden **sonsuz düzeyde küçültülebilir veya büyütülebilir**. İster bir akıllı saat ekranında, ister dev bir reklam panosunda gösterilsin, kenarlar her zaman kusursuz keskinliktedir!
   - Dosya boyutları çoğu zaman raster grafiklere kıyasla çok daha küçüktür.

---

### SVG nedir?

**SVG (Scalable Vector Graphics)**, iki boyutlu vektör görsellerini tanımlamak için kullanılan XML tabanlı bir dildir.

Tıpkı HTML gibi etiketlerden oluşur. Şekilleri tanımlamak için `<circle>`, `<rect>`, `<polygon>`, `<path>` gibi elementler kullanılır.

Örnek bir SVG kodu:

```xml
<svg version="1.1"
     baseProfile="full"
     width="300" height="200"
     xmlns="http://www.w3.org/2000/svg">
  <rect width="100%" height="100%" fill="black" />
  <circle cx="150" cy="100" r="90" fill="blue" />
</svg>
```

---

### Sayfalarınıza SVG ekleme yöntemleri

#### 1. `<img>` elementi ile hızlı ekleme

Tıpkı bir PNG veya JPG gibi, bir SVG dosyasını doğrudan `<img>` etiketinin `src` niteliğine verebilirsiniz:

```html
<img
  src="triangle.svg"
  alt="triangle with equal sides"
  height="87"
  width="100" />
```

- **Artıları:** Hızlı, tanıdık ve tarayıcı tarafından kolayca önbelleğe alınır.
- **Eksileri:** SVG içindeki elementler CSS ile doğrudan stillendirilemez ve JavaScript ile SVG'nin iç yapısına müdahale edilemez.

#### 2. Satır içi (Inline) SVG kodunu HTML'e dahil etme

SVG kodunu dosya olarak değil, doğrudan HTML belgenizin içine yazabilirsiniz:

```html
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow" />
</svg>
```

- **Artıları:**
  - Fazladan bir HTTP isteği tasarrufu sağlar.
  - SVG elementlerine CSS sınıfları ve stilleri (`hover` efektleri vb.) uygulanabilir.
  - JavaScript ile SVG şekilleri dinamik olarak manipüle edilebilir.
- **Eksileri:** HTML dosyasının boyutunu artırır ve tarayıcı tarafından bağımsız olarak önbelleğe alınamaz.

#### 3. `<iframe>` ile bir SVG gömme

```html
<iframe src="triangle.svg" width="500" height="500" sandbox>
  <img src="triangle.png" alt="A triangle" />
</iframe>
```

---

### Özet

Bu bölümde vektör grafiklerini ve SVG'nin gücünü inceledik. Çözünürlükten bağımsız netlik sağlayan SVG'nin ikonlar, logolar ve illüstrasyonlar için neden modern webin vazgeçilmezi olduğunu öğrendiniz.

---

## 27.2. Gömme teknolojileri

**HTML** > **Additional tutorials** > **Embedding technologies** (General embedding technologies) | English (US)

Web sayfalarında başka web sayfalarını, üçüncü taraf içerikleri (YouTube videoları, Google Haritalar) ve harici belgeleri (PDF) gömmek için kullanılan temel teknolojiler: `<iframe>`, `<embed>` ve `<object>`.

| Alan | Detay |
| :--- | :--- |
| **Prerequisites (Önkoşullar):** | Temel HTML aşinalığı ve [Images](#14-images) ile [Video and audio](#16-video-and-audio) bölümlerinin kavranmış olması. |
| **Learning outcomes (Öğrenim çıktıları):** | • Web sayfalarına harici içerik gömmenin tarihsel gelişimi.<br>• `<iframe>` elementinin anatomisi ve yaygın parametreleri.<br>• `<iframe>` güvenlik riskleri: HTTPS zorunluluğu, `sandbox` niteliği ve CSP (İçerik Güvenlik Politikası).<br>• `<embed>` ve `<object>` elementleri arasındaki farklar.<br>• Web sayfalarında PDF belgelerini gömme yöntemleri. |

---

### Gömme teknolojilerinin kısa tarihi

Web'in ilk yıllarında web siteleri **frames (çerçeveler)** ve **frameset** kullanılarak yapılırdı. Ekranın bir kısmı menü sayfası, diğer kısmı içerik sayfası olarak bölünürdü. Ancak bu mimari derin bağlantı (deep linking), yazdırma, arama motoru optimizasyonu (SEO) ve erişilebilirlik açısından felaketlere yol açtığı için modern web standartlarından tamamen kaldırıldı.

Bugün harici bir web belgesini güvenle gömmenin modern ve standart yolu **`<iframe>` (Inline Frame)** elementidir.

---

### Web sayfalarını gömmek için iframe kullanımı

`<iframe>` elementi, geçerli HTML belgesinin içine başka bir HTML belgesini gömmenizi sağlar:

```html
<iframe
  src="https://developer.mozilla.org/en-US/"
  width="100%"
  height="500"
  frameborder="0"
  allowfullscreen
  sandbox>
  <p>
    <a href="https://developer.mozilla.org/en-US/">
      Fallback link for browsers that don't support iframes
    </a>
  </p>
</iframe>
```

Önemli nitelikler:
- **`src`:** Gömülecek web sayfasının URL'si.
- **`width` ve `height`:** Çerçevenin piksel veya CSS boyutları.
- **`allowfullscreen`:** Çerçevenin tam ekran moduna geçmesine izin verir (video oynatıcılar için gereklidir).
- **`loading="lazy"`:** Çerçeve ekrana yaklaşana kadar yüklenmesini geciktirerek sayfa performansını artırır.

---

### Güvenlik endişeleri ve en iyi pratikler

Sayfanıza başka bir web sitesini gömmek, sitenizi saldırılara açık hale getirebilir (örneğin tıklama avcılığı / clickjacking, kötü amaçlı script çalıştırma). Bu nedenle şu güvenlik kurallarına mutlaka uyulmalıdır:

1. **Yalnızca gerekli olduğunda gömün:** Güvenmediğiniz üçüncü taraf siteleri asla sayfanıza gömmeyin.
2. **Her zaman HTTPS kullanın:** Hem ana sayfanız hem de `<iframe>` içindeki URL HTTPS üzerinden sunulmalıdır. Karma içerik (Mixed Content) tarayıcılar tarafından engellenir.
3. **Her zaman `sandbox` niteliğini kullanın:**
   `sandbox` niteliği, gömülen içeriği en kısıtlı izin modunda çalıştırır (scriptler çalışmaz, formlar gönderilemez, yeni pencereler açılamaz). İhtiyaç duyulan izinler tek tek verilir:
   ```html
   <iframe seamless src="https://example.com" sandbox="allow-scripts allow-forms"></iframe>
   ```
4. **CSP (Content Security Policy) direktiflerini yapılandırın:** Sunucu düzeyinde hangi sitelerin sayfanızı çerçeve içine alabileceğini (`frame-ancestors`) belirleyin.

---

### <embed> ve <object> elementleri

`<iframe>` genel HTML sayfalarını gömmek için tasarlanmışken; **`<embed>`** ve **`<object>`** elementleri geçmişte Flash, Java Applet gibi eklentileri (plugins) çalıştırmak için kullanılmıştır.

Günümüzde bu eklentiler tarihe karıştığı için, `<embed>` ve `<object>` elementlerinin başlıca modern kullanım alanı **PDF belgelerini ve multimedya dosyalarını** gömmektir.

---

### PDF belgelerini gömme

Bir PDF dosyasını web sayfasında doğrudan görüntülenebilir kılmak için `<object>` veya `<iframe>` kullanılabilir:

```html
<object data="mypdf.pdf" type="application/pdf" width="800" height="1200">
  <p>
    You don't have a PDF plugin, but you can
    <a href="mypdf.pdf">download the PDF file.</a>
  </p>
</object>
```

veya `<iframe>` ile:

```html
<iframe src="mypdf.pdf" width="100%" height="600">
  <p>Your browser does not support PDFs.
    <a href="mypdf.pdf">Download the PDF</a>.
  </p>
</iframe>
```

---

### Özet

Bu makalede genel web ortamı gömme teknolojilerini inceledik:
- `<iframe>` ile harici sayfaları ve medya widget'larını güvenli bir şekilde entegre etmeyi,
- `sandbox` ve HTTPS ile güvenlik risklerini bertaraf etmeyi,
- `<object>` ve `<embed>` ile PDF gibi belgeleri doğrudan sayfa içinde sunmayı öğrendiniz.

Böylece **"Structuring content with HTML"** modülünün tüm derslerini, sınavlarını, meydan okumalarını ve ek kılavuzlarını eksiksiz olarak tamamlamış oldunuz!

