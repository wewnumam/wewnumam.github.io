---
title: "Notes PKA"
date: 2025-10-07T12:28:24+07:00
draft: false
---

## Pengenalan Kecerdasan Artifisial

### Catatan tentang Perspektif dan Perkembangan KA

#### **1. Tujuan yang Berbeda dalam AI**

- Orang memiliki tujuan yang berbeda dalam mempelajari AI:
    
    - **Pemikiran vs. Perilaku**: Apakah fokusnya pada bagaimana mesin _berpikir_ atau bagaimana mesin _bertindak_?
        
    - **Meniru manusia vs. Hasil optimal**: Apakah AI harus meniru kecerdasan manusia atau mencapai hasil yang _paling optimal_?
        

#### **2. Model Standar AI**

- AI terutama berfokus pada **tindakan rasional**, yaitu membangun agen yang bertindak secara optimal.
    
- **Agen rasional** adalah agen yang mengambil tindakan terbaik dalam suatu situasi.
    

#### **3. Penyempurnaan Model Standar**

- **Batasan komputasional**: Rasionalitas sempurna sulit dicapai karena keterbatasan daya komputasi.
    
- **Tujuan berpusat pada manusia**: AI seharusnya bertindak untuk _memberikan manfaat bagi manusia_, meskipun sering kali tidak pasti tentang apa sebenarnya yang diinginkan manusia.
    

#### **4. Kontribusi Dasar dari Berbagai Bidang**

- **Filsuf** (sejak 400 SM): Mengusulkan bahwa pikiran bekerja seperti mesin yang memproses pengetahuan internal untuk menentukan tindakan.
    
- **Ahli matematika**: Mengembangkan logika, probabilitas, serta dasar untuk memahami komputasi dan algoritma.
    
- **Ekonom**: Memformalkan **pengambilan keputusan** dengan teori _utilitas yang diharapkan_ (expected utility).
    
- **Ahli saraf (neurosaintis)**: Menemukan cara kerja otak serta persamaan dan perbedaannya dengan komputer.
    
- **Psikolog**: Memandang manusia dan hewan sebagai **mesin pemroses informasi**.
    
- **Ahli linguistik**: Menunjukkan bahwa **penggunaan bahasa** dapat dijelaskan dengan model komputasional.
    
- **Insinyur komputer**: Membangun **perangkat keras** yang semakin kuat untuk memungkinkan aplikasi AI.
    
- **Insinyur perangkat lunak**: Membuat sistem AI lebih **mudah digunakan**.
    
- **Teori kendali (control theory)**: Merancang sistem yang bertindak **secara optimal berdasarkan umpan balik** dari lingkungan; kini semakin banyak beririsan dengan AI.
    

#### **5. Perkembangan Historis AI**

- Sejarah AI mengalami **siklus keberhasilan, optimisme berlebihan, dan kemunduran** (AI winter).
    
- Setiap masa membawa **pendekatan baru** yang kemudian disempurnakan.
    

#### **6. Evolusi Metode AI**

- Dari **logika Boolean** → menuju **penalaran probabilistik**.
    
- Dari **pengetahuan buatan manusia** → menuju **pembelajaran mesin dari data**.
    
- Pergeseran ini meningkatkan kemampuan sistem AI dan memperkuat integrasinya dengan berbagai disiplin ilmu lain.
    

#### **7. Pertimbangan Etika dan Keamanan**

- Penerapan AI di dunia nyata menimbulkan **risiko dan konsekuensi etis**.
    
- Tantangan jangka panjang: **Mengendalikan AI superinteligensi** yang mungkin berkembang secara tidak terduga.
    
- Masalah ini menuntut **perubahan cara pandang kita terhadap AI** dan hubungannya dengan manusia.


---

## Agen Cerdas

- **AI sebagai Desain Agen**: Kecerdasan buatan dipandang sebagai ilmu merancang agen cerdas.

