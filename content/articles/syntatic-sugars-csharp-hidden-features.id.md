---
title: "Syntatic Sugars | Fitur Tersembunyi C#"
date: 2022-12-22T18:24:06+07:00
draft: false
tags: ["Programming", "Unity", "C#"]
---

**Catatan:**
> Untuk dapat menggunakan fitur-fitur ini, kita membutuhkan setidaknya C# versi 7 ke atas atau Unity 2018 ke atas.

---

## Ternary Operator

Dalam pemrograman komputer, ternary operator adalah merupakan bagian dari sintaks untuk ekspresi kondisional dasar dalam beberapa bahasa pemrograman, biasanya disebut sebagai operator kondisional, *ternary if*, atau *inline if*. 

> Sebuah ekspresi `a ? b : c` dievaluasi ke `b` jika nilai `a` benar, dan sebaliknya ke `c`. Atau secara singkat: "*jika a maka b jika tidak maka c*".

Ekspresi kondisional menggunakan `if`:

```csharp
if (health > 0) {
    barColor = Color.red;
}
else {
    barColor = Color.black
}
```

Ekspresi kondisional menggunakan ternary operator:

```csharp
barColor = health > 0 ? Color.red : Color.black;
```

---

## String Interpolation

Karakter khusus `$` mengidentifikasi string literal (string tanpa format) sebagai string interpolasi. String interpolasi adalah string literal yang mungkin berisi ekspresi interpolasi.

> Interpolasi string menyediakan sintaks yang lebih mudah dibaca dan nyaman untuk memformat string.

```csharp
string name = "Groot";
float health = 100;
float mana = 50;

// operator '+'
logMessage = "Unit " + name + ", health: " + health + ", mana: " + mana;

// string.Format
logMessage = string.Format("Unit {0}, health: {1}, mana: {2}", name, health, mana);

// string interpolation
logMessage = $"Unit {name}, health: {health}, mana: {mana}";

```

---

## Expression Body

Definisi expression body memungkinkan kita menyediakan implementasi property dalam bentuk yang sangat ringkas dan mudah dibaca. 

Definisi expression body memiliki sintaks umum berikut ini: `anggota => ekspresi;`

Properti normal:

```csharp
private float health, maxHealth;

public float HealthPrencentage {
    get {
        return health / maxHealth;
    }
    
    set {
        health = value * maxHealth;
    }
}
```

Properti expression-body:

```csharp
private float health, maxHealth;

public float HealthPrencentage {
    get => health / maxHealth;
    set => health = value * maxHealth;
}
```

read-only properti expression-body:

```csharp
public float HealthPrencentage => health / maxHealth;
```

&nbsp

Method normal:

```csharp
public float Percentage(float current, float max) {
    return current / max;
}
```

Method expression-body:

```csharp
public float Percentage(float current, float max) => current / max;
```

---

## Local Function

Local functions adalah method-method yang bersarang di dalam method yang lain. Mereka hanya bisa dipanggil dari method yang mengandungnya. 

Local functions membuat maksud dari kode kita menjadi jelas. Siapa pun yang membaca kode kita dapat melihat bahwa method ini tidak dapat dipanggil kecuali oleh method yang mengandungnya.

Method normal:

```csharp
public void UpdateHealthBar() {
    StartCoroutine(UpdateHealthBarCoroutine());
}

private IEnumerator UpdateHealthBarCoroutine() {
    yield return null;
}
```

Local function:

```csharp
public void UpdateHealthBar() {
    StartCoroutine(UpdateHealthBarCoroutine());

    IEnumerator UpdateHealthBarCoroutine() {
        yield return null;
    }
}

```

---

## Null Checking

Menyederhanakan pola pengkodean umum di mana variabel diberi nilai jika null.

Pengecekan null yang umum:

```csharp
private event Action<GameObject> OnEnemyHit;

private void OnTriggerEnter2D(Collider2D other) {
    if (OnEnemyHit != null) OnEnemyHit.Invoke(other.gameObject);
}
```

Operator null checking:

```csharp
private event Action<GameObject> OnEnemyHit;

private void OnTriggerEnter2D(Collider2D other) {
    OnEnemyHit?.Invoke(other.gameObject);
}
```

### Null Coalescing

Operator null-coalescing `??` mengembalikan nilai dari operasi kiri jika operasi kiri tidak null; jika tidak, operator ini mengevaluasi operasi kanan dan mengembalikan hasilnya. Operator `??` tidak mengevaluasi bagian kanan operasi kanannya jika operasi kiri bernilai non-null.

```csharp
public class GameManager : MonoBehaviour {
    private Player player;

    // using null comparison
    public Player GetPlayer() {
        if (player == null) return new Player("Groot");
        else return player;
    }

    // using null coalescing operator
    public Player GetPlayer() {
        return player ?? new Player("Groot");
    }
}
```

---

## `nameof` Keyword

Ekspresi `nameof` menghasilkan nama variabel, tipe, atau member sebagai konstanta string. Ekspresi `nameof` dievaluasi pada waktu kompilasi dan tidak berpengaruh pada waktu berjalan.

```csharp
public class Enemy {
    public string name;
    public flaot health;
}

Enemy enemy = new Enemy("Groot", 100);

// will print -> name: Groot, health: 100
Debug.Log($"name: {enemy.name}, health: {enemy.health}");\

// will print -> name: Groot, health: 100
Debug.Log($"{nameof(Enemy.name)}: {enemy.name}, {nameof(Enemy.health)}: {enemy.health}");

```

> Dalam situasi tertentu ketika kita ingin mengubah nama variabel, kita tidak perlu mengubah string yang kita buat secara manual.

```csharp
public class Enemy {
    public string id;
    public flaot hp;
}

Enemy enemy = new Enemy("Groot", 100);

// will print -> name: Groot, health: 100
Debug.Log($"name: {enemy.id}, health: {enemy.hp}");\

// will print -> id: Groot, hp: 100
Debug.Log($"{nameof(Enemy.id)}: {enemy.id}, {nameof(Enemy.hp)}: {enemy.hp}");

```

---

**Source:**

{{< youtube mrV4g4Dq5h4 >}}