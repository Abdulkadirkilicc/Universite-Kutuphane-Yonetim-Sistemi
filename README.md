# Üniversite Kütüphane Yönetim Sistemi

Bu proje, bir üniversite kütüphanesinin işleyişini yönetmek için geliştirilmiş bir **Kütüphane Yönetim Sistemi** yazılımıdır. Kullanıcılar kitap arayabilir, ödünç alabilir, iade edebilir ve yöneticiler kütüphane envanterini yönetebilir.

## **Katkıda Bulunanlar**
- Adi Hidayat (https://github.com/AdiDayat12)

## **Projenin Özellikleri**

### **Genel Özellikler**
- Kullanıcılar (öğrenciler ve yöneticiler) için giriş ve kayıt işlemleri.
- Kitapların ödünç alınması, iade edilmesi ve durumlarının takibi.
- Kitap adına, yazara ve yayınevine göre arama işlemleri.
- Yönetici paneli üzerinden kitap ve kullanıcı yönetimi.

### **Kullanılan Teknolojiler**
- **Java**: Uygulama geliştirme.
- **Postrgre SQL**: Veritabanı yönetimi.
- **Swing**: Grafiksel kullanıcı arayüzü (GUI).

### **Tasarım Desenleri**
1. **Singleton Pattern**: Veritabanı bağlantısı (`DBConnection`) ve oturum yönetimi (`UserSession`).
2. **Factory Pattern**: Kullanıcı türlerine göre nesne oluşturma (`UserFactory`).
3. **State Pattern**: Kitapların durum yönetimi (`AvailableState`, `OutOfStock`).
4. **Builder Pattern**: Kitap nesnesi oluşturma (`Book` sınıfında).
5. **Observer Pattern**: Kitap durumu değiştiğinde kullanıcıya bildirim gönderme.

---

## **Kurulum ve Çalıştırma**

### **Gereksinimler**
- **Java 8** veya üzeri
- **Postgre SQL**

### **Adımlar**
1. **Projenin Klonlanması**
   ```bash
   git clone https://github.com/Abdulkadirkilicc/Universite-Kutuphane-Yonetim-Sistemi.git
   cd universite-kutuphane-yonetim-sistemi
   ```

2. **MySQL Veritabanı Kurulumu**
   - MySQL'de aşağıdaki komutları çalıştırarak veritabanını oluşturun:
     ```sql
     CREATE DATABASE library_management_system;
     USE library_management_system;

     -- Tablo oluşturma sorguları için `database_schema_mysql` dosyasını kullanın.
     ```

3. **Projenin Derlenmesi ve Çalıştırılması**
   - Eğer bir IDE kullanıyorsanız (IntelliJ IDEA, Eclipse):
     1. Projeyi açın.
     2. Ana sınıfı (`Main.java`) çalıştırın.

   - Eğer terminal kullanıyorsanız:
     ```bash
     javac -d out src/com/grup31/universite_kutuphane_yonetim_sistemi/Main.java
     java -cp out com.grup31.universite_kutuphane_yonetim_sistemi.Main
     ```

---

## **Projenin Özellikleri (Detaylı)**

### **Giriş ve Kayıt İşlemleri**
- Kullanıcılar (öğrenci ve yönetici) sisteme kayıt olabilir ve giriş yapabilir.
- Giriş yapıldıktan sonra, kullanıcı türüne göre yetkilendirme gerçekleştirilir:
  - **Öğrenci**: Kitap arama, ödünç alma ve iade etme gibi temel işlemleri gerçekleştirebilir.
  - **Yönetici**: Kitap ekleme, güncelleme ve silme işlemlerinin yanı sıra kullanıcı yönetimi yapabilir.

### **Kitap Yönetimi**
- **Yönetici Yetkileri**:
  - Yeni kitap ekleyebilir.
  - Mevcut kitap bilgilerini güncelleyebilir (örneğin, stok durumu veya yayın yılı).
  - Kütüphaneden kitap silebilir.
- **Öğrenci Yetkileri**:
  - Kitap arayabilir (kitap adı, yazarı veya yayınevine göre).
  - Mevcut kitapları ödünç alabilir.
  - Ödünç alınan kitapları zamanında iade edebilir veya gecikme durumunda ceza işlemleriyle karşılaşabilir.

### **Raporlama**
- **Yönetici Paneli**:
  - Tüm ödünç alma işlemleri detaylı olarak görüntülenebilir.
  - Kullanıcıların ödünç aldığı kitapların listesini inceleyebilir.
  - Kitapların durumu (rafta, ödünçte, kayıp) hakkında rapor oluşturabilir.
- **Öğrenci Paneli**:
  - Öğrenciler, kendi ödünç aldıkları kitapların geçmişini ve durumunu görebilir.

---

---

## **Lisans**
Bu proje MIT Lisansı altında lisanslanmıştır. Daha fazla bilgi için LICENSE dosyasını inceleyin.