- **Definisi Agen**: Agen adalah entitas yang dapat _merasakan (perceive)_ dan _bertindak (act)_ di dalam suatu lingkungan. _Fungsi agen_ menentukan tindakan berdasarkan urutan persepsi yang diterimanya.
    
- **Ukuran Kinerja (Performance Measure)**: Menilai seberapa baik agen berperilaku di lingkungannya. Agen _rasional_ memilih tindakan yang memaksimalkan nilai harapan ukuran kinerja.
    
- **Lingkungan Tugas (Task Environment)**: Meliputi ukuran kinerja, lingkungan eksternal, aktuator, dan sensor — harus dijabarkan secara lengkap sebelum merancang agen.
    
- **Jenis-jenis Lingkungan**:
	
	- Observable vs. Partially observable
	- Single-agent vs. Multiagent
    - Deterministic vs. Nondeterministic
    - Episodic vs. Sequential
    - Static vs. Dynamic
    - Discrete vs. Continuous
    - Known vs. Unknown
        
- **Ketidakpastian Tujuan**: Jika ukuran kinerja tidak jelas, agen bisa mengoptimalkan tujuan yang salah. Desain agen harus memperhitungkan ketidakpastian ini.
    
- **Program Agen**: Mengimplementasikan fungsi agen. Desain program bergantung pada sifat lingkungan dan memengaruhi efisiensi, fleksibilitas, serta kepadatannya.
    
- **Jenis Agen**:
    
    - _Simple Reflex Agent_: Merespons langsung terhadap persepsi saat ini.
        
    - _Model-based Reflex Agent_: Menyimpan keadaan internal untuk melacak aspek dunia yang tidak tampak.
        
    - _Goal-based Agent_: Bertindak untuk mencapai tujuan.
        
    - _Utility-based Agent_: Bertindak untuk memaksimalkan kebahagiaan atau utilitasnya sendiri.
        
- **Pembelajaran**: Semua agen dapat meningkatkan kinerjanya melalui proses belajar.
    

---

## Searching Solution

### **Ringkasan**

Bab ini membahas **algoritma pencarian** yang digunakan agen untuk memilih urutan tindakan dalam lingkungan yang **episodic, single-agent, fully observable, deterministic, static, discrete, and completely known**.  
Ada kompromi antara **waktu pencarian, kapasitas memori, dan kualitas solusi**. Efisiensi meningkat jika digunakan **fungsi heuristik** atau **solusi parsial yang telah dihitung sebelumnya**.

### **Poin-Poin Utama**

1. **Perumusan Masalah** – Masalah harus didefinisikan dengan jelas sebelum pencarian dimulai.  
    Komponen:
    
    - Initial state
    - Set of actions
    - Transition model
    - Goal states
    - Action cost function
        
2. **State Space** – Direpresentasikan sebagai graf.
    
    - Jalur dari keadaan awal ke tujuan merupakan solusi.
        
3. **Kriteria Evaluasi Algoritma Pencarian:**
    
    - Completeness
    - Optimality (cost)
    - Time complexity
    - Space complexity
        
4. **Pencarian Tidak Terinformasi (Uninformed Search):** Hanya menggunakan definisi masalah.
    
    - **Breadth-First Search:** Mengembangkan node terdangkal; lengkap dan optimal untuk biaya satuan, tapi boros memori.
        
    - **Uniform-Cost Search:** Mengembangkan node dengan biaya terkecil; optimal untuk biaya umum.
        
    - **Depth-First Search:** Mengembangkan node terdalam; tidak lengkap atau optimal, tapi hemat memori.
        
    - **Depth-Limited Search:** Menambahkan batas kedalaman.
        
    - **Iterative Deepening Search:** DFS dengan batas kedalaman bertambah; lengkap, optimal untuk biaya satuan, ruang linear.
        
    - **Bidirectional Search:** Pencarian dari awal dan tujuan hingga bertemu.
        
