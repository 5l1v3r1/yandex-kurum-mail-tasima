# Kurumlar için Yandex Mail Hesap Transferi

Bu anlatım; kurumlar için yandex mail'i kullanan domainlerin, başka bir yandex hesabı olan kullanıcıya yetki verilmesini anlatmaktadır.

## Yetki Verme :

Alan adınızdaki e-posta hesaplarının yönetimini (parola oluşturma, silme, değiştirme, vb.) başka birine vermek istiyorsanız bu kişiyi alan adının ek yöneticileri listesine ekleyebilirsiniz. Yalnızca yandex.com.tr alanındaki hesabın yönetimine erişim hakkı verilebilir.

1. Yandex.Mail'e bağlanırken kullandığınız kullanıcı adıyla Alanlarım sayfasına giriş yapın.
2. Tarayıcının penceresine https://api.kurum.yandex.com.tr/get_token.xml?domain_name=alanadi.com.tr girerken alanadi.com.tr kısmını alan adınızla değiştirin.
3. Alınan tokenini kaydedin (token özelliğinin değeri).
4. Tarayıcıya https://api.kurum.yandex.com.tr/api/multiadmin/add_admin.xml?domain=alanadi.com.tr&token=yourtoken&login=adminlogin girerken alanadi.com.tr kısmını alan adınızla, yourtoken kısmını aldığınız tokenle, adminlogin kısmını ise ek yöneticinin kullanıcı adıyla değiştirin. Bu durumda kullanıcı adı, kullanıcının e-posta adresinin ilk kısmından ibaret olur.

Not : Dikkat! Ek yöneticinin kullanıcı adında hata yapmayın, aksi halde başka bir kullanıcıya e-posta hesabı erişimi verebilirsiniz. Alan adı içerisinde alan adı yönetimine erişim hakkı verilemez. Ek yönetici yalnızca Yandex'te yetkili bir kullanıcı adı sahibi olur, alan adı içinde bu kullanıcı adı geçersizdir. Yöntem çağrıldıktan sonra mutlaka alan adına bağlı olduğunuz hesaptan çıkış yapın, ek yönetici kullanıcı adıyla tekrar giriş yapın ve Alanlarım sayfasında alan adının belirip belirmediğini kontrol edin.

## Tüm Yetki Alan Hesapları Listele :

Başka ek yönetici hakkı vermiş olduğunuz kullanıcı adlarının listesini girmek için:

1. Yandex.Mail'e bağlanırken kullandığınız kullanıcı adıyla Alanlarım sayfasına giriş yapın.
2. Tarayıcıya https://api.kurum.yandex.com.tr/api/multiadmin/get_admins.xml?domain=alanadi.com.tr&token=yourtoken girilirken alanadi.com.tr kısmını alan adınızla, yourtoken kısmını ise daha önce aldığınız tokenle değiştirin.


## Yönetici Silme :

Herhangi bir kullanıcı adından ek yönetici haklarını almak için şunları yapmanız gereklidir:

1. Yandex.Mail'e bağlanırken kullandığınız kullanıcı adıyla Alanlarım sayfasına giriş yapın.
2. Tarayıcıya https://api.kurum.yandex.com.tr/api/multiadmin/del_admin.xml?domain=alanadi.com.tr&token=yourtoken&login=adminlogin girerken alanadi.com.tr kısmını alan adınızla, yourtoken kısmını daha önce aldığınız tokenle, adminlogin kısmını ise ek yönetici haklarını almak istediğiniz kullanıcı adıyla değiştirin. Bu durumda kullanıcı adı, kullanıcının e-posta adresinin ilk kısmından ibaret olur.
