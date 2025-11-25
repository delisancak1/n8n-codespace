# n8n Codespace

Bu repo, GitHub Codespaces içinde n8n çalıştırmak üzere hazırlandı. SQLite veritabanı kullanır ve Basic Auth etkinleştirilmiştir.

Özet:
- n8n, docker-compose ile çalışır (port 5678).
- Veritabanı: SQLite (tek dosya, container içinde /home/node/.n8n/database.sqlite).
- Basic Auth default olarak aktif (kullanıcı/parola .env içinde tanımlı).

Hızlı başlangıç
1. .env dosyasını oluşturun:
   cp .env.example .env
   .env içindeki N8N_BASIC_AUTH_USER ve N8N_BASIC_AUTH_PASSWORD değerlerini değiştirin.

2. Codespace açma:
   - GitHub üzerinde "Code" -> "Open with Codespaces" -> Yeni Codespace oluşturun.
   - Codespace açıldığında devcontainer postStartCommand çalışacak ve `docker-compose up -d` komutu ile n8n başlatılacaktır.

3. n8n'e erişim:
   - Forward edilen port: 5678
   - Tarayıcıda: https://<codespace-host>:5678 (Codespaces port yönlendirmesini kullanın)
   - Basic Auth kullanıcı/parola .env içindeki değerlerdir.

Yerel olarak çalıştırma (opsiyonel)
- Eğer lokal makinede docker-compose ile çalıştırmak isterseniz:
  1. cp .env.example .env
  2. docker-compose up -d

Notlar
- docker-compose.yml ve .env.example dosyaları main branch'e eklendi.
- Gerekirse devcontainer.json içine Docker-in-Docker veya farklı base image ekleyebilirsiniz.