5. **Pencarian Terinformasi (Informed Search):** Menggunakan **fungsi heuristik h(n)** yang memperkirakan biaya ke tujuan.
    
    - **Greedy Best-First Search:** Mengembangkan node dengan h(n) terkecil; efisien tapi tidak optimal.
        
    - **A* Search:** Mengembangkan node dengan f(n)=g(n)+h(n); lengkap dan optimal jika h(n) dapat diterima, tapi boros memori.
        
    - **Bidirectional A*:** Kadang lebih efisien dari A*.
        
    - **IDA*:** Versi iteratif dari A*, mengatasi masalah ruang.
        
    - **RBFS dan SMA*:** Pencarian optimal dengan batas memori.
        
    - **Beam Search:** Membatasi ukuran frontier; tidak lengkap dan tidak optimal, tetapi cepat.
        
    - **Weighted A*:** Mengarahkan pencarian lebih cepat ke tujuan dengan mengorbankan optimalitas.
        
6. **Kualitas Heuristik** – Menentukan kinerja pencarian.  
    Heuristik yang baik dapat dibuat melalui:
    
    - Relaksasi masalah
    - Basis data pola (pattern database)
    - Landmark
    - Pembelajaran dari pengalaman
        

---

## Knowledge Representation

- Representasi pengetahuan skala besar memerlukan **general-purpose ontology** untuk mengorganisir dan menghubungkan berbagai domain pengetahuan spesifik.
    
- **General-purpose ontology** harus mencakup berbagai jenis pengetahuan dan mampu menangani domain apa pun secara prinsip.
    
- Membangun ontology umum berskala besar masih menjadi tantangan besar, meskipun kerangka yang ada saat ini cukup kuat.
    
- Sebuah **upper ontology** dapat dibangun berdasarkan **categories** dan **event calculus**, yang mencakup:
    
    - categories, subcategories, parts, structured objects, measurements, substances, events, time and space, change, dan beliefs.
        
- **Natural kinds** tidak dapat sepenuhnya didefinisikan dengan logika, tetapi sifat-sifatnya dapat direpresentasikan.
    
- **Actions**, **events**, dan **time** dapat direpresentasikan menggunakan **event calculus**, yang memungkinkan agen menyusun urutan tindakan dan membuat inferensi logis tentang apa yang akan terjadi ketika tindakan tersebut dilakukan.
    
- Sistem representasi khusus seperti **semantic networks** dan **description logics** membantu dalam mengorganisir hierarki kategori.
    
    - **Inheritance** merupakan bentuk inferensi penting yang memungkinkan sifat objek diturunkan dari keanggotaannya dalam kategori.
        
- **Closed-world assumption** dalam program logika menyediakan cara sederhana untuk menghindari spesifikasi informasi negatif yang berlebihan dan berfungsi sebagai aturan default.
    
- **Nonmonotonic logics** seperti **circumscription** dan **default logic** dirancang untuk menangani **default reasoning** secara umum.
    
- **Truth maintenance systems** menangani pembaruan dan revisi pengetahuan dengan efisien.
    
- Sulit untuk membangun ontology besar secara manual; **knowledge extraction from text** dapat mempermudah pekerjaan ini.

---

## Pengolahan Bahasa Alami (NLP)

- **Model bahasa probabilistik** berbasis **n-gram** dapat mengekstrak banyak informasi dari bahasa dan bekerja dengan baik untuk tugas seperti **language identification**, **spelling correction**, **sentiment analysis**, **genre classification**, dan **named-entity recognition**.
    
- Model-model ini dapat memiliki **jutaan fitur**, sehingga **preprocessing** dan **smoothing** penting untuk mengurangi noise.
    
- Dalam membangun **sistem bahasa statistik**, sebaiknya merancang model yang dapat memanfaatkan data dengan baik, meskipun tampak **terlalu sederhana**.
    
- **Word embeddings** memberikan representasi kata yang lebih kaya dan menggambarkan **kemiripan antar kata**.
    
- Untuk menangkap **struktur hierarkis bahasa**, **phrase structure grammars** (terutama **context-free grammars**) sangat berguna. **Probabilistic context-free grammar (PCFG)** dan **dependency grammar** banyak digunakan.
    
