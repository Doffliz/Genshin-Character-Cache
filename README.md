# Genshin Character Cache Core

This repository contains the Core Business Logic Layer for the Genshin Character Application project, developed as part of Practical Assignment 15: Data Persistence (Caching).

## 🎯 Project Goal

The primary goal of this layer is to ensure efficient handling of Genshin Impact character data by minimizing network load and improving user experience through the implementation of an **Image Caching** mechanism.

## ✨ Implemented Functionality (Practical Assignment 15)

The project implements the following key persistence and caching features:

* **Image Caching:** A mechanism has been introduced to store character portraits (image raw data) directly in the user's local file system.
* **Cache Location:** The cache is stored in a dedicated directory located within the special system folder for application data (Environment.SpecialFolder.LocalApplicationData), typically mapped to `C:\Users\AppData\Local\GenshinCharacterCache`.
* **Persistence Logic (Cache Hit/Miss):**
    * **Cache Miss:** On the first request, the image is downloaded from the network (URL) and saved to the local disk.
    * **Cache Hit:** On subsequent requests, the image is loaded immediately from the local cache, avoiding a network request and reducing load time.
* **Architecture:** The core caching logic is implemented in the **`ImageCacheManager`** class and integrated into the **`CharacterService.cs`**.

## 💻 How to Run the Project

The project is developed on **.NET Core** and is designed to be executed via the console.

### Requirements

* **NET Core SDK** (version 6.0 or newer) installed.

### Execution Steps

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Doffliz/Genshin-Character-Cache-Core.git](https://github.com/Doffliz/Genshin-Character-Cache-Core.git)
    ```
2.  **Navigate to the project directory:**
    ```bash
    cd Genshin-Character-Cache-Core
    ```
3.  **Run the application:**
    ```bash
    dotnet run
    ```

### Expected Test Result

Running `dotnet run` should output a test sequence demonstrating the cache mechanism's functionality:

| Test | Operation | Expected Status |
| :--- | :--- | :--- |
| **Test 1** (Cache Miss) | First Image Request | Image downloaded from the URL and saved locally. |
| **Test 2** (Cache Hit) | Second Image Request | Image loaded **from the local cache** immediately. |

> 

---

## 📄 Project Documentation

A detailed description of the architecture, caching strategy, flow of operation, and cache calculation formulas is provided in the accompanying **Design Document** (Task 15 - Design Document).
