# Moodify: Mengungkap Persona Musik Personal dengan Analisis Data Spotify dan AI

## 1. Project Overview

Proyek ini bertujuan untuk melampaui analisis musik standar dengan menggali lebih dalam ke dalam konteks emosional dan persona di balik kebiasaan mendengarkan seorang pengguna Spotify. Masalah utamanya adalah rekomendasi musik seringkali terasa generik karena hanya melihat apa yang didengar, bukan mengapa.

Moodify mengatasi ini dengan:

Menganalisis data riwayat mendengarkan, playlist, dan genre favorit pengguna.

Melakukan klasifikasi mood secara dinamis berdasarkan nama playlist yang dibuat oleh pengguna sendiri, yang mencerminkan niat dan konteks asli mereka.

Menggunakan Large Language Model (LLM) seperti IBM Granite untuk menganalisis data terstruktur dan menghasilkan ringkasan naratif, wawasan mendalam, serta rekomendasi yang dipersonalisasi.

Pendekatan ini mengubah data kuantitatif menjadi sebuah cerita kualitatif tentang identitas musik seseorang.

## 2. Raw Dataset Link

Dataset yang digunakan dalam proyek ini bersifat dinamis dan privat, dihasilkan secara real-time untuk setiap pengguna yang menjalankan skrip melalui Spotify Web API. Oleh karena itu, tidak ada tautan ke dataset mentah yang statis.

Data mentah yang diambil meliputi:

50 lagu teratas pengguna `/v1/me/top/tracks`

Semua playlist milik pengguna `/v1/me/playlists`

Genre dari setiap artis terkait `/v1/artists`

Proses pengambilan dan pengolahan data ini dapat dilihat dan dijalankan melalui notebook Google Colab berikut:

Tautan Notebook: [disini](https://colab.research.google.com/drive/1Vb_V-KdTW3up6q3hkL9BYwGjyYJXA_rp?usp=sharing)

## 3. Insight & Findings

Analisis dari data pengguna, yang diinterpretasikan oleh IBM Granite, menghasilkan beberapa temuan kunci mengenai persona dan perilaku musik mereka:

Persona Insight
Identitas musik pengguna berpusat pada genre Emo dan Pop Punk, menunjukkan kecintaan pada lirik yang introspektif dan musik berbasis gitar. Terdapat keseimbangan dengan trek dansa berenergi tinggi (Hardstyle, Jersey Club) dan apresiasi terhadap musik dari berbagai budaya (Pop Indonesia, Melayu, K-Pop). Penggunaan playlist dengan tema personal menunjukkan keinginan untuk mengekspresikan individualitas.

Listening Mood Breakdown
Emo/Pop Punk (Introspektif & Emosional): Mood ini paling dominan, terlihat dari lagu dan artis teratas. Musik ini digunakan untuk ekspresi emosional yang mendalam.

Energetic & Dance-Oriented: Kehadiran genre Hardstyle, Jersey Club, dan Phonk menunjukkan kebutuhan akan musik berenergi tinggi untuk membangkitkan semangat, percaya diri, atau sebagai katarsis.

Indonesian/Malay Pop (Kultural & Ceria): Mood ini mencerminkan koneksi kultural, nostalgia, atau sekadar kegembiraan yang didapat dari lagu-lagu yang familiar dan ceria.

Music Behavior Patterns
Ekspresi Diri: Playlist dengan tema personal ('This playlist is literally me') menunjukkan musik digunakan sebagai alat untuk mengekspresikan identitas.

Keterbukaan Budaya: Apresiasi terhadap genre dari berbagai negara (Indonesia, Melayu, Korea) menandakan selera musik yang beragam dan terbuka.

Penjelajah Niche: Ketertarikan pada genre seperti Phonk dan Drift Phonk menunjukkan semangat petualang dalam menemukan subkultur musik baru.

## 4. AI Support Explanation

Peran AI (IBM Granite) dalam proyek ini bukan sebagai alat klasifikasi data mentah, melainkan sebagai Inference and Summarization Engine tingkat lanjut.

Alur kerjanya adalah sebagai berikut:

Analisis Terprogram (Python & Pandas): Skrip Python melakukan semua pekerjaan berat: mengambil data dari API, membersihkannya, melakukan klasifikasi dinamis berdasarkan nama playlist, dan menghitung metrik kuantitatif (frekuensi, genre teratas, artis favorit, dll).

Pembuatan Ringkasan Terstruktur: Hasil dari langkah pertama diformat menjadi sebuah laporan teks yang padat dan terstruktur. Laporan ini berfungsi sebagai prompt yang kaya konteks untuk AI.

Analisis Kualitatif (IBM Granite): LLM menerima laporan terstruktur tersebut dan melakukan tiga tugas utama:

Menafsirkan (Interpret): Membaca data kuantitatif dan menyimpulkan makna di baliknya (misalnya, frekuensi playlist '🤫🧏♂️🎧🏋️♀️' yang tinggi menandakan musik sebagai outlet semangat).

Menceritakan (Narrate): Mengubah kumpulan data menjadi sebuah cerita yang koheren tentang persona, kebiasaan, dan mood musik pengguna.

Memberi Rekomendasi Cerdas: Memberikan saran yang kreatif dan relevan (jangka pendek, menengah, panjang) berdasarkan interpretasi tersebut.

Pendekatan ini secara efektif memisahkan tugas analisis kuantitatif (yang paling baik dilakukan oleh kode) dari analisis kualitatif dan penalaran (yang menjadi keunggulan LLM).
