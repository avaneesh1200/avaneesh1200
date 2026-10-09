<!--
  ┌─────────────────────────────────────────────────────────────┐
  │  My First 2 Weeks with C++ · Avaneesh Shahi                 │
  │  Renders nicely on GitHub, dev.to, Obsidian, etc.           │
  └─────────────────────────────────────────────────────────────┘
-->

# 🧠 My First 2 Weeks with C++: Moving Beyond Hello, World!

> **A beginner's honest log** — what I broke, what clicked, and why documentation matters more than tutorials.
>
> *Written by Avaneesh Shahi · 9 October 2026 · 4 min read*

![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![Beginner](https://img.shields.io/badge/level-beginner-brightgreen?style=for-the-badge)
![Status](https://img.shields.io/badge/status-learning-blue?style=for-the-badge)

---

Before moving further into this blog, I would like to introduce you to **Hello, World!** in C++.

## 📘 1. C-Style C++

```c
#include <cstdio>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

<details>
<summary><b>🔍 Line-by-line breakdown</b> (click to expand)</summary>

<br>

- `#include <cstdio>` — A preprocessor directive that includes the standard C input/output library. It provides access to functions like `printf`. In C, this is typically written as `<stdio.h>`.
- `int main()` — The entry point for every C/C++ program. Execution starts here. The `int` indicates that the function returns an integer status code to the operating system upon completion.
- `printf("Hello, World!\n");`
  - `printf` (formatted print) sends output directly to the standard output buffer.
  - `"Hello, World!\n"` is a string literal.
  - `\n` is an escape sequence for a newline character, moving the cursor to the next line.
- `return 0;` — Signals to the operating system that the program executed successfully without any errors.

</details>

## 📗 2. Standard C++ Style (Modern Idiomatic C++)

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

<details>
<summary><b>🔍 Line-by-line breakdown</b> (click to expand)</summary>

<br>

- `#include <iostream>` — Includes the C++ input/output stream header. This header defines objects like `std::cout`, `std::cin`, and `std::endl`.
- `int main()` — The primary execution entry point for any C/C++ program.
- `std::cout` — Stands for "character output". It is an output stream object connected to the standard console output.
- `::` (Scope Resolution Operator) — Specifies that `cout` belongs to the `std` (standard) namespace, preventing naming conflicts with user-defined code.
- `<<` (Stream Insertion Operator) — Sends the string `"Hello, World!"` into the `std::cout` stream buffer to display it on the screen.
- `std::endl;` — A stream manipulator that inserts a newline character (`\n`) and flushes the output buffer immediately to guarantee output is visible right away.
- `return 0;` — Indicates successful termination of the program.

</details>

---

## 🧩 Quick comparison

| Feature | C-Style (`cstdio`) | Modern C++ (`iostream`) |
|---|---|---|
| Header | `<cstdio>` / `<stdio.h>` | `<iostream>` |
| Output | `printf()` | `std::cout` |
| Newline | `\n` | `std::endl` or `\n` |
| Type safety | ❌ Not type-safe | ✅ Type-safe |
| Speed | ⚡ Faster | Slightly slower |
| Verbosity | Less | More |

> 💡 **My take:** Start with modern C++. You can always learn the C-style later when you touch legacy code.

---

## 🛠️ How the first two weeks actually went

Now, let's talk about how my first two weeks with C++ actually went.

**First of all**, C++ can be an extremely rewarding language, but it can also be a pain to debug — and I experienced that myself in my first small project 👉 [github.com/avaneesh1200/myprojects-cpp](https://github.com/avaneesh1200/myprojects-cpp).

**The best way to learn C++**, I think, is not by watching tutorials but by writing small tasks — even simple ones, like printing `"Hi"` on the screen five times using `cout`.

**One more thing we should think about:** the ability to learn any language, especially mid-level languages created in the 70s or 80s.

> 📖 Being able to read documentation helps us discover more of the concepts that exist in the language — because only a small part of C++ shows up in online tutorials, while almost all of it lives in the documentation. For older versions *and* newer ones too.

So a beginner like me should read the documentation *(which I actually did)* and shouldn't run away from it just because:

- 🙈 the UI feels ugly,
- 😵 the English feels confusing,
- 🤔 or the words feel strange.

And we also shouldn't paste documentation — big or small — straight into an AI tool and ask it to summarise. Because then we're not really building one of the more important skills in software development:

> ✍️ **The ability to read and write documentation.**

I might be wrong somewhere, but this is what I've felt so far.

---

## 🧮 My hand-typed Fibonacci program

In these 14 days I learned many new concepts, and I also completed my hand-typed Fibonacci program.

```cpp
#include <iostream>

int main() {
    int times;
    long long x = 0;
    long long y = 1;
    long long result;

    std::cout << "Enter the number: ";
    std::cin >> times;
    times = times - 2;
    std::cout << x << std::endl;
    std::cout << y << std::endl;

    for (int i = 0; i < times; ++i) {
        if (x > y) {
            result = x + y;
            std::cout << result << std::endl;
            y = result;
        }
        else if (x == y || x < y) {
            result = x + y;
            std::cout << result << std::endl;
            x = result;
        }
    }
}
```

<details>
<summary><b>🤔 A note on this code</b> (click to expand)</summary>

<br>

Might be bad logic, or it may not be performance efficient, but I liked it a lot because it was hand-typed by me and I didn't have to search how the code looked in other programs.

The `x` and `y` swap pattern I used isn't the cleanest way to do Fibonacci — most people would just do:

```cpp
long long a = 0, b = 1;
for (int i = 0; i < times; ++i) {
    std::cout << a << std::endl;
    long long next = a + b;
    a = b;
    b = next;
}
```

But that's fine. The point wasn't to write the *best* Fibonacci — it was to write **my own** Fibonacci.

</details>

I learned about various low-level topics also, and what the steps are to optimise a program.

---

## 🎯 Takeaways

| Lesson | Why it matters |
|---|---|
| Write small programs | Reading code ≠ writing code |
| Read the docs | Tutorials cover ~10% of C++ |
| Don't outsource thinking to AI | Reading docs *is* the skill |
| Finish something, even if it's ugly | Momentum > perfection |

---

## 🙏 Final words

This was my experience.

If you're also starting out with C++ — you're not alone. It gets easier. Or at least, you get used to it. 😄

---

*~ Avaneesh*

*Last updated: 9 October 2026 IST*

<!--
  ────────────────────────────────────────────────
  📝 Note for the author:
  This file renders beautifully on:
    • GitHub (badges, tables, details/summary all work)
    • dev.to & Hashnode (import as-is)
    • Obsidian & Logseq (native)
    • VS Code Markdown preview
  ────────────────────────────────────────────────
-->