- Kalimat dalam **context-free language** dapat di-**parse** dalam waktu **O(n³)** menggunakan **chart parser** seperti **CYK algorithm**, yang membutuhkan aturan tata bahasa dalam **Chomsky Normal Form**. Dengan sedikit penurunan akurasi, bahasa alami dapat di-**parse** dalam waktu **O(n)** menggunakan **beam search** atau **shift-reduce parser**.
    
- **Treebank** dapat menjadi sumber untuk mempelajari parameter **PCFG**.
    
- **Grammar augmentation** memudahkan penanganan **subject–verb agreement**, **pronoun case**, dan memungkinkan representasi informasi di tingkat **kata**, bukan hanya **kategori sintaksis**.
    
- **Semantic interpretation** juga dapat ditangani melalui **augmented grammar**, yang dapat dipelajari dari **corpus** berisi pertanyaan yang dipasangkan dengan **logical form** atau **jawaban**.
    
- **Bahasa alami** sangat **kompleks** dan sulit sepenuhnya direpresentasikan dalam **formal grammar**.

---

## Contoh Soal-Jawaban UTS

Berikut jawaban singkat: tiap soal ditampilkan → jawaban ringkas.

**1. Pertanyaan:** Anda sudah mengenal beberapa pengertian tentang Kecerdasan Artifisial (KA). Pada era industri 4.0 ini, menurut anda definisi KA yang mana yang cocok pada kondisi sekarang dan apa paradigma KA yang cocok.  

**Jawaban:** Definisi yang cocok: _KA adalah sistem/artifak komputer yang mampu mengamati lingkungan, belajar dari data/pengetahuan, membuat keputusan, dan bertindak untuk mencapai tujuan yang bermanfaat bagi manusia._ Paradigma yang cocok: **hybrid data-driven + simbolik** — utamakan _machine learning_ (deep learning) untuk persepsi & prediksi, dipadukan dengan komponen simbolik/penalaran (knowledge/rules, probabilistic models) untuk interpretabilitas, pengendalian kebijakan, dan keselamatan.

---

**2.a Pertanyaan:** Deskripsikan sebuah contoh permainan game yang cocok diselesaikan dengan informed search.  

**Jawaban:** Contoh: _8-puzzle_ (geser ubin 3×3 ke posisi tujuan). Informed search efektif karena ada heuristik (misal Manhattan distance) mempercepat pencarian solusi.

**2.b Pertanyaan:** Buatlah state space, dan tuliskan algoritmanya untuk mendapatkan hasil akhir.  
**Jawaban (ringkas):**

- State space: semua konfigurasi tata letak 9 ubin (termasuk kotak kosong).
- Operator: geser kotak kosong {up, down, left, right} bila legal.
- Start: konfigurasi awal; Goal: konfigurasi target.
- Heuristik: h(n) = jumlah Manhattan distance tiap ubin ke pos tujuan.
- Algoritma: **A\***
    
    ```python
    function A*(start, goal):
      open := {start} with f(start)=g(start)+h(start), g(start)=0
      closed := {}
      while open not empty:
        n := node in open with smallest f
        if n == goal: return reconstruct_path(n)
        move n from open to closed
        for each successor s of n:
          tentative_g := g(n)+cost(n,s)
          if s in closed and tentative_g >= g(s): continue
          if s not in open or tentative_g < g(s):
            parent(s) := n
            g(s) := tentative_g
            f(s) := g(s)+h(s)
            add s to open
    ```

---

**3.a Pertanyaan:** Buatlah bagan sistem inferensi fuzzy, jelaskan masing-masing bagiannya.  

**Jawaban (ringkas):** Bagan komponen:

