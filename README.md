## KMeans ile Görüntü Sıkıştırma (Image Compression)

Bir görüntüdeki renk sayısını azaltmak için **KMeans** algoritmasını kullanacağız:

- Isınma yapmak isterseniz `warmup_k_means.ipynb` ile başlayın  
- Ardından ana çalışma için `image_compression.ipynb` dosyasına geçin

<img src="https://miro.medium.com/max/840/1*y0nV4cWk3KbzXSe9dIWL5g.jpeg" width=500>

## Çalışma Notları

Bu proje önce `warmup_k_means.ipynb` ile yapay kümelerde KMeans, elbow yöntemi ve hiyerarşik kümelemeyi, sonra `image_compression.ipynb` ile bir görüntünün renklerini KMeans ile azaltarak sıkıştırmayı gösterir. İki notebook da şablondaki isimleriyle, kendi kodumla yeniden yazıldı.

1. Ortam: `workintech` sanal ortamı. Proje klasöründe `pyenv local workintech` ile etkinleştirilir. `scikit-image` yoksa `pip install scikit-image` ile kurulur (görüntü bu paketin içinde gelir, ayrıca veri indirmek gerekmez).
2. `jupyter notebook` ile notebook'ları aç ve hücreleri sırayla çalıştır. İkisi de birkaç saniye içinde çalışır.

Özet: Isınmada elbow ve silhouette yöntemleri de dendrogram da 4 kümeyi gösteriyor; KMeans ile bulunan kümeler gerçek kümelerle birebir örtüşüyor. Görüntüdeki 113.382 renk 32'ye indirildiğinde görüntü açıkça tanınıyor (PSNR 30.8 dB) ve paletli PNG olarak orijinal PNG'den 7.7 kat küçük (412 KB yerine 53 KB). 2 ile 128 arasında 7 farklı k denendi; k = 32 kalite ile boyut arasında iyi bir denge. Ayrıntılar ve sınırlılıklar notebook'ların sonuç bölümlerinde.
