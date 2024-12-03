# Öğrenci Yaşam Biçimi Keşifsel Veri Analizi
<img src="dataset-cover.jpg" alt="Resim Açıklaması" width="990" height="500" />


Öğrenci yaşam biçimi veri seti, öğrencilerin gün içinde saatlerini hangi aktiviler için ne kadar harcadığını, stres seviyelerini ve başarı notlarını tutan bir veri setidir. Veri setine ulaşmak için aşağıda verilen Kaggle bağlantısını takip edebilir ve değişkenler hakkındaki bilgilere aşağıdan ulaşabilirsiniz.

Öğrenci Yaşam Biçimi Veri Seti: [Student-Lifestyle](https://www.kaggle.com/datasets/steve1215rogg/student-lifestyle-dataset)

Bonus: Kaggle Hesabım [Aydoğan Karataş](https://www.kaggle.com/aydoankarata)

#### Değişkenler

* `Student_ID`: Öğrencilere 1'den başlanarak atanan kimlik numarasıdır.
* `Study_Hours_Per_Day`: Öğrencilerin gün içerisinde çalışmaya ayırdıkları saat miktarıdır.
* `Extracurricular_Hours_Per_Day`: Öğrencilerin gün içerisinde ekstra çalışmaya ayırdıkları saat miktarıdır.
* `Sleep_Hours_Per_Day`: Öğrencilerin gün içerisinde uykuya ayırdıkları saat miktarıdır.
* `Social_Hours_Per_Day`: Öğrencilerin gün içerisinde sosyal aktiviteye ayırdıkları saat miktarıdır.
* `Physical_Activity_Hours_Per_Day`: Öğrencilerin gün içerisinde fiziksel aktiviteye ayırdıkları saat miktarıdır.
* `GPA`: Öğrencilerin başarı notudur.
* `Stress_Level`: Öğrencilerin bulunduğu stres seviyesidir.


## Veri Setinin Hazırlanması

#### Eksik Verilerin Yönetilmesi

Veri setinde eksik veri gözlenmemekle beraber veri setinin kopyasında homojen olarak %3 seviyesinde eksik veri oluşturulup her sütun için uygun teknik ile doldurulmuştur. ( Makine öğrenmesi teknikleri kasıtlı olarak kullanılmadı.)

Veriler veri setinde bir yerde kümelenmişse, örneğin belirli bir sütunda, o zaman verinin silinmesi düşünülebilirdi. Ancak elimdeki veri setinde eksik değerler homojen bir şekilde dağılmış durumda, bu yüzden eksik verileri uygun tekniklerle doldurmak daha iyi bir çözümdür. Aksi taktirde önemli miktarda veri kaybı riskiyle karşılaşılır.

**Sayısal Sütunlar:**
* `Student_ID` sutünunun sahip olduğu ardışık yapıdan dolayı eksik veriyi bir önceki verinin bir fazlası şeklinde dolduruldu.

* `Sleep_Hours_Per_Day`, `Study_Hours_Per_Day`, `Extracurricular_Hours_Per_Day` sütunlarının dağılımından kaynaklı ve aldığı verileri göz önüne alındığında doldurma şekli önce her sütun için uygun seriler yaratılıp ardından serideki değerleri eşit oranda rastgele olarak eksik verilere dağıtarak dolduruldu.

* `Social_Hours_Per_Day`, `Physical_Activity_Hours_Per_Day` sütunlarının dağılımından kaynaklı medyan ile dolduruldu.

* `GPA` sütununun sahip olduğu dağılımın simetrik olmasından dolayı ortalama ile eksik verileri dolduruldu.

**Kategorik Sürunlar:**
* `Stress_Level` sütunu için eksik veriyi, dolu verinin oransalığı hesaplanıp bu oranlamaya göre kategorik veriler rastgele dağıtılarak dolduruldu.


## Temel Bulgular

* Veri seti 8 sütun 2000 kayıt içermektedir.

* Stres seviyesi sütunu object değere sahip kategorik değişken iken diğer sütunlar nümerik değişken olarak tespit edilmiştir.

* Öğrenciler için ortalama çalışma saati 7.4 , minimum çalışma saati 5 iken  maksimum çalışma saati 10 olarak görülmüştür. Ortalama ekstra çalışma saati ise 1.9 , minimum ekstra çalışma saati 0, maksimum ekstra çalışma saati 4 olarak görülmüştür.

* Öğrenciler için ortalama fiziksel aktivite saati 4.3 ,minimum fiziksel aktivite saati 0 iken  şaşırtıcı şekilde maksimum fiziksel aktivite saati 13 olarak görülmekle beraber 2.5 değeri ile en yüksek standart sapmaya sahip sütundur. Ortalama sosyal aktivite saati ise 2.7 , minimum sosyal aktivite saati 0, maksimum sosyal aktivite saati 6 olarak görülmüştür.

* Öğrenciler için ortalama uyku saati 7.5, minimum uyku saati 5 iken  maksimum uyku saati 10 olarak görülmüştür.

* Öğrenciler için ortalama başarı notu 3.1,minimum başarı notu 2.24 iken  maksimum başarı notu 4.00 olarak görülmekle beraber 0.29 değeri ile en düşük standart sapmaya sahip sütundur.
  
* Veri setindeki kayıtların %51.4’ü  yüksek stres, %33.7’si orta stres, %14.8’i düşük strese sahiptir.

**Stres seviyesine göre gruplandırılan öğrencilerin gün içerisindeki saat kullanım şekli incelendiğinde ;**

* Stres seviyesinin artması ile öğrencilerin çalışma saat aralığının hem minimum seviyesi hem de sahip olduğu aralığın uzunluğunun arttığı gözlemlendi.( Aykırı veriler IQR yöntemi ile gözardı edilerek bu gözlem yapılmıştır.)

* Yüksek stres seviyesindeki öğrenci grubu için çalışma saatlerinin yüksek saatlerde yoğunlaştığı, uyku saatlerinin düşük saatlerde yoğunlaştığı gözlemlendi.
  > Burada yüksek stres seviyesindeki öğrencilerin en karakteristik ve dikkat çekici özelliğini gözlemliyoruz.

**Öğrencilerin gün içerisindeki saat kullanım şekli ile başarı notu arasındaki ilişki incelendiğinde ;**

* Öğrencilerin çalışma saati ile başarı notu arasında güçlü ve pozitif bir ilişki olduğu gözlenmesine rağmen öğrenciler stres seviyelerine göre gruplandırıldığında düşük ve orta stres seviyesindeki öğrenciler için böyle bir ilişki biçiminden bahsedemiyoruz.
  > Yüksek stres seviyesindeki öğrencilerin başarılarının güçlü bir şekilde çalışma saati ile ilişkili olması ve diğer gruplarda bunun gözlenmemesi öğrencilerin davranışlarında şartlandırılma biçimlerinin çok etkili olduğu rahatlıkla gözlemlenebiliniyor. Biraz daha açmam gerekirse yüksek stres seviyesindeki öğrenciler empoze edilmeye en fazla uğrayan kişiler olmasından kaynaklı (bu benim hipotezimdir) şartlanmaya sahip olma eğiliminde olucaklardır. Bunun başarı şekillerine dahi etki ettiğini gözlemliyoruz.

* Öğrencilerin ekstra çalışma saati ile başarı notu arasındaki ilişkinin zayıf olduğu gözlenmekle beraber öğrenciler stres seviyelerine göre gruplandırıldığında da bu ilişki biçimi değişmedi.

* Öğrencilerin fiziksel aktivite saati ile başarı notu arasında güçlü ve negatif bir ilişki olduğu gözlenmesine rağmen öğrenciler stres seviyelerine göre gruplandırıldığında düşük ve orta stres seviyesindeki öğrenciler için böyle bir ilişki biçiminden bahsedemiyoruz.
  > Yukarıda bahsettiğim durumla ilişkilendiriyorum yani toplumda hakim olan söylem ve kanı, yüksek stres seviyesindeki öğrenciler üzerinde çok etkili olduğu düşüncesine varıyorum.

**Öğrencilerin gün içerisindeki saat kullanım şekillerin birbirleriyle ilişkisi incelendiğinde ;**

* Öğrencilerin fiziksel aktivite saati ile sosyal aktivite, uyku ve çalışma saatleri arasında negatif bir ilişkinin olduğu gözlemlendi. Öğrenciler stres seviyelerine göre gruplandırıldığında da bu ilişki gözlemlendi.
  > Buradan özellikle sosyal aktive, uyku saati ve çalışma saati ile diğer aktiviteler arasında güçlü bir ilişki bulunmamışken fiziksel aktivitenin diğer aktivitelerle arasında  negatif güçlü bir ilişkiye sahip olmuş olması, fiziksel aktivitenin diğer aktivitelere karşı daha hegemonik bir karaktere sahip olduğunu göstermekle beraber bu karakter daha ayrıntılı incelenebilir.

* Öğrenciler stres seviyelerine göre gruplandırıldığında ise gün içerisindeki saat harcamaları arasındaki ilişkinin genel öğrenci grubuyla benzer biçimde olduğu gözlemlendi.  