1. **Fuzzification** — ubah input numerik ke derajat keanggotaan pada himpunan fuzzy.
2. **Knowledge / Rule base** — kumpulan aturan IF–THEN (linguistik).
3. **Inference engine** — evaluasi aturan, kombinasikan antecedent untuk menghasilkan fuzzy output (tingkat aktivasi rule).
4. **Aggregation** — gabungkan kontribusi semua rule ke fungsi keanggotaan output fuzzy.
5. **Defuzzification** — konversi output fuzzy ke nilai numerik tunggal (mis. centroid).

---

**3.b Pertanyaan:** Buatlah sebuah contoh sistem inferensi fuzzy yg menggunakan 3 input, 1 output diluar yg telah dibahas di kelas.  

**Jawaban (ringkas):** _Sistem irigasi pintar_
- Input: SoilMoisture (kelembaban tanah), RainProb (probabilitas hujan), PlantNeed (kebutuhan air tanaman).
- Output: IrrigationDuration (durasi penyiraman dalam menit).

**3.c Pertanyaan:** Buatlah himpunan fuzzy untuk masing parameter.  

**Jawaban (ringkas):** (semua rentang contoh 0–100 kecuali duration 0–60 menit)

- SoilMoisture: {Low (0–40), Medium (30–70), High (60–100)} (triangular/trapezoid).
- RainProb: {Low (0–30), Medium (20–70), High (60–100)}.
- PlantNeed: {Low (0–30), Normal (20–70), High (60–100)}.
- IrrigationDuration: {Short (0–15), Medium (10–30), Long (25–60)}.

**3.d Pertanyaan:** Buatlah 4 fuzzy rules yang mengandung paling tidak dua konklusi yang menjadi premis di rules yang lain.  

**Jawaban (ringkas):** (gunakan variabel antara _Urgency_ sebagai intermediate)

- R1: IF SoilMoisture IS Low THEN Urgency IS High.
- R2: IF RainProb IS High THEN Urgency IS Low.
- R3: IF Urgency IS High AND PlantNeed IS High THEN IrrigationDuration IS Long.
- R4: IF Urgency IS Medium OR RainProb IS Medium THEN IrrigationDuration IS Medium.

(Keterangan: R1 & R2 menghasilkan _Urgency_ — yang dipakai oleh R3/R4 sebagai premis.)

---

**4. Pertanyaan:** Jelaskan bagaimana konsep Kecerdasan Artifisial serta berikan 5 contoh dan penjelasannya bidang aplikasi Kecerdasan Artifisial. Jelaskan dan terapkan metode inferensi yang anda ketahui untuk menghasilkan konklusi.  

**Jawaban (ringkas):**

- **Konsep AI:** rekayasa sistem yang _persepsi → representasi/pengetahuan → penalaran/decision → aksi_, sering memakai probabilitas/statistik dan/atau aturan simbolik untuk mencapai tujuan.
    
- **5 contoh aplikasi & penjelasan singkat:**
    1. **Pengenalan gambar (Computer Vision)** — deteksi objek/segmentasi untuk industri, keamanan.
    2. **Sistem rekomendasi** — menyarankan produk/musik dengan collaborative filtering / ML.
    3. **Chatbot / NLP** — pemrosesan bahasa alami untuk layanan pelanggan.
    4. **Kendaraan otonom** — integrasikan sensor + planning + control untuk mengemudi.
    5. **Diagnosis medis berbasis AI** — klasifikasi citra/risk scoring untuk membantu keputusan klinis.

- **Metode inferensi (contoh aplikasi rule-based, forward chaining):**  
    Contoh singkat: Sistem bantuan diagnostik (aturan):
    - Rule A: IF fever AND cough THEN suspect_infection.
    - Rule B: IF suspect_infection AND chest_pain THEN suspect_pneumonia.
    - Fact: fever = true, cough = true, chest_pain = true.  
        Forward chaining: dari Rule A → suspek_infection; dari suspek_infection + chest_pain + Rule B → suspek_pneumonia (konklusi).

---

**5. Pertanyaan:** Salah satu teknik penting dalam Kecerdasan Artifisial adalah searching. Sebutkan, jelaskan dan berilah contoh hal-hal yang berkaitan dengan proses searching tersebut! (5%)  

