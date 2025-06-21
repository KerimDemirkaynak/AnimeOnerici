# 🎲 Gelişmiş Anime Öneri Aracı

Bu proje, kullanıcıların detaylı filtrelere göre anime önerileri almasını sağlayan, tek bir HTML dosyası üzerinde çalışan modern bir web uygulamasıdır. **AniList GraphQL API**'sini kullanarak gerçek zamanlı verilerle rastgele ve kişiselleştirilmiş anime önerileri sunar.

## ✨ Öne Çıkan Özellikler

- **Detaylı Filtreleme:**
  - **Tür/Tema Seçimi:** Birden fazla tür veya tema (tag) seçerek aramanızı kişiselleştirin.
  - **Hariç Tutma:** İstemediğiniz türleri veya temaları kolayca filtre dışı bırakın.
  - **Stüdyo Filtresi:** Belirli animasyon stüdyolarının yapımlarını arayın.
  - **Minimum Puan:** Sadece belirlediğiniz kalitenin üzerindeki animeleri görün.
  - **Yayın Yılı:** Belirli bir yılda yayınlanmış animeleri listeleyin.
- **Rastgele Öneri Motoru:** Filtrelerinize uyan sonuçlar arasından rastgele bir anime önerir.
- **"Başka Öner" Özelliği:** Aynı filtrelerle yeni bir API isteği yapmadan, mevcut sonuç listesinden farklı bir anime önerisi alın.
- **Modern ve Duyarlı Arayüz:** Koyu tema üzerine kurulu, mobil uyumlu ve kullanıcı dostu bir tasarıma sahiptir.
- **Detaylı Anime Kartı:** Önerilen animenin kapak fotoğrafı, puanı, stüdyosu, türleri, bölüm sayısı, açıklaması ve dış bağlantıları (AniList, YouTube fragmanı) gibi bilgileri sunar.
- **Sıfır Bağımlılık:** Herhangi bir framework veya kütüphane olmadan, saf (Vanilla) JavaScript ile yazılmıştır.
- **Tek Dosya:** Tüm HTML, CSS ve JavaScript kodları tek bir dosyada yer alır, bu da kullanımı ve dağıtımı son derece kolaylaştırır.

## 🛠️ Kullanılan Teknolojiler

- **Frontend:**
  - HTML5
  - CSS3 (CSS Değişkenleri ile modern tasarım)
  - Vanilla JavaScript (ES6+)
- **API:**
  - [AniList GraphQL API](https://anilist.gitbook.io/anilist-apiv2-docs/)
- **Kütüphaneler:**
  - [Font Awesome](https://fontawesome.com/) (İkonlar için)
  - [Google Fonts](https://fonts.google.com/) (Poppins fontu için)

## 🚀 Nasıl Kullanılır?

Bu projenin çalışması için herhangi bir kurulum veya sunucu gerekmez.

1.  Bu repodaki `index.html` (veya sizin verdiğiniz isimle) dosyasını indirin.
2.  Dosyayı herhangi bir modern web tarayıcısında (Google Chrome, Firefox, Edge vb.) açın.
3.  Filtreleri seçin ve "Anime Öner" butonuna tıklayarak ilk önerinizi alın!

## 🧠 Kod Yapısı ve Mantığı

Projenin tüm mantığı, `index.html` dosyasındaki `<script>` etiketleri içinde yer alır.

-   **`populateSelects()`**: Sayfa yüklendiğinde `allTagsMap` ve `studioMap` objelerindeki verileri kullanarak filtreleme `select` kutularını dinamik olarak doldurur.
-   **`getFilteredAnime()`**: Ana fonksiyondur.
    1.  Kullanıcının seçtiği tüm filtre değerlerini alır.
    2.  Bu filtrelere göre dinamik olarak bir **GraphQL sorgusu** oluşturur. Bu yapı, sadece gerekli parametrelerin sorguya eklenmesini sağlayarak esneklik sunar.
    3.  `fetch` kullanarak AniList API'sine POST isteği gönderir.
    4.  Gelen sonuçları `fetchedAnimeList` dizisine kaydeder ve ilk rastgele öneriyi göstermek için `suggestAnother()` fonksiyonunu çağırır.
-   **`suggestAnother()`**: `fetchedAnimeList` dizisinden, daha önce gösterilmemiş rastgele bir anime seçer ve `displayAnime()` fonksiyonuna gönderir. Bu sayede aynı filtrelerle tekrar API isteği yapmaya gerek kalmaz.
-   **`displayAnime()`**: Gelen anime verisini kullanarak sonuç alanında gösterilecek olan HTML kartını oluşturur ve ekrana basar.

## 🤝 Katkıda Bulunma

Katkılarınız projeyi daha da geliştirmemize yardımcı olur! Katkıda bulunmak için:

1.  Bu repoyu fork'layın.
2.  Yeni bir dal (branch) oluşturun (`git checkout -b ozellik/yeni-bir-ozellik`).
3.  Değişikliklerinizi yapın ve commit'leyin (`git commit -m 'Yeni bir özellik eklendi'`).
4.  Oluşturduğunuz dala push'layın (`git push origin ozellik/yeni-bir-ozellik`).
5.  Bir Pull Request açın.

## 📜 Lisans

Bu proje [MIT Lisansı](https://choosealicense.com/licenses/mit/) ile lisanslanmıştır.
