## Code Review for TextProcessing Repository
This pull request reviews the code of the TextProcessing repository. The program reads a text file, removes punctuation, converts words to lowercase, counts word occurrences, and displays unique words in alphabetical order. The review covers documentation, error handling, and seven key areas, with suggestions to improve clarity, usability, and robustness.

## 1. Is the Code Properly Documented/Commented?
The code includes some helpful comments (like "Read all lines" and "Dictionary to hold word counts"), but documentation is limited and could be more comprehensive.
### Needs Work?: 
Yes, moderate improvement is needed.
### Suggestions:
- Add a summary comment at the start of the Main method to explain what the program does.
- Add comments for complex operations like the regex pattern used for cleaning text.

## 2. Does the Code Handle Errors Properly?
The code includes basic error handling by checking if the file exists with File, but deeper error handling is missing.
### Needs Work?: 
Yes, moderate improvement is needed.
### Suggestions:
- Use a try-catch block for File.ReadAllLines to handle exceptions like IOException.
- Check if Console.ReadLine() input is null or empty.
- Handle empty or unreadable files gracefully.

## 3. Suggestions for Improvement

### Naming:
Variable names like wordCounts, filePath, lines, cleanedLine, and words are descriptive, which is good. However, pair in the output loop is generic and could be more specific.
Suggestion: Rename pair to wordEntry for clarity in the output loop.

### Code Structure:
All logic is in the Main method, with no separation into reusable functions, making the code less modular and harder to maintain or test.
Suggestion: Break it into methods like ReadFile(), CleanLine(), CountWords(), DisplayResults().

### Error Handling:
Only checks if the file exists.
suggestion: Add try-catch for full error handling for file reading and invalid inputs.

### File Assumptions:
Assumes the user enters a valid file path after the existence check. No default file (e.g., sample.txt) is provided, which could improve usability.
Suggestion: Use a default file like sample.txt 

### OOP Principles:
The code is procedural, with no classes or encapsulation, limiting reusability and modularity.
Suggestion: May Create a WordCounter class to encapsulate the dictionary and processing logic, with methods for reading, cleaning, counting, and displaying.

### Output:
Clear and sorted alphabetically.

### Program Logic:
Logic is efficient and correct. But for large files, use File.ReadLines instead of File.ReadAllLines to save memory.




Added code review for TextProcessing repository

