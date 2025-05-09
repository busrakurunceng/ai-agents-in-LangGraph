## Ders 4: Persistence and Streaming - Mini Notlar

### 🧩 Persistence (Kalıcılık)
- **Amaç**: Agent’in konuşma geçmişini hatırlaması ve çoklu konuşmaları yönetmesi.
- **Araç**: `checkpointer`
  - `SqliteSaver`: Geçici, hafif veri saklama.
  - `Redis`, `PostgreSQL`: Kalıcı çözümler.
- `graph.compile()` içinde `checkpointer` parametresiyle kullanılır.

### 🌊 Streaming (Akış)
#### 1. Mesaj Akışı
- AI mesajları ve araç sonuçları sırayla ekrana yazdırılır.
- `stream()` ile yapılır.

#### 2. Token Akışı
- AI cevabı gerçek zamanlı olarak token token (kelime kelime) gösterilir.
- `astream_events()` fonksiyonu gerekir.
- `AsyncSqliteSaver` kullanılmalıdır.

### 🔗 Thread Config
- Her konuşma için `thread_id` belirlenir.
- Aynı `thread_id`: Konuşma devam eder.
- Farklı `thread_id`: Yeni konuşma başlatılır.

### ✅ Kullanım Alanı
- Çok kullanıcılı sistemler
- Agent belleği olan uygulamalar
- Canlı veri akışı gerektiren senaryolar
