# Urban Sounds Classification


Koç Holding ve Aygaz işbirliği ile düzenlenen ve Global AI Hub önderliğinde gerçekleştirilen Derin Öğrenme Bootcamp eğitimi bünyesinde aşağıdaki projeyi gerçekleştirmekten mutluluk duyuyorum. 


## Proje Künyesi

Proje Adı : Urban Sounds Classification

Proje Kapsamı : “UrbanSounds8K” veri setini kullanarak şehirlerde duyulan seslerin sınıflandırılması

Proje Hedefi : Derin öğrenme algoritmalarını kullanarak yapay zeka modeli hazırlamak

Proje Adımları : 
                * Veri setini indirecek
                * Ses dosyalarından spectrogram oluşturacak
                * Spectrogamlar ait oldukları kategorilere göre bilgisayara kaydedilecek
                * Spectrogramlar üzerinde önişleme yaparak CNN modeli hazırlanacak
                * Hazırlanan model eğitilecek

Global AI Hub 
Değerlendirme : Model performansı bir ölçüt olmayacak. Modelin hazırlanması, eğitilmesi ve hiperparametre optimizasyonunun yapılması aranacak.


Kullanılabilecek kütüphanelerin dokümanları :
    * Librosa (Ses İşleme): https://librosa.org/doc/latest/index.html
    * OpenCV (Görüntü İşleme): https://docs.opencv.org/4.x/d6/d00/tutorial_py_root.html
    * TensorFlow/Keras (Derin Öğrenme): https://www.tensorflow.org/api_docs/python/tf



### Proje Prosedürü

0. Veri Setinin İncelenmesi
    a. “UrbanSounds8K” veri setini bilgisayarınıza indirin. (5,6 GB)    https://urbansounddataset.weebly.com/urbansound8k.html
    b. İndirdiğiniz .tar dosyasını açın. (Mentorlarınızdan destek alabilirsiniz )
    c. README dosyasını okuyarak elimizdeki verinin ne olduğunu ve nasıl isimlendirildiğini iyice anlayın.

1. Spectrogram Oluşturma - Notebook
    a. Ses dosyalarının spectrogramlarını oluşturun. Kolaylık olması için aşağıdaki fonksiyonu kullanabilirsiniz. create_spectrogram fonksiyonuna, okuduğunuz
    ses dosyasını gönderdiğinizde size hazırlanmış spectrogramı dönecektir.
    
    def create_spectrogram(y):
          spec = librosa.feature.melspectrogram(y=y)
          spec_conv = librose.amplitude_to_db(spec, ref=np.max)
          return spec_conv

    b. Oluşturduğunuz spectrogramları ait olduğu sınıfın klasörüne kaydedin.

2. Önişleme - Notebook
    a. Görüntüleri (spectrogramları) sırasıyla okuyarak, grayscale dönüşümü, resizing ve normalizasyon yapın.
    b. Görüntüleri ait oldukları etiketlerle birlikte, [görüntü, etiket] formatında bir listeye ekleyin.
    c. Bu listeyi kullanarak, X_train, y_train, X_val, y_val, X_test ve y_test veri setlerini oluşturun.
    d. Bu veri setlerini bilgisayarınıza kaydedin.

3. Model Hazırlanması ve Eğitimi - Notebook
    a. Bir CNN modeli hazırlayın.
    b. Modeli hazırlamış olduğunuz veriyi kullanarak eğitin.
    c. Modelin performans metriklerini, loss ve accuracy grafiklerini ekrana yazdırın.
    d. Aldığınız sonuçlara göre hyperparameter optimization yapın.
