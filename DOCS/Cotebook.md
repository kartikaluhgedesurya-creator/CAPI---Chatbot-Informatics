# Codebook — CAPI Replication Package

- **Encoding**: UTF-8.
- **Missing values**: Encoded as empty fields or NA.
- **Cross-file linkage**: The Query field (integer) links ground_truth.csv with RecapRater1.csv and RecapRater2.csv. The ablation response files do not include the Query field; they are linked through the question text.
- **Literal data values**: Literal values (e.g., Category, age, and tools) are retained in Bahasa Indonesia, as they represent the actual recorded data.

---

## 1. File respons Ablation (`03_data/`)

The following five files **share an identical column schema**. Each file represents a different ablation configuration:


| File                        | Configuration                  |
|-----------------------------|--------------------------------|
| `LLM_ONLY.csv`              | LLM only (no RAG, no PA)        |
| `LLM_RAG.csv`               | LLM + RAG (no PA)               |
| `LLM_RAG_PA_top_k_1.csv`    | LLM + RAG + PA, Top-1           |
| `LLM_RAG_PA_top_k_3.csv`    | LLM + RAG + PA, Top-3           |
| `LLM_RAG_PA_top_k_5.csv`    | LLM + RAG + PA, Top-5           |

Each row represents a single user query together with its retrieved context (if available) and the generated response.

| Column            | Type               | Description                                                                                          | Values / Range                                                |
|-------------------|--------------------|-----------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
| question          | string             | Original user query                                                                                 | free text                                                    |
| similar_question  | list[string] (str) | Similar question(s) retrieved from the knowledge base; length = k                                   | e.g. `['Apa itu Informatika?']`                              |
| similar_score     | list[float] (str)  | Cosine similarity score for each item in `similar_question`                                          | 0.0–1.0                                                      |
| model_similarity  | string             | Embedding model used for retrieval                                                                  | `sentence-transformers/paraphrase-multilingual-mpnet-base-v2` |
| targeted_response | string             | Reference answer from the knowledge base; for k>1 it is the concatenation of all top-k answers      | free text                                                    |
| model_response    | string             | Final post-processed chatbot response (clean answer; the text that is evaluated)                    | free text                                                    |
| complete_response | string (JSON)      | Raw model output, including the prompt template and the thinking block                              | stringified JSON                                             |
| time_response     | string             | Latency to generate the response                                                                    | e.g. `"7 seconds"`                                           |



Note: In LLM_Only.csv, the model_similarity column contains the default system value (sentence-transformers/paraphrase-multilingual-mpnet-base-v2). This field is automatically populated by the system, even though the LLM-only configuration does not perform retrieval. Therefore, the values in this column are not used in the retrieval process and should be ignored for analyses involving retrieval performance.

---

## 2. `ground_truth.csv`


| Column       | Type        | Description                                                | Values / Range                                                              |
|--------------|-------------|------------------------------------------------------------|----------------------------------------------------------------------------|
| Query        | integer     | Query ID (join key to `RecapRater1/2.csv`)                 | 1..N                                                                       |
| question     | string      | User question text                                         | free text                                                                 |
| Ground truth | string      | Reference answer written by the team as evaluation baseline | free text                                                                 |
| Category     | categorical | Topic label of the query                                   | 26 categories (see full list below)                                        |

**`Category` values (26 categories).**

| Category (original, as in data) | Description (English)                          |
|---------------------------------|------------------------------------------------|
| Profil Program Studi            | Study program profile                          |
| Materi belajar                  | What is studied / learning material            |
| Bidang Kerja                    | Career/job fields                              |
| magang/ kerja praktek           | Internship / practical work                    |
| Skripsi                         | Undergraduate thesis                           |
| coding                          | Coding                                         |
| Gaji lulusan                    | Graduate salary                                |
| Bahasa Pemrograman              | Programming languages                          |
| Informatika VS jurusan yang lain| Informatics vs. other majors                   |
| Matakuliah                      | Courses / subjects                             |
| Manfaat di masyarakat           | Benefit to society                             |
| Biaya                           | Cost / tuition fees                            |
| Matematika                      | Mathematics                                    |
| Kampus                          | Campus                                         |
| Gelar                           | Academic degree                                |
| Susah tidak                     | Difficulty (is it hard?)                        |
| Manfaat dan Keuntungan          | Benefits and advantages                        |
| Dosen                           | Lecturers / faculty                            |
| Akreditasi                      | Accreditation                                  |
| Pelaksanaan Kuliah              | How classes are conducted                      |
| Pendaftaran mahasiswa baru      | New-student admission/registration             |
| Beasiswa                        | Scholarships                                   |
| Persiapan mahasiswa baru        | New-student preparation                        |
| Latar belakang Siswa Baru       | New-student background                         |
| Fasilitas                       | Facilities                                     |


---

## 3. `RecapRater1.csv` dan `RecapRater2.csv`


