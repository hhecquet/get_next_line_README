# get_next_line

> [!IMPORTANT]
> None of my code is publicly available here, but if you're a recruiter, I'd be happy to share it with you upon request.

<p align="center">
  <img width="317" height="268" alt="Screenshot from 2025-07-23 08-57-06" src="https://github.com/user-attachments/assets/bfae2c73-7a26-403d-acda-06b6cd9f967a" />
</p>

The ***get_next_line*** project is a foundational exercise at 42 that challenges you to implement a function in C capable of reading a file (or any file descriptor) line by line. Unlike standard functions like fgets or getline, you're tasked with creating your own logic to handle file input using only low-level functions like read.
The core goal is to return each line of a file — including the newline character — on successive calls, all while efficiently managing memory and buffer usage.

What I had to do:
* I implemented the function `get_next_line(int fd)` to:
* Read from a file descriptor until a full line is found (ending in `\n` or `EOF`)
* Return that line, dynamically allocating the necessary memory
* Maintain state between function calls to continue reading where it left off
* Handle multiple file descriptors simultaneously (bonus part)
* To achieve this, I had to:
  * Use static variables to store leftover data between function calls
  * Carefully manage buffer allocation and joining strings across reads
  * Handle cases where a line is split across multiple reads
  * Ensure memory is freed appropriately in case of errors or EOF

Bonus Part: Multi-FD Support & Efficiency
* For the bonus part, I extended get_next_line to:
* Work with multiple file descriptors at the same time, using one buffer per descriptor
* Handle edge cases like reading from empty files, very long lines, or interrupted reads
* Optimize memory usage and avoid leaks with precise error handling

What I Learned:
* Efficient reading from file descriptors using low-level I/O (read)
* Managing dynamic memory and buffers in C
* Handling persistent state across function calls
* Dealing with edge cases like `EOF`, null lines, or buffer overflows
* Implementing robust and leak-free code under strict constraints

get_next_line may sound simple on the surface, but it taught me the complexity involved in even basic input operations. It strengthened my skills in memory management, string manipulation, and modular coding — all without relying on the standard library beyond a few allowed functions.
