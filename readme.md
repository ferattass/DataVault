DataVault
DataVault, kullanıcıların veritabanı yönetimi yapmasına olanak sağlayan bir Flask uygulamasıdır. Bu proje, kullanıcıların kayıt olmasını, giriş yapmasını ve çeşitli veritabanı öğelerini (items) yönetmelerini sağlar.
Proje Yapısı
DataVault/
│
├── app/
│   ├── __init__.py
│   ├── models.py
│   ├── routes.py
│   ├── config.py
│   ├── extensions.py
│   ├── auth.py
│
├── migrations/
├── tests/
│
├── .env
├── run.py
├── requirements.txt

Kurulum
Gereksinimler
- Python 3.8+
- pip
Adımlar
1. Depoyu Klonlayın:
```bash
git clone https://github.com/ferattass/DataVault.git
cd DataVault
```
2. Gerekli Paketleri Yükleyin:
```bash
pip install -r requirements.txt
```
3. Çevre Değişkenlerini Ayarlayın:
.env dosyasını oluşturun ve aşağıdaki değişkenleri ekleyin:
```
SECRET_KEY=mysecretkey
DATABASE_URL=sqlite:///app.db
JWT_SECRET_KEY=myjwtsecret
```
4. Veritabanı Migrations Oluşturun ve Uygulayın:
```bash
flask db init
flask db migrate -m "Initial migration."
flask db upgrade
```
5. Uygulamayı Başlatın:
```bash
python run.py
```
Kullanım
Kayıt Olma
**Endpoint:** `POST /register`
**Gönderilecek JSON:**
```json
{
  "username": "yourusername",
  "email": "youremail@example.com",
  "password": "yourpassword"
}
```
Giriş Yapma
**Endpoint:** `POST /login`
**Gönderilecek JSON:**
```json
{
  "username": "yourusername",
  "password": "yourpassword"
}
```
Item'ları Listeleme
**Endpoint:** `GET /items`
**Not:** JWT token gerektirir.
Yeni Item Oluşturma
**Endpoint:** `POST /items`
**Gönderilecek JSON:**
```json
{
  "name": "Item Name",
  "description": "Item Description"
}
```
**Not:** JWT token gerektirir.
Item Güncelleme
**Endpoint:** `PUT /items/<id>`
**Gönderilecek JSON:**
```json
{
  "name": "Updated Item Name",
  "description": "Updated Item Description"
}
```
**Not:** JWT token gerektirir.
Item Silme
**Endpoint:** `DELETE /items/<id>`
**Not:** JWT token gerektirir.
Katkıda Bulunma
Katkıda bulunmak isterseniz, lütfen bir fork yapın ve bir pull request gönderin. Her türlü katkıya açığız!
Lisans
Bu proje MIT Lisansı altında lisanslanmıştır. Daha fazla bilgi için LICENSE dosyasına bakın.
