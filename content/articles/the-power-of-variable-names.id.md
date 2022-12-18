---
title: "Dahsyatnya Fungsi Nama Variabel"
date: 2022-12-16T09:22:51+07:00
draft: false
---

## Nama Variabel yang Bermakna
> Memilih nama yang baik membutuhkan waktu tetapi menghemat lebih banyak daripada yang dibutuhkan.

### Nama yang Mengungkapkan Niat
Nama harus menjawab semua pertanyaan besar. Nama harus memberitahu kita mengapa variabel itu ada, apa yang dilakukannya, dan bagaimana penggunaannya. Jika nama tersebut membutuhkan komentar, maka nama tersebut tidak mengungkapkan maksudnya.
```javascript
let d; // waktu yang berlalu dalam hari
```
Kita harus memilih nama yang menentukan apa yang sedang diukur dan unit pengukuran itu:
```javascript
let elapsedTimeInDays;
let daysSinceCreation;
let daysSinceModification;
let fileAgeInDays;
```
Contoh kode yang sulit dimengerti karena menggunakan nama yang buruk:
```javascript
function getThem() {
    let list1 = [];
    for (let x in theList)
        if (x[0] == 4) list1.add(x);
    return list1;
}
```
Masalahnya bukan pada kesederhanaan kodenya, tetapi *penyederhanaan* kodenya. Kode tersebut tidak memberitahukan benda apa saja yang ada di dalam `theList` dan apa nilai dari `4`. Hanya dengan memberikan nama-nama konseptual, kita dapat memperbaiki kode secara signifikan:
```javascript
function getFlaggedCells() {
    let flaggedCells = [];
    for (let cell in gameBoard) {
        if (cell[STATUS_VALUE] == FLAGGED)
            flaggedCells.add(cell);
    }
    return flaggedCells;
}
```
atau secara fungsional:
```javascript
function getFlaggedCells(gameBoard) {
    return gameBoard.filter(cell => cell[STATUS_VALUE] === FLAGGED)
}
```

**Contoh Nama Variabel yang Baik dan Buruk**

Tujuan Variabel | Nama Baik | Nama Buruk
--- | --- | ---
Jumlah total pemeriksaan yang ditulis hingga saat ini | `runningTotal`, `checkTotal` | `written`, `ct`, `checks`, `CHKTTL`, `x`, `x1`, `x2`
Kecepatan peluru | `velocity`, `trainVelocity`, `velocityMph` | `velt`, `v`, `tv`, `train`,`x`, `x1`, `x2`
Tanggal saat ini | `currentDate`, `todaysDate` | `cd`, `current`, `c`, `x`, `x1`, `x2`, `date`
Baris per halaman | `linesPerPage` | `lpp`, `lines`, `l`, `x`, `x1`, `x2`

**Panjang Nama Optimum**

Terlalu panjang | Pendek | Tepat
--- | --- | ---
`numberOfPeopleOnTheUsOlympicTeam` | `n`, `np`, `ntm` | `numTeamMembers`, `teamMemberCount`
`numberOfSeatsInTheStadium` | `n`, `ns`, `nsisd` | `numSeatsInStadium`, `seatCount`
`maximumNumberOfPointsInModernOlympics` | `m`, `mp`, `max`, `points` | `maxTeamPoints`, `maxPoints`

### Perbedaan yang Bermakna
Karena kita tidak dapat menggunakan nama yang sama untuk merujuk ke dua hal yang berbeda dalam lingkup yang sama, kita mungkin tergoda untuk mengubah satu nama secara sembarangan. Tidak cukup hanya dengan menambahkan deret angka atau kata-kata mengganggu (mubazir), walaupun compiler atau interpreter sudah puas.
```javascript
function copyChars(a1, a2) {
    for (let i = 0; i < a1.length; i++) {
        a2[i] = a1[i];
    }
}
```
Jika nama harus berbeda, maka mereka juga harus berarti sesuatu yang berbeda. Deret angka `{a1, a2, ... aN}` adalah kebalikan dari penamaan yang disengaja. Nama-nama seperti itu tidak disinformatif (mereka noninformatif); mereka tidak memberikan petunjuk tentang maksud penulis. Pertimbangkan:
```javascript
function copyChars(source, target) {
    for (let i = 0; i < source.length; i++) {
        target[i] = source[i];
    }
}
```
Gunakan lawan kata secara tepat. Menggunakan konvensi penamaan untuk lawan kata membantu konsistensi, dimana hal ini membantu keterbacaan.

**Kebalikan Umum dalam Nama Variabel**
- begin/end
- first/last
- locked/unlocked
- min/max
- next/previous
- old/new
- opened/closed
- visible/invisible
- source/target
- up/down

