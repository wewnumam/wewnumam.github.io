---
title: "Agate MVC Case Study"
date: 2025-05-05T20:31:05+07:00
draft: false
---

## 1. 📖 Introduction

Unity has become one of the most popular game engines. However, Unity's built-in component-based pattern often leads to:

* 🔄 **Tight coupling of code**
* 🗃️ **Unstructured persistent data management**
* 🕹️ **Abuse of Singleton pattern**

To overcome this, the “City of Philosophy” case study utilizes **Model-View-Controller (MVC)** via **Agate MVC Framework**, clearly separating data, logic, and views.

---

## 2. 🎯 Objectives & Benefits

* **Objectives**

  1. Implement MVC in Unity using Agate MVC.
  2. Evaluate the code quality and architecture of the game “City of Philosophy”.
* **Benefits**

  * **Academic**: Reference for MVC practice in game development.
  * **Students**: Increased game programming readiness and competency.
  * **Industry**: Game products are more **modular**, **scalable**, and **maintainable**.

---

## 3. 🔍 Common Challenges

* **Persistent data** difficult to manage between scenes
* **Singleton overuse** inhibits flexibility and testing
* **Code coupling** complicates maintenance & development of new features

---

## 4. 💡 MVC Architecture Solution

***Model**
  - Stores & manages data
**View**
  - Display UI & accept input
**Controller**
  - Connects Model & View, handles logic

> “With MVC, UI changes don't break the logic, and vice versa.”

---

## 5. 📦 Agate MVC Framework

Key features:

* 🗂️ **Layered Architecture** (Global vs Scene-specific modules)
* 🔌 **Dependency Injection (DI)**
* 📣 **Publish-Subscribe (Pub-Sub)**
* ⚙️ **Boot System & Scene Launcher**

Helps break down code into self-contained, easily testable modules.

---

## 6. 🕹️ Case Study: “City of Philosophy”

### 6.1. Game Flow

1. **Splash Screen**: Logo & game version
2. **Main Menu**: Play/Quiz Navigation
3. **Cutscene**: Story narration
4. **Level Selection**: Select level & preview
5. **Gameplay**: Shooter + puzzle + collect
6. **Quiz**: Knowledge question

### 6.2. Model Structure

| Model Type | Model Name | Brief Function |
| ------------- | ---------------- | --------------------------------------------- |
| **Persistent** | LevelData | Collectible level & progress unlocks
| | CollectibleData | Item & collectible data |
| | QuestData | Mission list & progress
| | GameSettings | Volume, vibration, tutorial |
| **Temporary** | CutscenePlayer | Dialog assets & cutscene progress |
| (per scene) | LevelSelection... | Selected level assets |
| | Mission, Health... | Gameplay logic (lives, enemies, puzzles, timers) |
| | QuizPlayer | Quiz questions & scores |

### 6.3. Controller Structure

| Controller Type | Controller Name | Responsibilities |
| ---------------- | ------------------------------------- | ---------------------------------- |
| **Persistent** | LevelData, QuestData... | Stores & processes global data |
| **Temporary** | MainMenu, GamePause, PlayerCharacter... | Manage local UI & gameplay events |

---

## 7. 🧪 Development Methodology

Following the **Game Development Life Cycle (GDLC)**:

1. **Initiation**: Concept & target audience
2. **Pre-Production**: GDD, UI mockup, basic prototype & structure
3. **Production**: Asset & code integration, optimization
4. **Testing**:
   * **Black-Box** (functions according to specifications)
   * **Unit Testing** (≥ 80% code coverage)
   * **Static Code Analysis** (SonarQube, Code Metrics)
5. **Beta**: Open/closed playtesting & survey
6. **Release**: Launch & maintenance plan

---

## 8. 📊 Evaluation Results

**SonarQube & Code Metrics**: Code quality **high**, technical debt **low**
* **Unit Testing Coverage**: Achieved **≥ 80%**
* **Survey (n=6)**:

  * 91.7% rated **code structure as very good**
  * 66.7% stated **ease of maintenance & development**

---

## 9. ✨ Conclusion

The implementation of **MVC** with **Agate MVC Framework** on the game “City of Philosophy” was successful:

* 🏗️ **Build an organized code structure**
* 🔄 **Easier iteration & testing**
* 📈 **Supports larger game scale**

> **Recommendation**: Adopt this approach for other Unity projects to improve **modularity**, **scalability**, and **development efficiency**!
