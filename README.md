# Capstone Project – Multi-Task Data Classification & Summarization on Amazon Food Reviews

## 📌 Project Overview
Proyek ini berfokus pada analisis ulasan makanan di Amazon untuk mengidentifikasi **sentimen** sekaligus **aspek utama produk makanan** yang sering muncul dalam review.  
Alih-alih hanya melakukan klasifikasi sederhana, proyek ini menggunakan pendekatan **multi-task** dengan **IBM Granite LLM** melalui **Replicate API**, yang memungkinkan:
- Mengklasifikasikan ulasan menjadi *Positive*, *Neutral/Mixed*, atau *Negative*.  
- Mengidentifikasi aspek spesifik makanan (misalnya: Taste, Freshness, Packaging, Price, Delivery, Portion).  

---

## 🎯 Objectives
1. Melakukan **Exploratory Data Analysis (EDA)** untuk memahami distribusi rating dan sentimen.  
2. Menggunakan **IBM Granite LLM** untuk:  
   - **Multi-task Sentiment & Aspect Classification** → klasifikasi + identifikasi aspek makanan dalam satu langkah.  
   - **Multi-task Summarization** → menghasilkan ringkasan dengan *Pros* dan *Cons*.  
3. Menyusun insight dan rekomendasi yang bermanfaat bagi produsen dan pemasar produk makanan.  

---

## 📂 Dataset
- **Source**: [Kaggle – Amazon Fine Food Reviews](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)  
- **Subset**: 10.000 review digunakan untuk menjaga efisiensi eksekusi di Google Colab.  
- **Fields**:
  - `Text`: Isi ulasan  
  - `Summary`: Ringkasan singkat dari pengguna  
  - `Score`: Rating (1–5)  
  - `Sentiment`: Label hasil pemetaan rating (Positive, Neutral, Negative)  

---

## 🔎 Analysis Process
1. **Data Loading & Cleaning** → memuat dataset, memilih kolom penting, membuang nilai kosong.  
2. **Preprocessing & Labeling** → konversi rating menjadi label sentimen.  
3. **EDA** → histogram distribusi rating, bar chart sentimen, pie chart proporsi sentimen.  
4. **Multi-task Classification with Granite** →  
   - Step 1: Klasifikasi sentimen (Positive / Neutral / Negative).  
   - Step 2: Identifikasi aspek makanan (Taste, Freshness, Packaging, Price, Delivery, Portion) dengan penjelasan singkat.  
5. **Multi-task Summarization with Granite** → ringkasan ulasan dalam format **Pros vs Cons**.  
6. **Insight & Findings** → hasil analisis pola sentimen dan aspek dominan.  
7. **Conclusion & Recommendation** → saran konkrit untuk perbaikan produk & strategi pemasaran.  

---

## 📊 Insight & Findings
- **Mayoritas ulasan bersentimen positif (70%+)**, dengan *Taste* dan *Freshness* paling sering disebutkan sebagai kekuatan.  
- **Aspek negatif utama**: harga (*perceived expensive*) dan kemasan (*packaging issues*).  
- Multi-task Granite membantu menyingkat ulasan panjang menjadi ringkasan *Pros* & *Cons* yang lebih mudah dibaca tim bisnis.  

---

## ✅ Conclusion & Recommendation
- **Conclusion**: IBM Granite sangat efektif untuk multi-task analisis ulasan makanan, menghasilkan insight mendalam tentang sentimen sekaligus aspek produk.  
- **Recommendation**:  
  - Tingkatkan **kemasan** dan pertimbangkan strategi harga agar lebih kompetitif.  
  - Gunakan insight positif (*taste* & *freshness*) untuk strategi pemasaran.  
  - Integrasikan Granite AI ke dalam dashboard monitoring ulasan secara real-time untuk mempercepat respons terhadap feedback pelanggan.  

---

## 🤖 AI Support Explanation
- Model: **IBM Granite 3.3 8B Instruct** (via [Replicate](https://replicate.com/ibm-granite/granite-3.3-8b-instruct)).  
- Digunakan untuk **multi-task classification & summarization**.  
- Prompt disusun agar output konsisten dengan format yang dapat langsung digunakan untuk analisis dan presentasi.  

---

## 🛠️ How to Run
1. Upload `kaggle.json` ke Colab untuk akses dataset.  
2. Set API token Replicate di Colab:
   ```python
   from google.colab import userdata
   api_token = userdata.get('api_token')
   ```
