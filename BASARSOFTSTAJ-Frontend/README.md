
# Basarsoft Stajyerlik Projesi 

**12/08/2024 - 24/09/2024 tarihleri arasında Başarsoft Bilgi Teknolojileri (www.basarsoft.com.tr) şirketinde tamamlamış olduğum stajımın frontend kodlarının bulunduğu yerdesiniz.**

Kullandığım openlayers (https://openlayers.org/) kütüphanesi sayesinde veritabanında kayıtlı halde bulunan WKT(Well Known Text) formatında bulunan stringi haritamızda nokta(point), çizgi(line) ve alan(polygon) şekilinde gösterebilmemiz için gerekli frontend kodlarını içermektedir.

Projede Asp.Net v8.0 Web API, Entity Framework, PostgreSQL teknolojileri kullanılmıştır.

Arayüzde responsive bir tasarım kullanılmış olup navbar(navigasyon çubuğu/barı) tasarımı ekranın altına haritanın üzerine konumlandırılmıştır. İçerisinde Nokta, çizgi ve alan ekleme butonları ve listeleme butonları bulunmaktadır. 

Harita ilk yüklendiğinde Türkiye sınırlarını içerisine alacak şekilde zoomlanmış ve cookie'den tema kontrolü yapılarak yüklenmektedir. Sağ üste göründüğü üzere 2 buton bulunmaktadır. Bu butonlardan üstteki dark mode / light mode değişiklik butonu, alttaki ise haritadal, herhangi bir yakınlaştırma, hareket işleminden sonra tek tık ile ana görünüme dönmeyi kolaylaştırmak için eklenmiştir.

**•Nokta Ekleme butonuna basıldığında** mouse imleci crosshaire dönmekte ve işaretlenmek istenilen noktaya basıldığında o noktanın koordinatlarını alıp animasyonlu zoom işlemi ile birlikte bir popup açılmaktadır. popup içerisine o noktaya verilmek istenen ad girildikten sonra kaydet butonuna basıldıktan sonra api post işlemi gerçekleşmekte ve haritaya özelleştirilmiş lokasyon simgesi koyulmaktadır. Artık o nokta database'de wkt formatında bulunmakta ve sayfa her yenilendiğinde fetch işlemi yapılarak haritaya işaretlenmektedir.

**•Alan Ekleme butonuna basıldığında** mouse imleci crosshaire dönmekte ve işaretlenmek istenilen alanın ilk noktasına basıldığında mouse nereye çekilirse oraya doğru bir kenar çıkmakta ve ilk basılan noktaya dönene kadar o alan ortaya çıkmatadır. İlk noktaya geri dönüldüğünde alan tamamlanmakta ve bir jspanel ortaya çıkmatadır. Bu panelde kullanıcıdan alan için bir isim alınmaktadır. O alana verilmek istenen ad girildikten sonra kaydet butonuna basıldıktan sonra api post işlemi gerçekleşmekte ve haritaya o alan eklenmektedir. Artık o alan database'de wkt formatında bulunmakta ve sayfa her yenilendiğinde fetch işlemi yapılarak haritaya işaretlenmektedir.

**•Çizgi Ekleme butonuna basıldığında** mouse imleci crosshaire dönmekte ve işaretlenmek istenilen çizginin ilk noktasına basıldığında mouse nereye çekilirse oraya doğru bir kenar çıkmakta ve çift tık yapılana kadar o çizgi ortaya çıkmatadır. Çİft tıklandığında çizgi tamamlanmakta ve bir jspanel ortaya çıkmatadır. Bu panelde kullanıcıdan çizgi için bir isim alınmaktadır. O çizgiye verilmek istenen ad girildikten sonra kaydet butonuna basıldıktan sonra api post işlemi gerçekleşmekte ve haritaya o çizgi eklenmektedir. Artık o çizgi database'de wkt formatında bulunmakta ve sayfa her yenilendiğinde fetch işlemi yapılarak haritaya işaretlenmektedir.

**•Listeleme butonuna basıldığında** bir jspanel açılmakta ve databaseden tüm featurelar çekilmektedir. Datatables kullanılarak tüm veriler tabloya işlenmektedir ilk sutünda feature ismi ikinci sutünda wkt stringi üçüncü sutünda ise 3 işlemin bulunduğu işlemler sutünü bulunmaktadır. Sağ üste arama butonu bulunmakta ve çok hızlı reaksiyonla aktif olarak çalışmaktadır.  

**•Haritadan herhangi bir feature'a basıldığında veya listelemeden göster butonuna basıldığında** o feature ekrana animasyonlu bir şekilde ortalanmakta ve bir jspanel açılmaktadır. Her feature'ın kendi özelliğine göre bilgiler yazmaktadır. Nokta için sadece ismi ve wkt stringi, çizgi için noktadan ekstra olarak çizgi uzunluğunun km cinsinde ölçülmüş hali, alan için ise noktadan farklı olarak o alanın kaç kilometrekare olduğu bilgisi çıkmaktadır. Ayrıca her panelde silme ve düzenleme işlemleri için butonlar bulunmaktadır. Manuel olarak stringi ve adı değiştirebilmekteyiz. Harita kullanılarak ise kenar kaydırma, sürükleme, uzatma, genişletme, kısaltma, küçültme vb. işlemleri kolaylıkla halledebilmekteyiz.

Staj süresi boyunca bana desteklerini sunan Başarsoft ailesine teşekkürlerimi sunar, iyi günler dilerim.
