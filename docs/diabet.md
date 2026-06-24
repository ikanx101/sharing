# Framework Presentasi: Observasi Digital — Persepsi Masyarakat tentang Diabetes

---

## Slide 1 — Judul
**Observasi Digital: Membaca Pikiran Masyarakat dari Data Publik**

> Studi Kasus: Apa yang Ditanyakan Netizen tentang Diabetes?

---

## Slide 2 — Definisi Observasi Digital

**Observasi** tidak selalu harus di lapangan fisik.

Observasi **digital** adalah metode mengamati perilaku, pertanyaan, dan percakapan masyarakat dari jejak digital yang mereka tinggalkan secara sukarela di ruang publik *online*.

**Perbedaan dengan Interview:**
| Observasi Digital | Interview / FGD |
|---|---|
| Data **organik** — responden tidak sadar diamati | Responden sadar dan bisa *performance bias* |
| Menangkap **pertanyaan nyata** yang mengganjal di benak mereka | Menangkap apa yang **mereka ingat** atau **mau** ceritakan |
| Bisa dalam skala besar (ratusan ribu) | Terbatas jumlah partisipan |
| **Tidak ada tanya jawab** — peneliti hanya mengamati jejak digital | Ada interaksi langsung |

---

## Slide 3 — Cerita Latar

> *"Jujurly, sebelum masuk Nutrifood, saya benar-benar blank sama sekali terkait apa itu penyakit diabetes."*

Beberapa tahun berselang → ibu saya seorang diabetesi.

**Masuk Nutrifood** — edukasi diabetes sudah sangat kencang dan masif.

**Pertanyaan riset:**
> *"Bagaimana dengan masyarakat awam yang masih jarang terpapar edukasi diabetes? Pengetahuan mereka seperti apa?"*

Bukan lewat interview — tapi dengan **mengamati pertanyaan-pertanyaan yang mereka tulis sendiri di internet.**

---

## Slide 4 — Sumber Data & Metode

