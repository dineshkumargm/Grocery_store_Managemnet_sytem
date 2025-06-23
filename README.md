Grocery Store Management System
Overview
The Grocery Store Management System is a terminal-based Python application that allows users to manage a grocery store's inventory, shopping cart, and checkout process. It uses SQLite for persistent data storage and integrates Machine Learning Computer Vision (MLCV) with MobileNetV2 for recognizing grocery items from images. The project is structured using Object-Oriented Programming (OOP) principles for modularity and maintainability.
Features

Inventory Management: Add, remove, update, and display items in the inventory.
Cart Management: Add items to a cart, remove items, and display cart contents with total price.
Checkout: Process checkout and clear the cart.
Image Recognition: Add items to the inventory using MLCV to recognize items from images.
Persistent Storage: Store items in a SQLite database (grocery_store.db with items table).
User Interface: Simple terminal-based menu for interaction.

File Structure
GMS/
├── main.py                    # Entry point to run the application
├── models/
│   ├── item.py               # Item class definition
│   ├── inventory.py          # Inventory class for managing items
│   ├── cart.py               # Cart class for managing shopping cart
│   └── grocery_store.py      # GroceryStore class for application logic and UI
├── database/
│   ├── db_connection.py      # SQLite database connection management
│   └── db_manager.py         # Database CRUD operations
├── vision/
│   └── vision_recognizer.py  # MLCV logic for item recognition
├── images/                   # Directory for sample images (e.g., apple.jpg)
├── grocery_store.db          # SQLite database file (generated on first run)
└── myenv/                    # Virtual environment

Requirements

Python: Version 3.7–3.11 (TensorFlow compatibility).
Python Libraries:
opencv-python (image processing)
numpy (numerical operations)
tensorflow (MLCV with MobileNetV2)


SQLite: Included in Python’s standard library (no separate installation required).

Setup Instructions
1. Clone or Set Up the Project

Ensure the project directory (GMS) is set up with the above file structure.
If cloning from a repository, use:git clone <repository-url>
cd GMS



2. Create and Activate Virtual Environment

Create a virtual environment:python -m venv myenv


Activate the virtual environment:
Windows:.\myenv\Scripts\Activate.ps1


Linux/macOS:source myenv/bin/activate





3. Install Dependencies

Install required Python libraries:pip install opencv-python numpy tensorflow


Verify installation:pip list



4. Prepare Images for MLCV

Create the images/ directory if not already present:mkdir images


Add sample images (e.g., apple.jpg, banana.jpg) to the images/ directory for testing MLCV functionality.

5. Run the Application

Navigate to the project directory:cd C:\Users\spide\Desktop\GMS


Run the main script:python main.py


The application will:
Create grocery_store.db in the project root if it doesn’t exist.
Initialize the items table.
Display a menu for managing the store.



Usage
Upon running python main.py, the terminal displays a menu:
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


Option 1: Manually add an item (e.g., ID: 001, Name: Apple, Price: 1.50, Quantity: 10, Image Path: images/apple.jpg).
Option 2: Add an item using MLCV by providing an image path (requires images in images/).
Option 3: Remove an item by ID.
Option 4: Update an item’s name, price, or quantity.
Option 5: Display all inventory items.
Option 6: Add an item to the cart.
Option 7: Remove an item from the cart.
Option 8: Display cart contents with total price.
Option 9: Process checkout and clear the cart.
Option 10: Exit the application.

Database

File: grocery_store.db (SQLite database, created automatically).
Table: items
Columns:
item_id: TEXT (primary key)
name: TEXT (not null)
price: REAL (not null)
quantity: INTEGER (not null)
image_path: TEXT (optional)




Access: Use SQLite tools (e.g., sqlite3 command-line or VS Code SQLite extension) to inspect:sqlite3 grocery_store.db
.tables
SELECT * FROM items;



Troubleshooting

Dependency Issues:
Ensure Python 3.7–3.11 is used (TensorFlow compatibility):python --version


Reinstall dependencies if errors occur:pip install opencv-python numpy tensorflow




Database Errors:
If grocery_store.db is locked or corrupted, delete it and rerun the program.
Check write permissions in the project directory:icacls "C:\Users\spide\Desktop\GMS"




MLCV Errors:
Ensure images are in images/ and paths are correct (e.g., images/apple.jpg).
Verify TensorFlow installation if recognition fails.


NameError or ImportError:
Ensure all files (main.py, models/*.py, database/*.py, vision/*.py) are in place and contain correct imports.
Example: models/grocery_store.py should import Inventory and Cart.



Contributing
To contribute:

Fork the repository (if hosted).
Create a feature branch (git checkout -b feature/new-feature).
Commit changes (git commit -m "Add new feature").
Push to the branch (git push origin feature/new-feature).
Open a pull request.

License
This project is licensed under the MIT License (or specify your preferred license).
Acknowledgments

Built with Python, SQLite, OpenCV, NumPy, and TensorFlow.
MobileNetV2 for image recognition (pre-trained on ImageNet).