### Nama yang Dapat Diucapkan
Jika kita tidak dapat mengucapkannya, kita tidak dapat mendiskusikannya tanpa terdengar seperti orang bodoh. Hal ini penting karena pemrograman adalah aktivitas sosial. Bandingkan:
```javascript
// ymdhms (date, year, month, day, hour)
let genymdhms;
let modymdhms;
let pszqint = "102";
```
menjadi
```javascript
let generationTimestamp;
let modificationTimestamp;
let recordId = "102";
```

### Nama yang dapat dicari
Nama dengan huruf tunggal dan konstanta numerik memiliki masalah khusus karena tidak mudah ditemukan di seluruh badan teks. Nama huruf tunggal HANYA dapat digunakan sebagai variabel lokal di dalam metode pendek. Panjang nama harus sesuai dengan ukuran ruang lingkupnya. Jika sebuah variabel atau konstanta mungkin terlihat atau digunakan di banyak tempat dalam sebuah badan kode, sangat penting untuk memberikan nama yang mudah dicari. Bandingkan:
```javascript
for (let j = 0; j < 34; j++) {
    s += (t[j] * 4) / 5;
}
```
menjadi
```javascript
let realDaysPerIdealDay = 4;
const WORK_DAYS_PER_WEEK = 5;
let sum = 0;
for (let j = 0; j < NUMBER_OF_TASK; j++) {
    let realTaskDays = taskEstimate[j] * realDaysPerIdealDay;
    let realTaskWeeks = realTaskDays / WORK_DAYS_PER_WEEK;
    sum += realTaskWeeks;
}
```

### Penamaan Jenis Data Tertentu
**Penamaan Indeks Loop**

Nama `i`, `j`, dan `k` adalah nama-nama variabel loop sederhana yang lazim:
```javascript
for (let i = firstItem; i < lastItem; i++) {
    data[i] = 0;
}
```
Jika sebuah variabel akan digunakan di luar perulangan, variabel tersebut harus diberi nama yang lebih bermakna daripada `i`, `j`, `k`. Misalnya, jika kita membaca record dari file dan perlu mengingat berapa banyak record yang telah kita baca, nama yang lebih bermakna seperti `recordCount` akan sesuai:
```javascript
let recordCount = 0
while (moreScore()) {
    score[recordCount] = getNextScore();
    recordCount++;
}
```
Satu alasan umum mengapa loop berkembang adalah karena mereka bersarang. Jika kita memiliki beberapa loop bersarang, berikan nama yang lebih panjang untuk variabel teratas untuk meningkatkan keterbacaan.
```javascript
for (teamIndex = 0; teamIndex < teamCount; teamIndex++) {
    for (eventIndex = 0; eventIndex < eventCount[teamIndex]; eventIndex++) {
        score[teamIndex][eventIndex] = 0;
    }
}
```
Nama-nama yang dipilih dengan hati-hati untuk variabel indeks-lingkaran menghindari masalah umum dari cross-talk indeks. Cara paling sederhana untuk menghindari masalah tersebut adalah dengan memikirkan nama-nama yang lebih deskriptif daripada `i`, `j`, `k`. `score[teamIndex][eventIndex]` lebih informatif daripada `score[i][j]`

**Penamaan Variabel Status**
Variabel status menggambarkan keadaan program kita. Lebih baik menganggap flag sebagai variabel status. Flag harus diberi nilai dan nilainya harus diuji dengan tipe enumerasi, konstanta, atau variabel global yang bertindak sebagai konstanta. Berikut adalah beberapa contoh flag dengan nama yang buruk:
```javascript
if (flag) ...
if (statusFlag == 0x0F) ...
if (printFlag == 16) ...
if (computeFlag == 0) ...

flag = 0x1;
statusFlag = 0x80;
printFlag = 16
computeFlag = 0;
```
Berikut adalah contoh kode serupa yang lebih jelas:
```javascript
if (dataReady) ...
if (charType & PRINTABLE_CHAR) ...
if (reportType == reportTypeEnum.annual) ...
if (recalcNeeded == true) ...

dataReady = true;
charType = CONTROL_CHARACTER;
reportType = reportTypeEnum.annual
recalcNeeded = false;
```

**Penamaan Variabel Sementara**

