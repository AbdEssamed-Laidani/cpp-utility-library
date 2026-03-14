# 📦 C++ Utility Library

A collection of reusable C++ header-only classes built from scratch, covering date manipulation, string operations, input validation, and general utilities.

---

## 📁 Classes Overview

| Class | Description |
|---|---|
| `clsDate` | Full-featured date handling |
| `clsString` | String manipulation utilities |
| `clsInputValidate` | Safe & validated user input |
| `clsUtil` | General-purpose utilities |

---

## 📌 clsDate

A comprehensive date class supporting arithmetic, formatting, calendar printing, and comparisons.

### Features
- Multiple constructors: from string, from `Day/Month/Year`, from day order in year
- Leap year detection
- Day of week calculation (Zeller's algorithm)
- Calendar printing (monthly & yearly)
- Date comparison (`<`, `==`, `>`)
- Date arithmetic (increase/decrease by one day, difference between dates)
- Days until end of week / month / year
- System date retrieval

### Example
```cpp
clsDate d1("25/12/2024");
clsDate d2(31, 12, 2024);

std::cout << clsDate::DiffrenceDaysBetweenDates(d1, d2); // 6
std::cout << clsDate::NameOfDay(d1.FindOrderOfDay());     // Wednesday

clsDate::PrintCalendar(2024, 12); // Prints December 2024 calendar
```

---

## 📌 clsString

A string utility class with both static and instance methods.

### Features
- Case conversion (upper/lower, first letter of each word)
- Character counting (vowels, capital, small, specific)
- Word counting and splitting
- String trimming (left, right, both)
- String reversing (word-by-word)
- Find & replace words
- Remove punctuation
- Join vector of strings with delimiter

### Example
```cpp
clsString s("  hello world  ");
std::cout << s.TrimText();                          // "hello world"
std::cout << clsString::UpperFirstLetterOfEachWord("hello world"); // "Hello World"

std::vector<std::string> parts = clsString::SplitText("a,b,c", ",");
// parts = {"a", "b", "c"}
```

---

## 📌 clsInputValidate

A template-based input validation class for safe console input.

### Features
- Read any numeric type with automatic retry on invalid input
- Read positive numbers only
- Read numbers within a specified range
- Date range validation
- Read strings and single characters safely

### Example
```cpp
int age = clsInputValidate::ReadPositiveNumberInRange<int>(
    "Enter age: ", 1, 120
);

std::string name = clsInputValidate::ReadString("Enter name: ");

bool valid = clsInputValidate::IsDateBetween(today, startDate, endDate);
```

---

## 📌 clsUtil

A general-purpose utility class covering numbers, arrays, matrices, files, and more.

### Features
- Random number & character/word/key generation
- Number utilities: reverse, palindrome, perfect number, prime check
- Array operations: sort, shuffle, remove duplicates, min/max, sum
- Matrix operations: multiply, sum, identity/scalar/sparse/palindrome checks
- File operations: read, write, append, delete & update records
- Text encryption/decryption (Caesar cipher)
- Convert numbers to words (up to billions)

### Example
```cpp
// Random key generation
std::string key = clsUtil::GenerateKey(clsUtil::CapitalLetter, 4);
// e.g. "ABCD-EFGH-IJKL-MNOP"

// Number to words
std::cout << clsUtil::numberToWords(1234567);
// "One Million Two Hundred Thirty Four Thousand Five Hundred Sixty Seven"

// File operations
clsUtil::LoadFileDataToVector("data.txt", myVector);
clsUtil::SaveVectorToFile("output.txt", myVector);
```

---

## 🚀 Usage

All classes are **header-only**. Simply include the relevant `.h` file in your project:

```cpp
#include "clsDate.h"
#include "clsString.h"
#include "clsInputValidate.h"
#include "clsUtil.h"
```

> ⚠️ Note: `clsInputValidate.h` depends on `clsDate.h`, and `clsDate.h` depends on `clsString.h`. Make sure all files are in the same directory.

---

## 🛠️ Requirements

- C++17 or later
- Standard library only — no external dependencies

---

## 👤 Author

Built as part of my C++ learning journey — focusing on OOP, reusable design, and building things from scratch.
