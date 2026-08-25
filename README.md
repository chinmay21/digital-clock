# Digital Clock

A simple **digital clock desktop application** built with **Python and PyQt5**. The application displays the current system time in a digital-clock style interface and updates automatically every second.

## Features

* 🕒 Displays the current time in **HH:MM:SS AM/PM** format
* 🔄 Automatically updates every second
* 🖥️ Simple desktop GUI built with PyQt5
* 💚 Digital-style green text
* 🖤 Black background
* 🔤 Uses a custom digital clock font (`DS-DIGIT.TTF`)
* 📐 Centered time display

## Technologies Used

* **Python**
* **PyQt5**
* **QTimer** – Used to update the clock every second
* **QTime** – Used to retrieve the current system time
* **QFont / QFontDatabase** – Used to load and apply the custom digital font

## Project Structure

```text
digital-clock/
│
├── main.py
├── DS-DIGIT.TTF
└── README.md
```

> Make sure `DS-DIGIT.TTF` is in the correct location so that the application can load the custom font.

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/chinmay21/digital-clock.git
```

### 2. Navigate to the project directory

```bash
cd digital-clock
```

### 3. Install PyQt5

```bash
pip install PyQt5
```

### 4. Run the application

```bash
python main.py
```

## How It Works

The application uses PyQt5's `QTimer` to trigger the `update_time()` function every second.

The current system time is retrieved using:

```python
QTime.currentTime()
```

The time is then formatted as:

```text
HH:MM:SS AM/PM
```

and displayed inside a `QLabel`.

The custom `DS-DIGIT.TTF` font is loaded using `QFontDatabase` to give the clock its digital-display appearance.

## Main Components

### `QTimer`

A `QTimer` is responsible for periodically calling the `update_time()` method.

```python
self.timer.timeout.connect(self.update_time)
self.timer.start(1000)
```

`1000` milliseconds means the clock updates once every second.

### `QTime`

`QTime` retrieves the current system time:

```python
current_time = QTime.currentTime().toString("hh:mm:ss AP")
```

### Custom Font

The application loads the digital font using:

```python
font_id = QFontDatabase.addApplicationFont("DS-DIGIT.TTF")
```

This font is then applied to the clock label.

## Future Improvements

Possible improvements for this project include:

* Add 12-hour / 24-hour format switching
* Add date and day display
* Add customizable clock colors
* Add adjustable font sizes
* Add fullscreen mode
* Add multiple themes
* Add an alarm feature
* Add a settings menu
* Add system-tray support

## Author

**Chinmay Dhaundiyal**

GitHub:
https://github.com/chinmay21

## License

This project is open-source and available for learning and personal use.