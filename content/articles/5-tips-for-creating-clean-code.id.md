---
title: "5 Tips untuk Membuat Kode yang Bersih"
date: 2022-12-29T05:39:14+07:00
draft: false
tags: ["Programming", "Technical Skill"]
---

Clean code adalah kode yang mudah dibaca, dipahami, dan dikelola. Kode bersih mengikuti seperangkat standar dan prinsip pengkodean yang bertujuan untuk membuat kode dapat dimengerti dan dirawat sebaik mungkin.

Clean code penting karena membantu mengurangi waktu dan upaya yang diperlukan untuk memahami dan memodifikasi basis kode, dan membuatnya lebih mudah untuk menambahkan fitur baru atau memperbaiki bug. Ini juga mendukung kolaborasi dan mengurangi risiko memperkenalkan masalah baru saat memodifikasi kode.

Untuk mencapai kode yang bersih, penting untuk mengikuti praktik terbaik untuk menamai variabel dan function, menggunakan format yang jelas dan konsisten, menjaga function tetap kecil dan terfokus, menghindari kerumitan yang tidak perlu, dan menulis kode yang mendokumentasikan diri sendiri. Penting juga untuk mengikuti standar pengkodean yang telah ditetapkan dan secara konsisten menerapkan prinsip-prinsip ini di seluruh basis kode.

Berikut adalah lima prinsip penting dari Clean Code, bersama dengan beberapa contoh kode untuk mengilustrasikan setiap prinsip:

## Gunakan Nama yang Dapat Dicari

Nama yang baik mudah dicari dan memudahkan untuk memahami tujuan kode. Gunakan nama yang deskriptif dan bermakna yang secara akurat mencerminkan tujuan variabel atau function.

Buruk:

```java
int computeTotalCost(int quantity, int pricePerItem)
{
    return quantity * pricePerItem + 5;
}
```

Dalam contoh ini, biaya tambahan $5 ditambahkan langsung ke perhitungan, tanpa konteks atau penjelasan apa pun. Hal ini membuat lebih sulit untuk memahami tujuan kode dan memodifikasinya jika perlu.

Cara yang lebih baik untuk mengimplementasikan kode ini adalah dengan menggunakan konstanta deskriptif untuk mewakili biaya tambahan:

Bagus:

```java
int computeTotalCost(int quantity, int pricePerItem)
{
    final int SHIPPING_COST = 5;
    return quantity * pricePerItem + SHIPPING_COST;
}
```

Versi kode ini lebih mudah dipahami dan dimodifikasi, karena tujuan biaya tambahan dijelaskan dengan jelas dengan penggunaan konstanta deskriptif.

## Nama Function Harus Berupa Kata Kerja dan Function Harus Melakukan Satu Hal Saja

Function harus memiliki nama deskriptif yang mencerminkan tindakan yang mereka lakukan, dan mereka harus melakukan satu hal saja. Function yang melakukan lebih dari satu hal lebih sulit untuk dipahami dan dikelola.

Buruk:

```java
int calc(int x, int y)
{
    int z = x + y;
    int w = x * y;
    return z - w;
}
```

Bagus:

```java
int add(int x, int y)
{
    return x + y;
}

int multiply(int x, int y)
{
    return x * y;
}

int subtract(int x, int y)
{
    return add(x, y) - multiply(x, y);
}
```

## Tiga atau Lebih Sedikit Argumen dalam Function

Function dengan terlalu banyak argumen sulit untuk dipahami dan dikelola. Bertujuan untuk menjaga jumlah argumen dalam function menjadi tiga atau kurang. Jika sebuah function membutuhkan lebih dari tiga argumen, pertimbangkan untuk mem-refactoring kode untuk menggunakan objek atau struktur data untuk meneruskan argumen.

Buruk:

```java
void printInvoice(int customerId, int invoiceNumber, int itemNumber, int quantity, int pricePerItem, int discountPercent, int taxPercent)
{
    // code to print invoice
}
```

Bagus:

```java
class Invoice
{
    int customerId;
    int invoiceNumber;
    int itemNumber;
    int quantity;
    int pricePerItem;
    int discountPercent;
    int taxPercent;
}

void printInvoice(Invoice invoice)
{
    // code to print invoice
}
```

## Hindari Memberikan Nilai Boolean sebagai Argumen dalam Function

Memberikan nilai boolean sebagai argumen ke function dapat membuat kode lebih sulit dipahami, karena tidak langsung jelas apa yang diwakili oleh nilai boolean. Sebaliknya, pertimbangkan untuk menggunakan nama deskriptif untuk argumen atau membuat ulang kode untuk menggunakan function dengan nama yang lebih deskriptif.

Buruk:

```java
void printMessage(string message, bool isError)
{
    if (isError)
    {
        Console.WriteLine("ERROR: " + message);
    }
    else
    {
        Console.WriteLine(message);
    }
}
```

Dalam contoh ini, nilai boolean `isError` dilewatkan sebagai argumen ke function, yang memerlukan pernyataan if tambahan untuk menentukan bagaimana mencetak pesan.

Cara yang lebih baik untuk mengimplementasikan kode ini adalah dengan menggunakan function dengan nama yang lebih deskriptif yang mencerminkan tujuan dari function tersebut:

Bagus:

```java
void printErrorMessage(string message)
{
    Console.WriteLine("ERROR: " + message);
}

void printMessage(string message)
{
    Console.WriteLine(message);
}
```

Versi kode ini lebih mudah dimengerti, karena tujuan dari function sudah jelas dari namanya, dan tidak perlu pernyataan if tambahan di dalam function.

## Hindari Penggunaan Nama Huruf

Menggunakan nama huruf tunggal untuk variabel dan function dapat membuat kode sulit dimengerti, karena tidak terlihat jelas apa yang diwakili oleh huruf-huruf tersebut. Sebaliknya, gunakan nama deskriptif yang secara akurat mencerminkan tujuan kode.

Buruk:

```java
int[][] data = new int[5][5];
for (int i = 0; i < 5; i++)
{
    for (int j = 0; j < 5; j++)
    {
        data[i][j] = i + j;
    }
}
```

Dalam contoh ini, variabel `i` dan `j` digunakan sebagai indeks untuk data array multidimensi, tetapi tidak jelas apa yang diwakili oleh huruf-huruf ini.

Cara yang lebih baik untuk mengimplementasikan kode ini adalah dengan menggunakan nama deskriptif untuk indeks:

Bagus:

```java
int[][] data = new int[5][5];
for (int row = 0; row < 5; row++)
{
    for (int col = 0; col < 5; col++)
    {
        data[row][col] = row + col;
    }
}
```

Versi kode ini lebih mudah dimengerti, karena tujuan dari variabel `row` dan `col` sudah jelas dari namanya.

---

Kesimpulannya, clean code adalah kode yang mudah dibaca, dipahami, dan dikelola. Ini mengikuti seperangkat standar dan prinsip pengkodean yang bertujuan untuk membuat kode dapat dibaca dan dirawat sebaik mungkin. 

Beberapa prinsip penting dari kode bersih termasuk menggunakan nama yang bermakna dan deskriptif, menggunakan format yang jelas dan konsisten, menjaga function tetap kecil dan terfokus, menghindari kerumitan yang tidak perlu, dan menulis kode yang mendokumentasikan diri sendiri. 

Dengan mengikuti prinsip-prinsip ini, kita dapat membuat kode yang lebih mudah dimengerti dan dimodifikasi, dan yang mendukung kolaborasi dan mengurangi risiko munculnya isu-isu baru ketika memodifikasi kode.

**Sumber:**

{{< youtube Jz8Sx1XYb04 >}}