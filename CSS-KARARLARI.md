# CSS Kararlari

## 1. Breakpoint Secimi
- Neden 640px ve 1024px sectim?
En yaygin kullanilan cihaz kategorilerini (telefon, tablet ve masaustu) desteklemek adina bu breakpoint'ler en ideal kirilimlardir. Icerik 640px'te daha genis ekranlara uyum saglamaya, 1024px'te ise tamamen masaustu davranisina gecmeye baslar.
- Icerigim bu noktalarda nasil degisiyor?
Mobilden tablete geciste header flex-direction elemanlari tek satir yerine satira yayilir, masaustunde ise 3'lu card grid (izgara) devreye girer. Yazi boyutlari ise breakpoint'lerden bagimsiz olarak `clamp()` ile akici degisir.

## 2. Layout Tercihleri
- Header icin neden Flexbox sectim?
Header'daki elemanlari (logo, navigasyon linkleri) tek yonlu, yanyana esit veya aralikli dagitmak icin en pratik layout araci Flexbox'tir.
- Proje kartlari icin neden Grid sectim?
Proje kartlarinin hem satir hem de sutun duzeninde esit hizalanmasini saglamak icin iki boyutlu layout olan Grid en ideal cözümdür.
- auto-fit mi auto-fill mi kullandim, neden?
Grid'de responsive yapi saglamak ve bosluklari da doldurarak (shrink) kapsayiciya sigacak kadar sutunu otomatik ayarlatmak icin `auto-fit` kullandim.

## 3. Design Tokens
- Hangi renk paletini sectim ve neden?
Mevcut tasarimla uyumlu modern ve dogal "slate/blue" tonlarini sectim. `--color-primary` vurgu icin maviyi temsil ederken tasarim karsitligini korudugu icin secildi. 
- Spacing skalasini nasil belirledim?
Standard base `8px` katsayili margin/padding degerleriyle `--space-xs` -> `--space-3xl` arasinda adimli esnek bir spacing hiyerarsisi kurdum.
- Fluid typography icin clamp degerlerini nasil ayarladim?
Her breakpoint tulumunda minmum piksel degerleri ile genis ekranlarda maksimum olcum olusturacak sekilde, `vw` degeri ile `rem`i harmanlayip `clamp(min, val, max)` mantigi ile akici typonun temellerini dösüdüm.

## 4. Responsive Stratejiler
- Mobile-first yaklasimini nasil uyguladim?
Once varsayilan class/etiket stillerini dar ekranlari dusunerek yazdim (tek sutun). Sonrasinda tablet (640px) ve masaustu (1024px) media query'leri `@media (min-width: ...)` blocklari ile sadece genis ekranlara etki edecek stilleri "uzerine" ekledim.
- Hangi elemanlar breakpoint'lerde degisiyor?
Form genislikleri, navigasyonun yonelimi (yanyana veya altalta), hakkimda kisminin duzeni ve en belirgini proje grid sistemi (tek sutundan 3 sutuna cikma).
- Gorsel boyutlari nasil yonettim?
Genel `img` etiketlerine `max-width: 100%` koyarak overflow yasamayi önledim ve grid projelerindeki fotograflara da `object-fit: cover` vererek responsive davrandigi esnada distorte olmasini engelledim.