Variabel sementara digunakan untuk menampung hasil antara dari perhitungan, sebagai placeholder sementara, dan untuk menampung nilai housekeeping. Mereka biasanya disebut `temp`, `x`, atau nama lain yang tidak jelas dan tidak deskriptif. Secara umum, variabel sementara adalah tanda bahwa programmer belum sepenuhnya memahami masalah. Selain itu, karena variabel-variabel tersebut secara resmi diberi status `temporary`, programmer cenderung memperlakukan mereka lebih santai daripada variabel lain. Hal ini meningkatkan kemungkinan terjadinya kesalahan.
```javascript
let temp = Math.sqrt(b^2 - 4*a*c);
root[0] = (-b + temp) / (2 * a);
root[1] = (-b - temp) / (2 * a);
```
Nama `temp` tidak memberitahukan apapun tentang apa yang dilakukan oleh variabel tersebut. Pendekatan yang lebih baik ditunjukkan dalam contoh ini:
```javascript
let disciminant = Math.sqrt(b^2 - 4*a*c);
root[0] = (-b + disciminant) / (2 * a);
root[1] = (-b - disciminant) / (2 * a);
```

**Penamaan Variabel Boolean**

Nama-nama variabel boolean yang berguna:
- **done**
- **error**
- **found**
- **success**

**Berikan nama variabel boolean yang menyiratkan `true` atau `false`**

Nama-nama seperti `done` dan `success` adalah nama boolean yang tepat karena statusnya adalah *`true`* atau *`false`*. Nama-nama seperti `status` dan `sourceFile`, di sisi lain, adalah nama-nama boolean yang buruk karena mereka tidak jelas *`true`* atau *`false`*.

Untuk hasil yang lebih baik, ganti `status` dengan nama seperti `error` atau `statusOK`, dan ganti `sourceFile` dengan `sourceFileAvailable` atau `sourceFileFound`, atau apapun yang diwakili oleh variabel tersebut.

Beberapa programmer suka meletakkan `Is` di depan nama boolean mereka. Kemudian nama variabel menjadi pertanyaan: `isDone`? `isError`? `isFound`? `isProcessingComplete`? Menjawab pertanyaan dengan *`true`* atau *`false`* akan memberikan nilai variabel.

**Gunakan nama variabel boolean positif**

Nama-nama negatif seperti `notFound`, `notDone`, dan `notSuccessful` sulit dibaca ketika mereka dinegasikan.

**Penamaan Tipe Enumerasi**

```javascript
const daysEnum = Object.freeze({
  monday: 0,
  tuesday: 1,
  wednesday: 2,
  thursday: 3,
  friday: 4,
  saturday: 5,
  sunday: 6
});
```
Mengambil satu langkah lebih jauh, seseorang dapat mengekstrak logika ke dalam fungsi dengan jumlah argumen yang bervariasi dan menghasilkan objek yang dibekukan. Hanya ada sedikit manfaat dari teknik ini, jadi alternatif yang lebih baik adalah membuat kelas sederhana. Lagipula, enum lebih umum dalam bahasa pemrograman berorientasi objek, jadi ini terdengar sangat cocok.

**Penamaan Konstanta**
Ketika menamai konstanta, beri nama entitas abstrak yang diwakili oleh konstanta tersebut daripada angka yang dirujuk oleh konstanta tersebut. `FIVE` adalah nama yang buruk untuk konstanta. `FIVE = 6` akan menjadi konyol. `CYCLES_NEEDED` adalah nama yang baik. Dengan cara yang sama, `BAKERS_DOZEN` juga merupakan nama konstanta yang buruk; `DONUT_MAX` adalah nama konstanta yang baik.

## Masalah Umum dalam Menggunakan Variabel
### Disinformasi
Programmer harus menghindari meninggalkan petunjuk palsu yang mengaburkan arti kode. Kita harus menghindari kata-kata yang maknanya berbeda dari makna yang kita maksudkan. Singkatan bisa menjadi disinformatif.

Jangan merujuk pada pengelompokan akun sebagai `accountList` kecuali jika itu adalah *`List`*. Kata daftar berarti sesuatu yang spesifik untuk programmer. Jika wadah yang menampung akun-akun tersebut bukan sebuah *`List`*, hal ini dapat menyebabkan kesimpulan yang salah. Jadi `accountGroup` atau hanya `accounts` akan lebih baik.

Contoh yang benar-benar parah dari nama yang tidak informatif adalah penggunaan huruf kecil `L` dan huruf besar `O` sebagai nama variabel, terutama dalam kombinasi. Masalahnya, tentu saja, adalah bahwa mereka terlihat hampir seluruhnya seperti konstanta satu dan nol, masing-masing.
```javascript
let a = l;
if (O == l) a = O1;
else l = 01;
```

**Orientasi-Masalah**