**Sumber:** [Alodokter.com](https://www.alodokter.com/komunitas/diskusi/penyakit) — forum tanya jawab dengan dokter.

**Topik:** 6 topik spesifik terkait diabetes.

**Tools:** 
- *Web scraping* via **thescraper.id** (karya Mas Apriandito — rekan sesama AIDI)
- Total: **446 pertanyaan unik** terkumpul

**Objek Analisis:** Judul pertanyaan — karena sudah merupakan **intisari** dari isi pertanyaan.

---

## Slide 5 — Alur Analisis

```
446 Judul Pertanyaan
        ↓
  Hapus stopwords Bahasa Indonesia
        ↓
       Bigrams
        ↓
  Embedding via Sentence Transformer (LLM)
        ↓
  Matriks jarak 446×446
        ↓
  Reduksi dimensi: t-SNE (non-linear)
        ↓
  Hierarchical Clustering
        ↓
     22 Clusters Pertanyaan
        ↓
  Summarization per Cluster via LLM
```

---

## Slide 6 — Bigrams: Gambaran Awal

**Bigrams** yang dominan dari judul pertanyaan:

| Pasangan Kata | Indikasi Topik |
|---|---|
| Gula darah | Kadar normal, cara turunkan, cek |
| Diabetes melitus | Definisi, tipe-tipe |
| Suntik insulin | Pengobatan lanjutan |
| Kaki bengkak | Komplikasi |
| Berat badan | Hubungan dengan diabetes |
| Efek samping | Obat-obatan |
| Kencing manis | Istilah awam |
| Makanan/minuman | Apa yang aman dikonsumsi |

---

## Slide 7 — 22 Clusters: Peta Pertanyaan Netizen

Dari 22 clusters yang terbentuk, setelah diringkas muncul tema-tema besar:

1. **Makanan & Minuman** (Clusters 1, 4, 9, 22) — buah aman, minuman penurun gula, susu untuk diabetesi, efek kopi/teh
2. **Definisi & Jenis Diabetes** (Clusters 2, 13, 18) — tipe 1 vs tipe 2, diabetes basah vs kering, prediabetes
3. **Pengobatan & Insulin** (Clusters 3, 5, 6, 8) — metformin, suntik insulin, obat herbal, cara pakai, efek samping
4. **Gejala & Diagnosis** (Clusters 7, 8, 12, 15, 19) — sering BAK, haus, lemas, kadar gula normal, HbA1c
5. **Komplikasi** (Clusters 10, 14, 20, 21) — luka diabetes, kaki bengkak, amputasi, gatal, gangguan ginjal
6. **Kehamilan & Reproduksi** (Clusters 11, 16) — diabetes gestasional, kesuburan, kehamilan
7. **Perawatan Kaki & Kulit** (Clusters 14, 20, 21) — luka, bengkak, gatal, kulit menghitam

---

## Slide 8 — Temuan Menarik

**Apa yang dominan?**

- **Makanan & Minuman** — paling banyak. Masyarakat masih sangat fokus ke "apa yang boleh/tidak boleh dimakan."
- **Gejala & Diagnosis** — kedua terbanyak. Banyak yang baru curiga diabetes dan mencari konfirmasi.

**Apa yang jarang?**

- **Komplikasi jangka panjang** — hanya sedikit yang bertanya soal gagal ginjal, neuropati, atau amputasi.
- **Manajemen mandiri** — cara monitoring harian, adjustment dosis, gaya hidup jangka panjang.

**Interpretasi:** Sebagian besar pertanyaan bersifat **general**. Pertanyaan yang sangat spesifik dan mendalam hanya sedikit. Ini mengindikasikan **masih banyak masyarakat yang perlu diedukasi lebih jauh** tentang diabetes.

---

## Slide 9 — Insight Kunci untuk Bisnis & Edukasi

1. **Kebutuhan dasar:** Masyarakat masih di tahap pengenalan — apa itu diabetes, apa yang boleh dimakan.
2. **Gap edukasi:** Komplikasi dan manajemen jangka panjang hampir tidak tersentuh — peluang besar untuk campaign edukasi.
3. **Kata kunci dominan:** "Gula darah", "makanan", "obat" — konten edukasi sebaiknya berbasis kata kunci ini.
4. **Kekhawatiran:** Efek samping obat (metformin, insulin) — banyak yang takut — perlu reassurance.
5. **Produk spesifik:** Susu untuk diabetesi (Cluster 22) — peluang produk yang sudah ada atau akan dikembangkan.

---

## Slide 10 — Mengapa Observasi Digital Lebih Tepat di Sini?

Kalau riset ini pakai **interview/FGD**:
- Responden mungkin **malu** mengakui ketidaktahuannya.
- Mereka bisa **overclaim**: "Oh saya tahu diabetes..." padahal tidak.
- Terbatas jumlah partisipan (maksimal 20-30 orang).

**Dengan observasi digital:**
- 446 pertanyaan **autentik** dari orang yang benar-benar punya masalah.
- Tidak ada *social desirability bias* — mereka jujur menuliskan kebingungannya.
- Cakupan jauh lebih luas.
- **Tidak ada tanya jawab** — peneliti hanya mengamati dan menganalisis jejak digital yang sudah ada.

---

## Slide 11 — Kesimpulan

**Observasi digital** adalah metode riset yang:
- Memanfaatkan data publik yang sudah tersedia di internet
- Menangkap suara masyarakat yang **tidak terfilter**
- Bisa dilakukan dalam skala besar dengan biaya relatif kecil
- Sangat cocok untuk riset eksploratori sebelum menentukan arah strategi

**Contoh riset ini membuktikan:**
> Dari 446 pertanyaan netizen, kita bisa memetakan **apa yang sebenarnya masyarakat pikirkan dan khawatirkan** tentang diabetes — bukan apa yang kita *kira* mereka pikirkan.

Hasilnya bisa langsung digunakan sebagai landasan:
- Campaign edukasi yang tepat sasaran
- Strategi konten yang menjawab kebutuhan nyata
- Pengembangan produk yang sesuai dengan *pain point* konsumen
