
# 🛒 Grocery Store Management System

## 📌 Overview

The **Grocery Store Management System** is a terminal-based Python application that enables management of a grocery store’s inventory, shopping cart, and checkout processes. It utilizes **SQLite** for persistent data storage and integrates **Machine Learning Computer Vision (MLCV)** using **MobileNetV2** to recognize grocery items from images.

This project follows **Object-Oriented Programming (OOP)** principles for clean, modular, and maintainable code.

---

## ✅ Features

- **Inventory Management**: Add, remove, update, and view items.
- **Cart Management**: Add to/remove from cart; view contents and total.
- **Checkout**: Finalize purchases and clear the cart.
- **Image Recognition**: Use MLCV to add items from images.
- **Persistent Storage**: Stores inventory in SQLite (`grocery_store.db`).
- **Simple UI**: Text-based menu-driven interface.

---

## 📁 File Structure

```
GMS/
├── main.py                    # Entry point to run the application
├── models/
│   ├── item.py               # Item class definition
│   ├── inventory.py          # Inventory class for managing items
│   ├── cart.py               # Cart class for shopping operations
│   └── grocery_store.py      # Main UI & controller logic
├── database/
│   ├── db_connection.py      # Handles DB connection
│   └── db_manager.py         # CRUD operations
├── vision/
│   └── vision_recognizer.py  # Image recognition with MobileNetV2
├── images/                   # Directory for sample images (e.g., apple.jpg)
├── grocery_store.db          # SQLite database file
└── myenv/                    # Virtual environment (recommended)
```

---

## 🛠️ Requirements

- **Python**: 3.7 – 3.11  
- **Libraries**:
  - `opencv-python` (image processing)
  - `numpy` (numerical operations)
  - `tensorflow` (MobileNetV2-based MLCV)
- **SQLite**: Included in Python Standard Library

---

## 🚀 Setup Instructions

### 1. Clone or Set Up the Project

```bash
git clone <repository-url>
cd GMS
```

### 2. Create and Activate Virtual Environment

```bash
# Create
python -m venv myenv

# Activate
# Windows:
.\myenv\Scripts\Activate.ps1

# Linux/macOS:
source myenv/bin/activate
```

### 3. Install Dependencies

```bash
pip install opencv-python numpy tensorflow
pip list  # Verify installation
```

### 4. Prepare Images for MLCV

```bash
mkdir images  # If not already present
# Add files like apple.jpg, banana.jpg etc.
```

### 5. Run the Application

```bash
cd path/to/GMS
python main.py
```

---

## 🧑‍💻 Usage

On running `main.py`, the terminal displays:

```
=== Grocery Store Management System ===
1. Add Item to Inventory (Manual)
2. Add Item to Inventory (Via Image)
3. Remove Item from Inventory
4. Update Item in Inventory
5. Display Inventory
6. Add Item to Cart
7. Remove Item from Cart
8. Display Cart
9. Checkout
10. Exit
```

### Example Options:

- **1**: Add manually (e.g., ID: 001, Name: Apple, Price: 1.50, Quantity: 10, Path: `images/apple.jpg`)
- **2**: Add via image recognition.
- **5**: View all inventory.
- **8**: View cart with total.
- **9**: Finalize purchase.

---

## 🗃️ Database

- **File**: `grocery_store.db`
- **Table**: `items`
- **Columns**:
  - `item_id` (TEXT, PK)
  - `name` (TEXT)
  - `price` (REAL)
  - `quantity` (INTEGER)
  - `image_path` (TEXT, optional)

### Access via SQLite CLI:

```bash
sqlite3 grocery_store.db
.tables
SELECT * FROM items;
```

---

## 🧩 Troubleshooting

### 📦 Dependency Errors

- Ensure Python 3.7–3.11 is installed:
  ```bash
  python --version
  pip install opencv-python numpy tensorflow
  ```

### 🗃️ DB Errors

- If `grocery_store.db` is corrupted or locked, delete and rerun.
- Check folder permissions:
  ```bash
  icacls "C:\Users\<your-user>\Desktop\GMS"
  ```

### 🖼️ Image Recognition Issues

- Make sure image paths are valid (e.g., `images/apple.jpg`).
- TensorFlow must be installed and functioning correctly.

### ⚠️ Import or Name Errors

- Verify all files are present and imports are valid.
- Example: `grocery_store.py` should import `Inventory` and `Cart` correctly.

---

## 🤝 Contributing

1. Fork the repository.
2. Create a branch:
   ```bash
   git checkout -b feature/new-feature
   ```
3. Commit changes:
   ```bash
   git commit -m "Add new feature"
   ```
4. Push and create a Pull Request.

---

## 📄 License

This project is licensed under the **MIT License**.

---

## 🙏 Acknowledgments

- Built with Python, SQLite, OpenCV, NumPy, and TensorFlow.
- Uses **MobileNetV2**, pre-trained on **ImageNet** for image classification.

---