Nama mnemonik nama yang baik umumnya berbicara tentang masalah daripada solusi. Nama yang baik adalah *apa* lebih dari *bagaimana*. Secara umum, jika sebuah nama mengacu pada beberapa aspek komputasi daripada masalah, itu adalah *bagaimana* daripada *apa*. Hindari nama seperti itu dan pilihlah nama yang mengacu pada masalah itu sendiri.

Sebuah catatan data karyawan bisa disebut `inputRec` atau `employeeData`. `inputRec` adalah istilah komputer yang mengacu pada ide komputasi - input dan record. `employeeData` mengacu pada domain masalah daripada dunia komputasi. Demikian pula, untuk bidang bit yang menunjukkan status printer, `bitFlag` adalah nama yang lebih komputeris daripada `printerReady`. Dalam aplikasi akuntansi, `calcVal` lebih komputeris.

### Pengkodean
Kita sudah cukup banyak encoding untuk ditangani tanpa menambah beban kita. Pengkodean tipe atau informasi ruang lingkup ke dalam nama-nama hanya menambah beban ekstra untuk menguraikannya. Ini adalah beban mental yang tidak perlu ketika mencoba untuk memecahkan masalah. Nama-nama yang dikodekan jarang diucapkan dan mudah salah ketik. Sistem pengkodean akan menyesatkan pembaca.

### Saran
- Hindari nama atau singkatan yang menyesatkan
- Hindari nama-nama dengan arti yang mirip
- Hindari variabel dengan arti yang berbeda tetapi nama yang mirip
- Hindari angka dalam nama
- Hindari kata-kata yang salah eja dalam nama
- Jangan membedakan nama variabel hanya dengan kapitalisasi
- Hindari beberapa bahasa alamiah
- Hindari nama-nama tipe standar, variabel, dan rutinitas
- Jangan gunakan nama yang tidak berhubungan dengan apa yang diwakili oleh variabel tersebut
- Hindari nama yang mengandung karakter yang sulit dibaca

## Konvensi Penamaan
**Mengapa Perlu Ada Konvensi?**
- Konvensi memungkinkan kita mengambil lebih banyak hal untuk diberikan. Dengan membuat satu keputusan global daripada banyak keputusan lokal, kita dapat berkonsentrasi pada karakteristik kode yang lebih penting.
- Konvensi membantu kita mentransfer pengetahuan lintas proyek. Kesamaan nama memberi kita pemahaman yang lebih mudah dan lebih percaya diri tentang apa yang seharusnya dilakukan oleh variabel yang tidak dikenal.
- Mereka membantu kita belajar kode lebih cepat pada proyek baru.
- Mereka mengurangi proliferasi nama. Tanpa konvensi penamaan, kita dapat dengan mudah menyebut hal yang sama dengan dua nama yang berbeda. Sebagai contoh, kita mungkin menyebut total poin dengan `pointTotal` dan `totalPoints`.
- Konvensi ini mengkompensasi kelemahan bahasa. Konvensi dapat membedakan antara data lokal, kelas, dan global.
- Mereka menekankan hubungan di antara item-item yang terkait.

**Kapan Kita Harus Memiliki Konvensi Penamaan?**
- Ketika beberapa programmer sedang mengerjakan sebuah proyek
- Ketika kita berencana untuk menyerahkan program kepada programmer lain untuk modifikasi dan pemeliharaan
- Ketika program kita ditinjau oleh programmer lain dalam organisasi kita
- Ketika program kita begitu besar sehingga kita tidak dapat menyimpan semuanya di otak kita sekaligus dan harus memikirkannya secara terpisah-pisah
- Ketika program kita akan berumur cukup panjang sehingga kita mungkin mengesampingkannya selama beberapa minggu atau bulan sebelum mengerjakannya lagi
- Ketika kita memiliki banyak istilah yang tidak biasa yang umum pada suatu proyek dan ingin memiliki istilah atau singkatan standar untuk digunakan dalam pengkodean

Kita selalu mendapat manfaat dari memiliki semacam konvensi penamaan. Pertimbangan-pertimbangan di atas akan membantu kita menentukan sejauh mana konvensi yang akan digunakan pada proyek tertentu.

> Pertimbangan yang paling penting dalam penamaan variabel adalah bahwa nama tersebut sepenuhnya dan secara akurat menggambarkan entitas yang diwakili oleh variabel tersebut.
> 
> > Nama variabel yang baik adalah elemen kunci dari keterbacaan program.

## Daftar Pustaka:
- Martin, R. C. (2009). Clean code: a handbook of agile software craftsmanship. Pearson Education.
- McConnell, S. (2004). Code complete. Pearson Education.

Terima kasih kepada Julien Dephix, Ben Sinclair, dan penasihat lainnya yang telah membantu memperbaiki artikel ini.