**Jawaban (ringkas):**

- **Komponen dasar**: state space, initial state, goal test, operators, path cost, solusi (path).
- **Uninformed search**: tidak pakai heuristik. Contoh: BFS (lengkap, optimal jika cost=1), DFS (hemat memori, tidak optimal), Uniform-cost (optimal untuk biaya).
- **Informed search (heuristic)**: pakai fungsi heuristik h(n). Contoh: Greedy best-first (cepat, tidak optimal), A* (optimal jika h admissible).
- **Local search / hill-climbing**: optimisasi tanpa eksplorasi penuh (contoh: simulated annealing, genetic algorithms).
- **Contoh aplikasi**: pathfinding di game (A*), puzzle solving (8-puzzle dengan A*), optimasi jadwal (genetic algorithms).

---

**6. Diberikan pernyataan-pernyataan berikut...**  
Pernyataan:

- Budi suka semua jenis makanan.
- Apel adalah makanan.
- Ayam goreng adalah makanan.
- Sesuatu yang dimakan dan tidak membuat mati adalah makanan.
- Johan makan kacang dan masih hidup.
- Susi makan setiap yang dimakan Johan.

**6.a Pertanyaan:** Tuliskan kalimat-kalimat tersebut dalam logika predikat!  
**Jawaban (ringkas):** (predikat: Food(x), Likes(budi,x), Eats(person,x), AliveAfterEating(person,x))

1. ∀x (Food(x) → Likes(Budi,x)).
2. Food(apel).
3. Food(ayam_goreng).
4. ∀y∀z (Eats(y,z) ∧ AliveAfterEating(y,z) → Food(z)).
5. Eats(Johan,kacang) ∧ AliveAfterEating(Johan,kacang).
6. ∀x (Eats(Johan,x) → Eats(Susi,x)).

**6.b Pertanyaan:** Dengan menggunakan teknik resolusi, tunjukkan bahwa Budi suka kacang!  
**Jawaban (ringkas, langkah resolusi):**

- Dari (5) dan (4): Eats(Johan,kacang) ∧ AliveAfterEating(Johan,kacang) ⇒ Food(kacang). (instansiasi)
- Dari (1) dan Food(kacang) ⇒ Likes(Budi,kacang). (modus ponens / resolusi)  
    Jadi: **Likes(Budi,kacang)**. (terbukti)

**6.c Pertanyaan:** Gunakan teknik resolusi untuk menjawab pertanyaan: "Apa makanan yang dimakan Susi."  
**Jawaban (ringkas):**

- Dari (5): Eats(Johan,kacang). Dari (6): Eats(Johan,kacang) → Eats(Susi,kacang). Jadi **Susi makan kacang**.
- Umum: Susi makan semua yang Johan makan (∀x Eats(Johan,x) → Eats(Susi,x)), jadi Susi makan setiap item yang Johan makan (di sini: kacang).

---

## Flash Card

### Kartu Flash — Pengenalan Kecerdasan Buatan (1–10)

1. Q: Apa definisi singkat Kecerdasan Buatan (AI)?  
    A: Sistem komputer yang mengamati lingkungan, memproses informasi, belajar, dan bertindak untuk mencapai tujuan tertentu.
    
2. Q: Sebutkan dua pendekatan utama dalam AI.  
    A: Pendekatan simbolik (aturan/logika) dan pendekatan statistik/pembelajaran (ML/DL).
    
3. Q: Apa yang dimaksud agen rasional?  
    A: Agen yang memilih aksi untuk memaksimalkan expected performance berdasarkan persepsi dan pengetahuan.
    
4. Q: Mengapa etika penting dalam pengembangan AI?  
    A: Karena AI dapat mempengaruhi keselamatan, privasi, fairness, dan keputusan bernilai pada manusia.
    
5. Q: Apa perbedaan antara AI kuat (strong AI) dan AI lemah (weak AI)?  
    A: Weak AI fokus tugas spesifik; strong AI berarti kemampuan kognitif umum setara manusia.
    
