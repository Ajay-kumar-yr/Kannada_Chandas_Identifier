Kannada Chandas Identifier (ಕನ್ನಡ ಛಂದಸ್ಸು)

An AI-powered tool to analyze and identify the meter (Chandas) of Kannada poems. It supports text input and image scanning (OCR) to detect popular meters like Kanda Padya, Shatpadi, and various Vruttas (Utpalamala, Champakamala, etc.).

(Replace with actual screenshot if available)

🚀 Features

Meter Identification: Detects complex meters based on Laghu/Guru patterns and Matra counts.

Supported: Kanda Padya, Shatpadi (Bhamini/Vardhaka), Utpalamala, Champakamala, Shardulavikridita, Mattebhavikridita, Sragdhara, Mahasragdhara.

OCR Support: Upload images of poems to automatically extract text and analyze the meter (Powered by Tesseract).

Multi-Stanza Analysis: Paste full poems; the tool separates and analyzes each stanza individually.

Auto-Save History: Valid identifications are automatically saved to a local database (chandas.db) for future reference.

PDF Export: Download a beautifully formatted report of the analysis.

Visual Scansion: View the line-by-line breakdown of Laghu (U) and Guru (-) markers.

🛠️ Installation

Prerequisites

Python 3.x installed on your system.

Tesseract OCR engine installed.

Step 1: Install Tesseract OCR

This project relies on Tesseract for reading images.

Windows: Download the installer from UB-Mannheim/tesseract.

Important: During installation, select "Kannada" under "Additional Script Data" or "Additional Languages".

Note your installation path (e.g., D:\tessaract\tesseract.exe).

Linux: sudo apt install tesseract-ocr tesseract-ocr-kan

Mac: brew install tesseract-lang

Step 2: Clone & Install Dependencies

Clone this repository or download the files.

Open a terminal in the project folder.

Install the required Python libraries:

pip install flask flask-cors pytesseract pillow


Step 3: Configure Tesseract Path (Windows Only)

If you installed Tesseract in a custom location (like D:\tessaract), open app.py and ensure the path matches:

# Inside app.py
pytesseract.pytesseract.tesseract_cmd = r"D:\tessaract\tesseract.exe"


▶️ Running the Application

1. Start the Backend

Run the Flask server:

python app.py


You should see: SUCCESS! Server is running on http://127.0.0.1:5000

2. Open the Frontend

Option A (Recommended): Open your browser and go to http://127.0.0.1:5000. The Python server serves the HTML file directly.

Option B (VS Code Live Server): You can also open index.html using Live Server (port 5500). The frontend is configured to talk to the backend on port 5000 automatically.

📖 Usage Guide

Analyze Text: Type or paste a Kannada poem into the text box and click Analyze.

Scan Image: Click the Scan Image button to upload a picture (.png, .jpg) of a poem. The text will be extracted and placed in the box.

View History: Click the History button in the top-right to see previously analyzed poems. Click any item to reload it.

Download Report: Once analyzed, click the PDF button to save the results.

📂 Project Structure

app.py: The main Flask backend. Handles logic, DB connections, and OCR.

index.html: The frontend user interface (HTML/Tailwind CSS/JS).

chandas.db: SQLite database (auto-created) storing your history.

logo.png / favicon.png: Icons for the UI.

❓ Troubleshooting

"OCR Error: tesseract is not installed...":

Ensure Tesseract is installed.

Check that the path in app.py (pytesseract.pytesseract.tesseract_cmd) exactly matches your installation location.

"Connection Failed":

Ensure the Python terminal is open and app.py is running.

Check if the server is running on port 5000.

Made with ❤️ for Kannada Literature
