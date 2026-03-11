# 👗 Fashion-CLIP Fine-Tuning with DeepFashion

Bu proje, moda dünyası için özel olarak tasarlanmış **Fashion-CLIP** modelinin, DeepFashion veri seti kullanılarak daha spesifik moda kavramlarını tanıyabilmesi için ince ayar (fine-tuning) yapılmış halidir.

## 🚀 Proje Hakkında
Genel yapay zeka modelleri, moda ürünlerindeki kesim, doku ve stil detaylarını her zaman doğru analiz edemeyebilir. Bu çalışma ile:
- Modelin görsel-metin eşleştirme kabiliyeti moda dikeyinde güçlendirilmiştir.
- Contrastive Loss (Kontrastif Kayıp) kullanılarak, doğru açıklamalar ile görseller arasındaki anlamsal mesafe kısaltılmıştır.
- DeepFashion'ın zengin nitelik (attribute) setiyle modelin moda terminolojisi geliştirilmiştir.

## 🛠️ Teknik Özellikler
- **Temel Model:** `patrickjohncyh/fashion-clip`
- **Veri Seti:** DeepFashion (Category & Attribute Prediction)
- **Kütüphaneler:** PyTorch, Transformers, PIL
- **Eğitim Stratejisi:** AdamW Optimizer (Learning Rate: 5e-6)

## 📦 Model Ağırlıkları
Eğitilmiş modelin tüm dosyalarına (safetensors, config, tokenizer) Hugging Face üzerinden ulaşabilirsiniz:
👉 [Yeniekinci/fashion-clip-finetuned](https://huggingface.co/Yeniekinci/fashion-clip-finetuned/tree/main)

## 📊 Örnek Kullanım
Aşağıdaki kod bloğu ile eğitilmiş modeli projenize dahil edebilirsiniz:

```python
from transformers import AutoModel, AutoProcessor

model_path = "Yeniekinci/fashion-clip-finetuned"
model = AutoModel.from_pretrained(model_path)
processor = AutoProcessor.from_pretrained(model_path)
