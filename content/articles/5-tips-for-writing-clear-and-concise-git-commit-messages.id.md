---
title: "5 Tips untuk Menulis Pesan Git Commit yang Jelas dan Ringkas"
date: 2023-01-01T05:27:33Z
draft: false
tags: ["Technical Skill"]
---


Menulis pesan commit yang baik adalah praktik penting yang dapat membantu orang lain memahami perubahan yang telah kita buat dan alasannya. Berikut ini beberapa kiat untuk menulis commit message yang lebih baik:

1. ## Gunakan baris subjek yang jelas dan deskriptif
    
    Baris pertama dari pesan commit harus berupa ringkasan singkat dan padat dari perubahan yang telah kita buat. Jaga agar panjangnya sekitar 50 karakter atau kurang. Ini akan membantu pengembang lain dengan cepat memahami perubahan yang telah kita buat.

    &nbsp

    Buruk: 
    
    ```Update```

    &nbsp

    Bagus: 
    
    ```Fix typo in README file```


1. ## Gunakan nada perintah
    
    Gunakan gaya bahasa imperatif dalam baris subjek, seolah-olah kita sedang memberikan perintah. Misalnya, ```Fix bug``` atau ```Add feature```. Ini membantu membuat pesan commit lebih lugas dan dapat ditindaklanjuti.

    &nbsp

    Buruk: 
    
    ```Added feature to search bar```

    &nbsp

    Bagus: 
    
    ```Add feature to search bar```


1. ## Tambahkan lebih banyak konteks di body
    
    Body dari pesan commit harus memberikan informasi yang lebih rinci tentang perubahan yang telah kita buat. Jelaskan mengapa kita membuat perubahan dan bagaimana perubahan itu bermanfaat bagi basis kode. Ini akan membantu pengembang lain memahami alasan di balik perubahan kita.

    &nbsp

    Buruk: 
    
    (No body)

    &nbsp

    Bagus: 
    
    ```I added a feature to the search bar that allows users to search for specific items by keyword. This will make it easier for users to find what they are looking for and should improve the overall user experience.```


1. ## Jaga agar tetap ringkas
    
    Usahakan untuk menjaga pesan commit menjadi sekitar 72 karakter per baris. Ini membuatnya lebih mudah dibaca di baris perintah atau di git client.

    &nbsp

    Buruk: 
    
    ```I fixed a bug that was causing the application to crash when a user tried to submit a form with an empty field. This was a really annoying bug and it toome a while to track it down, but I finally found it and was able to fix it. I hope this doesn't happen again.```

    &nbsp

    Bagus: 
    
    ```Fix bug that caused application to crash when submitting form with empty field```


1. ## Gunakan poin-poin
    
    Jika Anda telah membuat beberapa perubahan, gunakan poin-poin untuk mencantumkannya. Hal ini membantu mengatur informasi dan membuatnya lebih mudah dibaca.

    &nbsp

    Buruk: 
    
    ```I made a bunch of changes to the codebase. I fixed some bugs, added some new features, and refactored some of the code to make it more readable. I also added some tests to make sure everything is working properly.```

    &nbsp

    Bagus: 

    
    ```- Fix bug that caused application to crash when submitting form with empty field```

    ```- Add feature to search bar```

    ```- Refactor code for improved readability```

    ```- Add tests to ensure proper functionality```

---

## Contoh Lainnya

Berikut adalah beberapa contoh pesan commit git yang baik yang menggunakan poin-poin di body untuk menjelaskan perubahan yang dibuat dengan jelas dan ringkas:

1. "Fix typo in README file"

    - Corrected spelling error on line 5

1. "Add feature to search bar"

    - Added keyword search functionality
    - Improved UI of search bar

1. "Refactor code for improved readability"

    - Renamed variables to be more descriptive
    - Grouped related code into functions
    - Added comments to clarify code logic

1. "Improve performance of login page"

    - Optimized database queries
    - Reduced amount of data transferred between server and client
    - Added caching to improve response time

1. "Update dependencies to fix security vulnerabilities"

    - Upgraded library "X" to version 2.0
    - Replaced deprecated function "Y" with recommended alternative


1. "Fix bug that caused application to crash when submitting form with empty field"

    - Identified root cause of crash
    - Implemented fix to handle empty field input
    - Added tests to prevent similar issues in the future

1. "Add tests to ensure proper functionality"

    - Wrote tests for new features
    - Added coverage for edge cases
    - Improved reliability of existing tests

1. "Update documentation to reflect changes in API"

    - Added descriptions for new endpoints
    - Updated examples to reflect changes in request and response formats
    - Clarified usage of deprecated functions

1. "Rename variables for improved readability"

    - Renamed variables throughout codebase to be more descriptive
    - Adjusted tests and documentation to reflect renames
    - Improved code clarity and maintainability

1. "Refactor code to use new library"

    - Replaced old library with more feature-rich alternative
    - Adjusted code to use new library's API
    - Improved code performance and reliability


---

Dengan mengikuti tips-tips ini, kita dapat menulis pesan commit yang jelas, ringkas, dan mudah dimengerti. Ini akan membantu pengembang lain untuk lebih mudah meninjau dan memahami kode kita, yang dapat mempercepat review dan deployment kode. Jadi, luangkan waktu untuk membuat pesan commit-mu dengan hati-hati dan kamu akan bisa menulis pesan commit yang lebih baik dalam waktu singkat!