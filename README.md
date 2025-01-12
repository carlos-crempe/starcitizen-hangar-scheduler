
# Starcitizen Executive Hangar Status Tracker
![System Screenshot](/readme.jpeg?raw=true "Starcitizen Executive Hangar Status Tracker")

The **Hangar Status Tracker** is a lightweight web application for monitoring and managing the status of hangars. It uses visual indicators (semaphore-style LEDs) to display the current state of each hangar and provides tools for adding, editing, and removing entries. This project is entirely implemented in HTML, CSS, and JavaScript, and leverages browser `localStorage` to persist data.

---

## Features

### 1. Semaphore Display
- Each state is visually represented using a row of LEDs:
  - **Green LED**: Indicates a positive state.
  - **Red LED**: Indicates a negative state.
  - **Gray LED**: Indicates a neutral or inactive state.

### 2. Dynamic State Selector
- Users can select one of the predefined 11 states via an interactive dropdown.
- Each state is displayed visually in the selector for intuitive selection.

### 3. Data Management
- **Add Entries**: Enter a shard name and select its initial state.
- **Edit Entries**: Modify existing shard entries, including their name and state.
- **Remove Entries**: Delete entries that are no longer needed.

### 4. Status Calculation
- The system automatically calculates the current state of the hangar based on the time elapsed since the last update.
- Displays whether the hangar is open or closed, along with the time remaining until the next state change.
- **⚠ ATENTION**: For accurate predictions and functionality, ensure the system is updated virtually at the same time the hangar status changes. Delayed updates may result in incorrect state calculations or predictions.

### 5. Persistent Storage
- All shard data is stored in the browser using `localStorage`.
- Data remains available even after refreshing the page.

---

## How to Use

### Adding a Shard
1. Enter a shard name in the input field (optional).
2. Click the **"Select State"** button to open the state selector.
3. Choose a state from the dropdown.
4. The shard will appear in the table with its details.

### Editing a Shard
1. Click the **"Edit"** button next to the shard in the table.
2. Modify the state using the selector.

### Removing a Shard
- Click the **"Remove"** button next to the shard in the table.

---

## Technical Details

### Predefined States
The application supports 11 predefined states. Each state is defined as an array of integers:
- **1**: Green LED
- **-1**: Red LED
- **0**: Gray LED

| State | Pattern        | Duration (minutes) |
|-------|----------------|---------------------|
| 1     | `[0, 0, 0, 0, 0]` | 5                   |
| 2     | `[-1, -1, -1, -1, -1]` | 23                |
| 3     | `[-1, -1, -1, -1, 1]` | 23                |
| ...   | ...            | ...                 |
| 11    | `[0, 0, 0, 0, 1]` | 12                |

### Status Logic
- A hangar is **open** when it contains at least one green LED and no red LEDs.
- The status message indicates how long the hangar will remain in its current state.

---

## Project Structure
This project consists of a single HTML file with embedded CSS and JavaScript. All functionality, including state management, data persistence, and UI rendering, is self-contained.

---

## Installation
No installation is required. Simply open the `index.html` file in a browser to run the application.

---

## Roadmap
- **Enhanced Styling**: Add more visually appealing themes.
- **Optimize Layout**: Make it responsive/more mobile friendly
- **Enable Notification**: Enable user notification when a Hangar is close to open.

---

## License
This project is open-source and available under the [MIT License](https://opensource.org/licenses/MIT).
