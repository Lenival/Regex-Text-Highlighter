# Regex Text Highlighter

This project is an interactive web application that allows users to input text and a regular expression (regex). The application highlights, in real-time, the portions of the text that match the provided regex. The matching portions are highlighted with a green background.

---

## **Key Features**

- **Dynamic Interface**: Changes in the text or regex are reflected immediately.
- **Real-Time Highlighting**: Matching portions of the text are automatically highlighted.
- **Error Handling**: Displays an error message if the regex is invalid.

---

## **Design Patterns Used**

### **1. MVC (Model-View-Controller)**
The application follows the **MVC** pattern, separating responsibilities as follows:
- **Model**: Manages data and business logic (class `Model`).
- **View**: Handles the user interface (class `View`).
- **Controller**: Coordinates interaction between the Model and the View (class `Controller`).

### **2. Object-Oriented Programming**
The code is implemented using an object-oriented approach, organizing responsibilities into modular classes:
- **Class `Model`**: Handles data (text and regex) and performs regex processing.
- **Class `View`**: Manages the graphical interface and captures user inputs.
- **Class `Controller`**: Acts as an intermediary between the Model and the View, ensuring synchronization between components.

### **3. Event-Driven Programming**
The application responds to user-generated events (typing in the text and regex fields). This is implemented using "event listeners" that call specific functions whenever a change occurs.

### **4. Single Responsibility Principle (SRP)**
Each class and method has a single, clear responsibility:
- The `Model` class handles only data and business logic.
- The `View` class manages only the user interface.
- The `Controller` class coordinates interaction between the Model and the View.

---

## **Business Logic**

The core logic resides in the `Model` class, specifically in the `getHighlightedText` method. This method:
1. Reads the text and regex provided by the user.
2. Uses the `replace()` function to find all matches of the regex in the text.
3. Replaces each match with itself wrapped in a `<span>` tag with the `highlight` class.
4. Returns the processed text to be displayed in the interface.

If the regex is invalid, the method returns an error message.

---

## **Execution Flow**

1. The user enters or edits text in the `<textarea>` field or the regex in the `<input>` field.
2. An `input` event is triggered, calling the `handleInput` method of the `Controller`.
3. The `Controller` updates the `Model` with the new text and regex values.
4. The `Model` processes the text and generates HTML with highlighted portions.
5. The `Controller` updates the `View` with the generated HTML, displaying the result in the interface.

---

## **How to Use**

1. Clone the repository:
   ```bash
   git clone https://github.com/Lenival/Regex-Text-Highlighter.git
   ```
2. Open the `index.html` file in any modern browser.
3. Enter text in the text field and a regex in the input field.
4. Observe the matching portions being highlighted in real-time.

---

## **Dependencies**

No external dependencies are required. The project uses only plain HTML, CSS, and JavaScript.

---

## **Contributions**

Contributions are welcome! If you find bugs or want to improve the project, feel free to open an issue or submit a pull request.

---

## **License**

This project is licensed under the [MIT License](LICENSE).
