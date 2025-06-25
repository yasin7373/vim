Vim Komutları Referans Kılavuzu

Bu kılavuz, Vim metin düzenleyicisini verimli bir şekilde kullanmak için gereken temel ve orta seviye komutları içerir. Yeni başlayanlar için bir başlangıç noktası ve tecrübeli kullanıcılar için bir hatırlatma kaynağı olması amacıyla hazırlanmıştır.
Temel Kavramlar

Vim'in en önemli özelliği "Mod"larıdır. En sık kullanacağınız iki mod şunlardır:

    Normal Mod (Normal Mode): Vim'in varsayılan modudur. Bu modda tuşlar yazı yazmak yerine komutları çalıştırır (hareket etme, silme, kopyalama vb.). Yazı yazarken Esc tuşuna basarak bu moda dönersiniz.

    Ekleme Modu (Insert Mode): Bu modda klavyeniz normal bir metin editörü gibi çalışır ve yazdığınız karakterler dosyaya eklenir.

1. Temel Hareket Komutları (Normal Mod)

Vim'in gücü, farenizi kullanmadan metin içinde hızlıca gezinebilmektir.

    h: Sola git

    j: Aşağı git

    k: Yukarı git

    l: Sağa git

    w: Bir sonraki kelimenin başına git

    b: Bir önceki kelimenin başına git

    e: Kelimenin sonuna git

    0: Satırın en başına git (ilk karaktere)

    ^: Satırdaki ilk metin karakterine git (boşlukları atlar)

    $: Satırın en sonuna git

    gg: Dosyanın en başına git

    G: Dosyanın en sonuna git

    5G veya :5: 5. satıra git

    Ctrl + d: Yarım sayfa aşağı in

    Ctrl + u: Yarım sayfa yukarı çık

2. Ekleme Moduna Geçiş (Normal Mod'dan)

    i: İmlecin bulunduğu karakterin önünden itibaren Ekleme Modu'na geçer.

    I: İmlecin bulunduğu satırın başından itibaren Ekleme Modu'na geçer.

    a: İmlecin bulunduğu karakterin sonrasından itibaren Ekleme Modu'na geçer.

    A: İmlecin bulunduğu satırın sonundan itibaren Ekleme Modu'na geçer.

    o: İmlecin bulunduğu satırın altına yeni bir satır açar ve Ekleme Modu'na geçer.

    O: İmlecin bulunduğu satırın üstüne yeni bir satır açar ve Ekleme Modu'na geçer.

3. Metin Düzenleme (Normal Mod)
Kesme, Kopyalama ve Yapıştırma

    yy: İmlecin bulunduğu satırı kopyala.

    dd: İmlecin bulunduğu satırı kes (sil).

    p: Kopyalanan/kesilen metni imlecin bulunduğu satırın altına yapıştır.

    P: Kopyalanan/kesilen metni imlecin bulunduğu satırın üstüne yapıştır.

"Vim Grameri": Operatör + Hareket

Çoğu düzenleme komutu [operatör][hareket] yapısını kullanır. Örneğin d (delete) bir operatördür ve w (word) bir harekettir.

    dw: İmleçten kelimenin sonuna kadar olan kısmı sil.

    d$: İmleçten satırın sonuna kadar olan kısmı sil.

    dgg: İmleçten dosyanın başına kadar olan kısmı sil.

    caw: İmlecin bulunduğu tüm kelimeyi sil ve ekleme moduna geç ("change around word").

    ci": Tırnak içindeki metni sil ve ekleme moduna geç ("change inside "").

    yiw: İmlecin bulunduğu kelimeyi kopyala ("yank inside word").

    3yy: 3 satır kopyala.

    5dd: 5 satır kes.

Değiştirme ve Silme

    cc: Satırı tamamen sil ve Ekleme Modu'na geç.

    C: İmleçten satır sonuna kadar sil ve Ekleme Modu'na geç.

    r: İmlecin altındaki tek bir karakteri değiştir (Ekleme Modu'na geçmez).

    x: İmlecin altındaki karakteri sil.

    J: Alt satırı mevcut satırın sonuna ekle (birleştir).

Girintileme

    >>: Satırı bir seviye sağa kaydır (girinti ekle).

    <<: Satırı bir seviye sola kaydır (girintiyi azalt).

4. Görsel Mod (Visual Mode)

Metin bloklarını seçmek için kullanılır. Seçim yaptıktan sonra d (kes), y (kopyala), c (değiştir) gibi operatörleri kullanabilirsiniz.

    v: Karakter bazlı Görsel Mod'u başlatır.

    V: Satır bazlı Görsel Mod'u başlatır.

    Ctrl + v: Blok bazlı Görsel Mod'u başlatır (sütun seçmek için ideal).

    Örnek: V tuşuna basın, jj ile 2 satır aşağı inin ve d tuşuna basarak 3 satırı birden silin.

5. Arama ve Değiştirme

    /kelime: kelime'yi aşağıya doğru arar.

    ?kelime: kelime'yi yukarıya doğru arar.

    n: Bir sonraki arama sonucuna gider.

    N: Bir önceki arama sonucuna gider.

    *: İmlecin altındaki kelimeyi arar.

    :%s/eski/yeni/g: Tüm dosyadaki bütün eski kelimelerini yeni olarak değiştirir. (g = global)

    :%s/eski/yeni/gc: Her değişiklik için onay ister. (c = confirm)

6. Geri Alma ve Yineleme

    u: Son işlemi geri al (undo).

    Ctrl + r: Geri alınan işlemi tekrar yap (redo).

    . (Nokta): Yapılan son komutu (örneğin dd veya bir kelime ekleme) tekrar eder. Çok güçlü bir komuttur!

7. Pencere ve Sekme Yönetimi

    :sp: Ekranı yatay olarak ikiye böler.

    :vsp: Ekranı dikey olarak ikiye böler.

    Ctrl + w + h/j/k/l: Pencereler arasında gezin.

    Ctrl + w + w: Pencereler arasında sırayla geçiş yap.

    Ctrl + w + q: Aktif pencereyi kapat.

    :tabnew: Yeni bir sekme aç.

    gt: Bir sonraki sekmeye git.

    gT: Bir önceki sekmeye git.

8. Kaydetme ve Çıkma

    :w: Dosyayı kaydet.

    :q: Dosyadan çık (değişiklik yoksa).

    :wq veya ZZ: Dosyayı kaydedip çık.

    :q!: Değişiklikleri kaydetmeden çıkmaya zorla.

    :w yeni_dosya_adi: Mevcut içeriği farklı bir dosyaya kaydet.

9. İleri Seviye İpuçları

    Makrolar: Tekrarlayan işlemleri kaydedip tek tuşla çalıştırmak için kullanılır.

        qa ile 'a' kaydına kaydı başlat.

        Yapmak istediğin komutları sırala.

        q ile kaydı durdur.

        @a ile makroyu çalıştır. @@ ile son çalıştırılan makroyu tekrar çalıştır.

    Kişiselleştirme (.vimrc): Vim'i kendi ihtiyaçlarınıza göre özelleştirmek için ev dizininizde (~/.vimrc) bir dosya oluşturabilirsiniz.

        Örnek: set number satır numaralarını gösterir.

        Örnek: set mouse=a fare kullanımını tüm modlarda aktif eder.
