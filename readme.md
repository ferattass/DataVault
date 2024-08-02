# DataVault

DataVault, kullanıcıların veritabanı yönetimi yapmasına olanak sağlayan bir Flask uygulamasıdır. Bu proje, kullanıcıların kayıt olmasını, giriş yapmasını ve çeşitli veritabanı öğelerini (items) yönetmelerini sağlar.

## Proje Yapısı

DataVault/
├── app/
│ ├── init.py
│ ├── models.py
│ ├── routes.py
│ ├── config.py
│ ├── extensions.py
│ └── auth.py
├── migrations/
├── tests/
├── .env
├── run.py
└── requirements.txt

markdown


## Kurulum

### Gereksinimler

- Python 3.8+
- pip

### Adımlar

1. **Depoyu Klonlayın:**

```bash
git clone https://github.com/yourusername/DataVault.git
cd DataVault
Gerekli Paketleri Yükleyin:
bash

pip install -r requirements.txt
Çevre Değişkenlerini Ayarlayın:
.env dosyasını oluşturun ve aşağıdaki değişkenleri ekleyin:

makefile

SECRET_KEY=mysecretkey
DATABASE_URL=sqlite:///app.db
JWT_SECRET_KEY=myjwtsecret
Veritabanı Migrations Oluşturun ve Uygulayın:
bash

flask db init
flask db migrate -m "Initial migration."
flask db upgrade
Uygulamayı Başlatın:
bash

python run.py
Kullanım
Kayıt Olma
POST /register

Gönderilecek JSON:

json

{
    "username": "yourusername",
    "email": "youremail@example.com",
    "password": "yourpassword"
}
Giriş Yapma
POST /login

Gönderilecek JSON:

json

{
    "username": "yourusername",
    "password": "yourpassword"
}
Item'ları Listeleme
GET /items

JWT token gerektirir.

Yeni Item Oluşturma
POST /items

Gönderilecek JSON:

json

{
    "name": "Item Name",
    "description": "Item Description"
}
JWT token gerektirir.

Item Güncelleme
PUT /items/<id>

Gönderilecek JSON:

json

{
    "name": "Updated Item Name",
    "description": "Updated Item Description"
}
JWT token gerektirir.

Item Silme
DELETE /items/<id>

JWT token gerektirir.

Katkıda Bulunma
Katkıda bulunmak isterseniz, lütfen bir fork yapın ve bir pull request gönderin. Her türlü katkıya açığız!

Lisans
Bu proje MIT Lisansı altında lisanslanmıştır. Daha fazla bilgi için LICENSE dosyasına bakın.

css


Bu içeriği `README.md` dosyasına yapıştırabilirsiniz. Başka bir yardıma ihtiyacınız olursa lüt