| Column   | Type        | Description                                     | Values / Range                          |
|----------|-------------|-------------------------------------------------|-----------------------------------------|
| Query    | integer     | Query ID (join key to `ground_truth.csv`)       | 1..N                                    |
| question | string      | User question text                              | free text                               |
| Top1     | ordinal     | Rating for the LLM+RAG+PA Top-1 configuration   | Correct / Partially Correct / Incorrect |
| Top3     | ordinal     | Rating for the LLM+RAG+PA Top-3 configuration   | Correct / Partially Correct / Incorrect |
| Top5     | ordinal     | Rating for the LLM+RAG+PA Top-5 configuration   | Correct / Partially Correct / Incorrect |
| LLMOnly  | ordinal     | Rating for the LLM-only configuration           | Correct / Partially Correct / Incorrect |
| LLM+RAG  | ordinal     | Rating for the LLM+RAG configuration            | Correct / Partially Correct / Incorrect |


---

## 4. `ISO_questionaire_response.csv`


### Kolom metadata
| Column    | Type        | Description                     | Values / Range           |
|-----------|-------------|---------------------------------|--------------------------|
| timestamp | datetime    | Questionnaire submission time   | M/D/YYYY H:MM:SS         |
| age       | categorical | Respondent age group            | e.g. `15-19 tahun`       |
| tools     | categorical | Device used by the respondent   | e.g. `Smartphone`        |

###  item response
All questionnaire items were measured using a five-point Likert scale, with response options ranging from 1 ("Not True") to 5 ("Very True").

| Column   | ISO/IEC 25010 characteristic | Questionnaire item (Indonesian, verbatim)                                                                                                                                   | English translation                                                                                                                            |
|----------|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| EFF1     | Effectiveness                | Anda dapat memperoleh informasi mengenai Prodi Informatika yang anda butuhkan menggunakan Chatbot ini tanpa kesulitan                                                        | You can obtain the information you need about the Informatics program using this chatbot without difficulty.                                   |
| EFI1     | Efficiency                   | Anda merasa Aplikasi Chatbot ini mampu memberikan jawaban dengan cepat dan tidak membuang waktu                                                                              | You feel this chatbot provides answers quickly and does not waste time.                                                                        |
| EFI2     | Efficiency                   | Anda merasa penggunaan aplikasi Chatbot ini memudahkan Anda mendapatkan informasi mengenai Prodi Informatika UHN ... dibandingkan metode lain (seperti Google atau Website) | You feel using this chatbot makes it easier to obtain information about the UHN Informatics program than other methods (e.g., Google/website). |
| SAT1     | Satisfaction                 | Aplikasi Chatbot ini memenuhi harapan Anda dalam memperoleh informasi mengenai Prodi Informatika UHN I Gusti Bagus Sugriwa Denpasar.                                         | This chatbot meets your expectations for obtaining information about the UHN Informatics program.                                              |
| SAT2     | Satisfaction                 | Anda akan merekomendasikan aplikasi Chatbot ini kepada orang lain.                                                                                                          | You would recommend this chatbot to others.                                                                                                    |
| FFR1     | Freedom from Risk            | Anda merasa bahwa aplikasi Chatbot ini tidak memiliki resiko ketika digunakan.                                                                                              | You feel this chatbot carries no risk when used.                                                                                               |
| REL1     | Reliability                  | Anda merasa aplikasi Chatbot ini dapat digunakan tanpa sering mengalami gangguan atau error.                                                                                | You feel this chatbot can be used without frequent disruptions or errors.                                                                      |
| REL2     | Reliability                  | Aplikasi Chatbot merespons dengan cepat saat Anda menggunakannya.                                                                                                          | The chatbot responds quickly when you use it.                                                                                                  |
| SEC1     | Security                     | Anda merasa data pribadi Anda terlindungi saat menggunakan aplikasi Chatbot UHN                                                                                             | You feel your personal data is protected when using the UHN chatbot.                                                                           |
| SEC2     | Security                     | Anda merasa nyaman memberikan informasi sensitif ke dalam aplikasi Chatbot UHN                                                                                              | You feel comfortable providing sensitive information to the UHN chatbot.                                                                        |
| CTX1     | Context Coverage             | Anda merasa Chatbot mampu memberikan jawaban yang relevan terhadap berbagai topik seputar Prodi Informatika di UHN I Gusti Bagus Sugriwa Denpasar                          | You feel the chatbot provides relevant answers across various topics about the UHN Informatics program.                                        |
| CTX2     | Context Coverage             | Anda merasa chatbot dapat memahami maksud pertanyaan Anda, meskipun disampaikan dengan gaya bahasa yang berbeda-beda                                                         | You feel the chatbot understands the intent of your questions even when phrased in different language styles.                                  |
| LRN1     | Learnability                 | Anda memahami cara menggunakan chatbot ini saat pertama kali mencobanya                                                                                                     | You understood how to use this chatbot the first time you tried it.                                                                            |
| ACC1     | Accessibility                | Anda dapat mengakses chatbot ini dengan mudah melalui perangkat yang Anda gunakan (seperti smartphone, laptop, atau tablet)                                                 | You can easily access this chatbot on the device you use (e.g., smartphone, laptop, or tablet).                                                |
| ACC1.1   | Accessibility                | Anda dapat mengakses chatbot ini dimana saja tanpa terkendala jaringan?                                                                                                     | You can access this chatbot anywhere without network constraints.                                                                             |

**Note:**
ISO/IEC 25010 First edition 2011-03-01

---

## Ethics and Anonymization
The ISO evaluation dataset (DataAnalisisISO.csv) and the rater assessment data do not contain any personally identifiable information; only participants' age group and device type were recorded.
Respondent and rater identifiers were anonymized to protect participants' privacy.
