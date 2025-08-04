# ImageProcessing-Using-Dsl
A **Java-based DSL (Domain Specific Language)** image processing engine built using **ANTLR4**, Maven, and Swing GUI. It allows users to manipulate images via a custom scripting language with operations like grayscale, resize, rotate, flip, and save.

## 🚀 Features

- Custom DSL to control image operations.
- GUI interface to load, process, and view images.
- Integration with ANTLR4 to tokenize and parse DSL scripts.
- Built-in commands for:
  - Loading images
  - Resizing (width x height)
  - Grayscale conversion
  - Rotation (angle)
  - Flipping (horizontal, vertical, both)
  - Saving images in various formats

## 📁 Project Structure

```

├── parsingfiles/
│   ├── Imagescript.g4              # ANTLR grammar file
│   ├── Generated lexer/parser files
│   ├── MainApp.java                # Entry point for GUI
├── org/
│   └── DslProcessor.java           # Core script processing logic
├── resources/
│   └── test images / output files

````

## 🛠️ Build and Run Instructions

1. **Generate ANTLR files**  
   *(run this in the root directory where `Imagescript.g4` is located)*:
   ```bash
   java -jar path/to/antlr-4.13.1-complete.jar -Dlanguage=Java Imagescript.g4


2. **Build with Maven**:

   ```bash
   mvn clean install
   mvn clean compile
   ```

3. **Run the application**:

   ```bash
   mvn exec:java -Dexec.mainClass="org.MainApp"
   ```

> ⚠ Make sure to include ANTLR in your dependencies or add the jar to classpath manually.

## 🧪 DSL Script Sample

```dsl
load "input.jpg" as img1
resize img1 to 300 x 300 as resized
grayscale resized as gray
rotate gray by 90 as rotated
flip rotated horizontally as flipped
save flipped to "output.jpg" in "jpg"
```

## 🧠 How It Works

* `DslProcessor.java` handles parsing and processing the DSL scripts.
* `Imagescript.g4` defines the DSL grammar (parsed using ANTLR).
* ANTLR-generated files convert DSL into a parse tree.
* Operations are executed via handler callbacks to perform actions on images using Java AWT.


## 📝 Generated Files from ANTLR

* `ImagescriptLexer.java` – Lexer to tokenize input DSL
* `ImagescriptParser.java` – Parser to generate parse tree
* `ImagescriptBaseListener.java` – Base listener class
* `ImagescriptListener.java` – Custom listener interface
* Token and interpreter files (`.tokens`, `.interp`)

---

## 📌 Notes

* Branch was renamed to `main` using:

  ```bash
  git branch -m master main
  ```
* Project designed under **Problem-Based Learning (PBL)** model.

