```markdown
# Sanal Mikroskop Projesi

Bu proje, büyük çözünürlüklü patoloji slaytlarını sanal mikroskop görünümünde görüntülemek için OpenSeadragon kütüphanesini kullanmaktadır. Slaytlar, Deep Zoom formatına dönüştürülerek her biri için ayrı bir bağlantı ile sunulmaktadır.

## Slaytlara Şimdi Bakın

[Sanal Mikroskop Projesi](https://metinciris.github.io/slaytlar/)

## BCC tam boy ve yakılaşmış alan:

![BCC Görüntüsü](https://raw.githubusercontent.com/metinciris/slaytlar/main/bcc.jpg)

## Proje Yapısı

Her slayt için aşağıdaki dosya yapısı kullanılmıştır:

```
/slayt1/
    ├── index.html
    ├── output.dzi
    └── output_files/
```

### Ana Dizindeki `index.html`

Ana dizinde bulunan `index.html` dosyası, tüm slaytlar için bağlantılar içermektedir. Ziyaretçiler bu bağlantılar aracılığıyla istedikleri slaydı seçebilir ve inceleyebilir.

### Slayt Klasörlerindeki `index.html`

Her slayt klasöründe bulunan `index.html` dosyası, OpenSeadragon kütüphanesini kullanarak ilgili slaydı sanal mikroskop olarak görüntüler.

Örnek HTML yapısı:

```html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Slayt 1</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/openseadragon/3.0.0/openseadragon.min.js"></script>
    <style>
        body { margin: 0; }
        #viewer { width: 100vw; height: 100vh; }
    </style>
</head>
<body>
    <div id="viewer"></div>

    <script type="text/javascript">
        var viewer = OpenSeadragon({
            id: "viewer",
            prefixUrl: "https://cdnjs.cloudflare.com/ajax/libs/openseadragon/3.0.0/images/",
            tileSources: "output.dzi" // Buraya Deep Zoom dosyanızın yolunu girin
        });
    </script>
</body>
</html>
```

## GitHub Pages

Proje, GitHub Pages üzerinden yayınlanarak kullanıcıların erişimine sunulmuştur. [Proje URL'si](https://metinciris.github.io/slaytlar/) üzerinden görüntülenebilir.

## Yeni Slayt Ekleme

Yeni bir slayt eklemek için:

1. Yeni bir `slaytX` klasörü oluşturun.
2. `output.dzi` ve `output_files` klasörünü bu yeni klasöre kopyalayın.
3. `index.html` dosyasını yapılandırın ve ilgili dizine ekleyin.
4. Ana dizindeki `index.html` dosyasına yeni slayt için bir bağlantı ekleyin.

## OpenSeadragon Kullanımı

OpenSeadragon, büyük görüntüleri yüksek çözünürlükte incelemenizi sağlayan bir JavaScript kütüphanesidir. Projede kullanılan CDN bağlantısı:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/openseadragon/3.0.0/openseadragon.min.js"></script>
```

## Katkıda Bulunma

Bu projeye katkıda bulunmak için lütfen bir pull request gönderin veya bir issue açın. Her türlü geri bildirime açığız!

---

Teşekkürler!
```