6. Q: Sebutkan satu contoh aplikasi AI di kehidupan sehari-hari.  
    A: Rekomendasi produk, asisten virtual, deteksi wajah, atau kendaraan otonom.
    
7. Q: Mengapa hybrid (simbolik + statistik) sering digunakan?  
    A: Untuk memanfaatkan interpretabilitas aturan sekaligus kekuatan generalisasi data-driven.
    
8. Q: Apa arti “bias data” pada AI?  
    A: Ketidakseimbangan atau pola buruk di data yang menyebabkan model membuat keputusan tidak adil.
    
9. Q: Apa tujuan evaluasi model AI?  
    A: Menilai kinerja, generalisasi, keandalan, dan kecocokan model untuk tugas nyata.
    
10. Q: Sebutkan satu batasan penting AI modern.  
    A: Kebutuhan data banyak; kadang sulit interpretasi (black-box).
    

### Kartu Flash — Agen Cerdas (11–20)

11. Q: Apa fungsi agen?  
    A: Mapping dari percept (input sensor) ke aksi (action).
    
12. Q: Jenis agen sederhana pertama yang sering dibahas?  
    A: Simple reflex agent (respon berdasarkan kondisi sekarang).
    
13. Q: Kapan simple reflex agent gagal?  
    A: Saat lingkungan partial observable atau memerlukan memori/history.
    
14. Q: Apa itu model-based agent?  
    A: Agen yang menyimpan state internal/model lingkungan untuk membuat keputusan.
    
15. Q: Bedakan goal-based dan utility-based agent.  
    A: Goal-based berorientasi mencapai goal; utility-based memaksimalkan nilai utilitas yang mengukur preferensi.
    
16. Q: Sebutkan dua dimensi karakter lingkungan agen.  
    A: Observable vs partially observable; deterministic vs nondeterministic.
    
17. Q: Apa arti environment episodic vs sequential?  
    A: Episodic: setiap episode independen; sequential: keputusan sekarang mempengaruhi masa depan.
    
18. Q: Apa tantangan pada multi-agent environment?  
    A: Koordinasi, kompetisi, komunikasi, dan ketidakpastian perilaku agen lain.
    
19. Q: Mengapa representasi state penting pada agen?  
    A: Karena menentukan apa yang agen ketahui dan bagaimana dia merencanakan aksi.
    
20. Q: Contoh nyata utility-based agent.  
    A: Agen trading yang memaksimalkan expected return dengan penalti risiko.
    

### Kartu Flash — Searching / Pencarian Solusi (21–30)

21. Q: Apa komponen utama formulasi masalah pencarian?  
    A: Initial state, actions, transition model, goal test, cost function.
    
22. Q: Apa tujuan algoritma search?  
    A: Menemukan urutan aksi dari initial state ke goal state.
    
23. Q: Kapan BFS lebih cocok daripada DFS?  
    A: Saat solusi paling dangkal dicari dan ruang status terdiskret/sedang.
    
24. Q: Apa kelebihan dan kekurangan DFS?  
    A: Kelebihan memori rendah; kekurangan bisa tidak lengkap dan terjebak di cabang tak hingga.
    
25. Q: Apa itu Uniform Cost Search (UCS)?  
    A: Search yang memilih node dengan biaya kumulatif terkecil (optimal untuk biaya non-negatif).
    
26. Q: Rumus utama A* dan maknanya.  
    A: f(n)=g(n)+h(n). g biaya dari start ke n; h estimasi biaya n→goal.
    
27. Q: Apa itu heuristik admissible?  
    A: Heuristik yang tidak pernah melebih-lebihkan biaya sebenarnya ke goal (underestimate).
    
28. Q: Mengapa konsistensi heuristik penting?  
    A: Konsisten (monotonic) memastikan f tidak menurun dan membuat A* lebih efisien (tidak perlu reopen node).
    
