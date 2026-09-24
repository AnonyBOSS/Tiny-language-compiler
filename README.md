# Tiny Language Compiler (Front End)

A scanner and recursive-descent parser for the **Tiny** programming language, written in C# with a Windows Forms UI that shows the token stream, the parse tree, and any errors.

---

## 💡 Tiny Language Features

- **Data Types**: `int`, `float`, `string`
- **Identifiers**: Must start with a letter, followed by letters/digits
- **Numbers**: Integers and floating-point (e.g., `123`, `3.14`)
- **Strings**: Text enclosed in double quotes (`"Hello World"`)
- **Operators**: `+`, `-`, `*`, `/`, `:=`, `<`, `>`, `=`, `<>`, `&&`, `||`
- **Control Keywords**: `if`, `elseif`, `else`, `then`, `repeat`, `until`, `return`
- **I/O**: `read`, `write`, `endl`
- **Comments**: `/* ... */`
- **Delimiters**: `()`, `{}`, `[]`, `,`, `;`

---

## ⚙️ How It Works

1. **Lexical analysis** — [`Scanner.cs`](Tiny_language/JASON_Compiler/Scanner.cs)
   Scans the source character by character into tokens, using reserved-word and operator tables plus regular expressions for identifiers and numbers. Lexical errors (invalid tokens or identifiers, malformed numbers, unclosed comments) are reported.

2. **Syntax analysis** — [`Parser.cs`](Tiny_language/JASON_Compiler/Parser.cs)
   A recursive-descent parser with one method per grammar rule (program, functions, declarations, `if`/`elseif`/`else`, `repeat … until`, boolean conditions, expressions, function calls). Left recursion is removed from the grammar, and the parser builds a parse tree.

3. **UI** — [`Form1.cs`](Tiny_language/JASON_Compiler/Form1.cs)
   Paste Tiny source code, compile, and inspect the token table, the parse tree, and the error list.

The context-free grammar is documented in [`Tiny_Language_CFG_Final.docx`](Tiny_Language_CFG_Final.docx).

---

## 🚀 Running It

Requires Windows, Visual Studio, and .NET Framework 4.8.

1. Open `Tiny_language/JASON_Compiler.sln` in Visual Studio.
2. Build and run (F5).
3. Paste a Tiny program into the editor and compile it.

---

## 📁 Layout

```
Tiny_language/
├── JASON_Compiler.sln
└── JASON_Compiler/
    ├── Scanner.cs          # tokens, reserved words, operators
    ├── Parser.cs           # recursive-descent parser + parse tree
    ├── Errors.cs           # shared error list
    ├── JASON_Compiler.cs   # runs scanner then parser
    └── Form1.cs            # WinForms UI
Tiny_Language_CFG_Final.docx  # grammar
```
