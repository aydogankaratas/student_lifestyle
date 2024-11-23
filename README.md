# student_lifestyle
# Öğrenci Yaşam Biçimi Keşifsel Veri Analizi

Öğrenci yaşam biçimi veri seti, öğrencilerin gün içinde saatlerini hangi aktiviler için ne kadar harcadığını, stres seviyelerini ve başarı notlarını tutan bir veri setidir. Veri setine ulaşmak için aşağıda verilen Kaggle bağlantısını takip edebilir ve değişkenler hakkındaki bilgilere aşağıdan ulaşabilirsiniz.

Öğrenci Yaşam Biçimi Veri Seti: https://www.kaggle.com/datasets/steve1215rogg/student-lifestyle-dataset

**Değişkenler**

* Student_ID : Öğrencilere 1'den başlanarak atanan kimlik numarasıdır.
* Study_Hours_Per_Day: Öğrencilerin gün içerisinde çalışmaya ayırdıkları saat miktarıdır.
* Extracurricular_Hours_Per_Day: Öğrencilerin gün içerisinde ekstra çalışmaya ayırdıkları saat miktarıdır.
* Sleep_Hours_Per_Day: Öğrencilerin gün içerisinde uykuya ayırdıkları saat miktarıdır.
* Social_Hours_Per_Day: Öğrencilerin gün içerisinde sosyal aktiviteye ayırdıkları saat miktarıdır.
* Physical_Activity_Hours_Per_Day: Öğrencilerin gün içerisinde fiziksel aktiviteye ayırdıkları saat miktarıdır.
* GPA: Öğrencilerin başarı notudur.
* Stress_Level: Öğrencilerin bulunduğu stres seviyesidir.

#### Bonus: Kaggle Hesabım
Kaggle: https://www.kaggle.com/aydoankarata

## Temel Bulgular
* Veri seti 8 sütun 2000 kayıt içermektedir.

* Stres seviyesi sütunu object değere sahip kategorik değişken iken diğer sütunlar nümerik değişken olarak tespit edilmiştir.

* Veri setindeki kayıtların %51.4’ü  yüksek stres, %33.7’si orta stres, %14.8’i düşük strese sahiptir.

* Veri setinde eksik veri gözlenmemekle beraber veri setinin kopyasında homojen olarak %3 seviyesinde eksik veri oluşturulup her sütun için uygun teknik ile doldurulmuştur. ( Makine öğrenmesi teknikleri kasıtlı olarak kullanılmadı.)

*  Öğrenciler için ortalama çalışma saati 7.4 , ortalama ekstra çalışma saati 1.9 , ortalama fiziksel aktivite saati 4.3 , ortalama sosyal aktivite saati 2.7 , ortalama uyku saati 7.5 ve ortalama başarı notu 3.1 olarak hesaplandı.

* Stres seviyesine göre gruplandırılan öğrencilerin gün içerisindeki saat kullanım şekli incelendiğinde ;

  - Stres seviyesinin artması ile öğrencilerin çalışma saat aralığının hem minimum seviyesi hem de sahip olduğu aralığın uzunluğunun arttığı gözlemlendi.( Aykırı veriler IQR yöntemi ile gözardı edilerek bu gözlem yapılmıştır.)

  - Yüksek stres seviyesindeki öğrenci grubu için çalışma saatlerinin yüksek saatlerde yoğunlaştığı, uyku saatlerinin düşük saatlerde yoğunlaştığı gözlemlendi.

* Öğrencilerin gün içerisindeki saat kullanım şekli ile başarı notu arasındaki ilişki incelendiğinde ;

  - Öğrencilerin çalışma saati ile başarı notu arasında güçlü ve pozitif bir ilişki olduğu gözlenmesine rağmen öğrenciler stres seviyelerine göre gruplandırıldığında düşük ve orta stres seviyesindeki öğrenciler için böyle bir ilişki biçiminden bahsedemiyoruz. 

  - Öğrencilerin ekstra çalışma saati ile başarı notu arasındaki ilişkinin zayıf olduğu gözlenmekle beraber öğrenciler stres seviyelerine göre gruplandırıldığında da bu ilişki biçimi değişmedi.

  - Öğrencilerin fiziksel aktivite saati ile başarı notu arasında güçlü ve negatif bir ilişki olduğu gözlenmesine rağmen öğrenciler stres seviyelerine göre gruplandırıldığında düşük ve orta stres seviyesindeki öğrenciler için böyle bir ilişki biçiminden bahsedemiyoruz.

* Öğrencilerin fiziksel aktivite saati ile sosyal aktivite, uyku ve çalışma saatleri arasında negatif bir ilişkinin olduğu gözlemlendi. Öğrenciler stres seviyelerine göre gruplandırıldığında ise gün içerisindeki saat harcamaları arasındaki ilişkinin genel öğrenci grubuyla benzer biçimde olduğu gözlemlendi.  