29. Q: Bagaimana membuat heuristik dari relaksasi masalah?  
    A: Hilangkan beberapa constraint sehingga solusi relaksasi mudah dihitung → gunakan biaya relaksasi sebagai h.
    
30. Q: Apa trade-off antara beam search dan A*?  
    A: Beam lebih hemat memori tapi tidak lengkap/optimal; A* lengkap/optimal dengan heuristik admissible tapi memori besar.
    

### Kartu Flash — Knowledge Representation (31–40)

31. Q: Apa tujuan Knowledge Representation (KR)?  
    A: Menyimpan pengetahuan sehingga mesin dapat melakukan inferensi dan membuat keputusan.
    
32. Q: Bedakan propositional vs predicate logic.  
    A: Propositional: atom tanpa argumen; predicate: fungsi/predikat dengan variabel → ekspresivitas lebih tinggi.
    
33. Q: Apa itu ontology dalam KR?  
    A: Model konsep dan relasi domain untuk komunikasi dan interoperabilitas pengetahuan.
    
34. Q: Fungsi semantic network?  
    A: Merepresentasikan konsep sebagai node dan relasi sebagai edge untuk inferensi berbasis jaringan.
    
35. Q: Apa itu nonmonotonic reasoning?  
    A: Penalaran di mana menambah informasi baru dapat mengubah kesimpulan sebelumnya (default assumptions).
    
36. Q: Untuk apa truth maintenance system (TMS)?  
    A: Melacak justifikasi untuk fakta sehingga dapat retract (membatalkan) dengan konsisten.
    
37. Q: Kapan description logic biasa dipakai?  
    A: Untuk ontologies dan reasoning tentang kelas, subclass, dan keterbatasan (mis. OWL).
    
38. Q: Apa role event calculus?  
    A: Merepresentasikan events, waktu, dan efeknya pada status world untuk reasoning temporal.
    
39. Q: Apa tantangan utama saat membangun knowledge base dari teks?  
    A: Ambiguitas bahasa, inkonsistensi, pengenalan entitas, dan skala data.
    
40. Q: Sebutkan satu metode untuk menangani default assumptions.  
    A: Default logic atau circumscription untuk mengekspresikan asumsi “kecuali terbukti sebaliknya”.
    

### Kartu Flash — NLP (Pengolahan Bahasa Alami) (41–50)

41. Q: Apa itu model n-gram?  
    A: Model probabilistik yang memprediksi kata berikutnya berdasarkan (n−1) kata sebelumnya.
    
42. Q: Kenapa smoothing diperlukan pada n-gram?  
    A: Untuk memberi probabilitas pada n-gram yang tidak muncul di data training (menghindari nol).
    
43. Q: Sebutkan satu teknik smoothing.  
    A: Laplace smoothing (add-one) atau Kneser-Ney.
    
44. Q: Apa itu PCFG?  
    A: Probabilistic Context-Free Grammar — grammar kontekstual dengan probabilitas untuk produksi aturan.
    
45. Q: Untuk apa algoritma CYK dipakai? dan kompleksitasnya?  
    A: Parsing dengan grammar CNF; kompleksitas O(n³) (n = panjang kalimat).
    
46. Q: Perbedaan parsing dependensi dan parsing konstituen?  
    A: Dependensi fokus relasi antar kata; konstituen fokus struktur frasa dan pohon konstituen.
    
47. Q: Apa itu word embedding?  
    A: Representasi vektor kata yang menangkap makna/kemiripan semantik (mis. word2vec).
    
48. Q: Bagaimana embeddings membantu task NLP?  
    A: Menyediakan fitur kontinu yang menangkap hubungan semantik sehingga model ML lebih efektif.
    
49. Q: Sebutkan satu aplikasi sederhana model n-gram.  
    A: Language identification, spelling correction, atau predictive text sederhana.
    
50. Q: Mengapa treebanks penting untuk NLP?  
    A: Sebagai data beranotasi untuk melatih parser, POS tagger, dan model sintaksis lainnya.
    

----