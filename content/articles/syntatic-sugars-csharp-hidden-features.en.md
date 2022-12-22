---
title: "Syntatic Sugars | C# Hidden Features"
date: 2022-12-22T18:24:03+07:00
draft: false
tags: ["Programming", "Unity", "C#"]
---

**Note:**
> To be able to use these features we need at least C# version 7 and above or Unity 2018 and above.

---

## Ternary Operator

In computer programming, the ternary conditional operator is a ternary operator that is part of the syntax for basic conditional expressions in several programming languages.It is commonly referred to as the conditional operator, ternary if, or inline if. 

> An expression `a ? b : c` evaluates to `b` if the value of `a` is true, and otherwise to `c`. One can read it aloud as "*if a then b otherwise c*".

Normal `if` statement:

```csharp
if (health > 0) {
    barColor = Color.red;
}
else {
    barColor = Color.black
}
```

`if` statement using ternary operator:

```csharp
barColor = health > 0 ? Color.red : Color.black;
```

---

## String Interpolation

The special character `$` identifies a string literal (unformatted string) as an interpolated string. An interpolated string is a literal string that may contain an interpolated expression.

> Interpolated strings provide a more readable and convenient syntax for formatting strings.

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


Expression body definitions allow us to provide property implementations in a very concise and readable form. 

The expression body definition has the following general syntax: `member => expression;`

Normal property:

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

Expression-body porperty:

```csharp
private float health, maxHealth;

public float HealthPrencentage {
    get => health / maxHealth;
    set => health = value * maxHealth;
}
```

Expression-body read-only property:

```csharp
public float HealthPrencentage => health / maxHealth;
```

&nbsp

Normal method:

```csharp
public float Percentage(float current, float max) {
    return current / max;
}
```

Expression-body method:

```csharp
public float Percentage(float current, float max) => current / max;
```

---

## Local Function

Local functions are methods that are nested inside other methods. They can only be called from the method that contains them. 

Local functions make the intent of our code clear. Anyone reading our code can see that this method cannot be called except by the method that contains it.

Normal method:

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

Simplifies a common coding pattern where a variable is assigned a value if it is null.

Common null checking:

```csharp
private event Action<GameObject> OnEnemyHit;

private void OnTriggerEnter2D(Collider2D other) {
    if (OnEnemyHit != null) OnEnemyHit.Invoke(other.gameObject);
}
```

Null checking operator:

```csharp
private event Action<GameObject> OnEnemyHit;

private void OnTriggerEnter2D(Collider2D other) {
    OnEnemyHit?.Invoke(other.gameObject);
}
```

### Null Coalescing

The null-coalescing operator `??` returns the value of its left-hand operand if it isn't null; otherwise, it evaluates the right-hand operand and returns its result. The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.

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

A `nameof` expression produces the name of a variable, type, or member as the string constant. A `nameof` expression is evaluated at compile time and has no effect at run time.

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

> In certain situations when we want to change the name of a variable, we don't need to change the string we created manually.

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