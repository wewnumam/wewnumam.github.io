---
title: "5 Tips for Writing Clear and Concise Git Commit Messages"
date: 2023-01-01T05:27:25Z
draft: false
tags: ["Technical Skill"]
---

Writing good commit messages is an important practice that can help other people understand the changes that you have made and why. Here are some tips for writing better commit messages:

1. ## Use a clear and descriptive subject line
    
    The first line of the commit message should be a short and concise summary of the changes that you have made. Keep it to around 50 characters or less. This will help other developers quickly understand the changes that you have made.

    &nbsp

    Bad: 
    
    ```Update```

    &nbsp

    Good: 
    
    ```Fix typo in README file```


1. ## Use the imperative mood
    
    Use the imperative mood in the subject line, as if you are giving a command. For example, ```Fix bug``` or ```Add feature```. This helps to make the commit message more direct and actionable.

    &nbsp

    Bad: 
    
    ```Added feature to search bar```

    &nbsp

    Good: 
    
    ```Add feature to search bar```


1. ## Add more context in the body
    
    The body of the commit message should provide more detailed information about the changes that you have made. Explain why you made the changes and how they benefit the codebase. This will help other developers understand the reasoning behind your changes.

    &nbsp

    Bad: 
    
    ```(No body)```

    &nbsp

    Good: 
    
    ```I added a feature to the search bar that allows users to search for specific items by keyword. This will make it easier for users to find what they are looking for and should improve the overall user experience.```


1. ## Keep it concise
    
    Try to keep the commit message to around 72 characters per line. This makes it easier to read in the command line or in a git client.

    &nbsp

    Bad: 
    
    ```I fixed a bug that was causing the application to crash when a user tried to submit a form with an empty field. This was a really annoying bug and it took me a while to track it down, but I finally found it and was able to fix it. I hope this doesn't happen again.```

    &nbsp

    Good: 
    
    ```Fix bug that caused application to crash when submitting form with empty field```


1. ## Use bullet points
    
    If you have made multiple changes, use bullet points to list them out. This helps to organize the information and make it easier to read.

    &nbsp

    Bad: 
    
    ```I made a bunch of changes to the codebase. I fixed some bugs, added some new features, and refactored some of the code to make it more readable. I also added some tests to make sure everything is working properly.```

    &nbsp

    Good: 

    ```- Fix bug that caused application to crash when submitting form with empty field```

    ```- Add feature to search bar```

    ```- Refactor code for improved readability```
    
    ```- Add tests to ensure proper functionality```

---

## More Example

Here are some examples of good git commit messages that use bullet points in the body to clearly and concisely describe the changes made:

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

By following these tips, you can write commit messages that are clear, concise, and easy to understand. This will help other developers to more easily review and understand your code, which can lead to faster code review and deployment. So take some time to carefully craft your commit messages and you'll be on your way to writing better git commit messages in no time!