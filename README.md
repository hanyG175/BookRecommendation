# Book Recommendation System

This project is a Python-based expert system that recommends books based on user preferences (genre, author, rating, and publication year). It uses a knowledge base with logical inference (from the AIMA library), integrates with the Google Books API for real-time book data, and displays recommendations in a `Tkinter` GUI.

## Features
- Knowledge base with facts about books (title, genre, author, rating, year).
- Logical rules for recommending books based on user preferences and reading history.
- Interactive GUI with filters for author, genres, minimum rating, and year.
- Displays book cards with cover images, titles, authors, ratings, genres, and descriptions fetched from the Google Books API.
- Scrollable interface for browsing multiple recommendations.

## Prerequisites
To run this project, you’ll need:
- **Python 3.x** (tested with Python 3.9+)
- **Required Libraries**:
  - `requests` (install with `pip install requests`)
  - `Pillow` (install with `pip install Pillow`)
  - `tkinter` (usually included with Python; if not, install via `sudo apt-get install python3-tk` on Linux)
- **AIMA Library**: Requires the AIMA Python library (`aima1`) from the specified path or a compatible version.
- **Google Books API Access**: Ensure the `GoogleBooksApiCall.py` module is functional (API key may be required).
- **Windows-specific**: Uses `ctypes` for high DPI support, optimized for Windows but adaptable.

## Installation
1. Clone or download this repository:
   `git clone <repository-url>`
   `cd <repository-folder>`
2. Install the required dependencies:
   `pip install requests Pillow`
3. Ensure `tkinter` is available. On Linux, you may need:
   `sudo apt-get install python3-tk`
4. Place the AIMA library in the correct path (e.g., `C:\Users\LENOVO\Code\AI\ES_Project\Logic\aima1`) or adjust `sys.path` in the code to match your setup.
5. Ensure `GoogleBooksApiCall.py` is in the `Logic` directory and properly configured for API calls.

## Usage
1. Run the interface script:
   `python interface.py`
2. Steps:
   - Enter an author name (optional) in the search bar.
   - Select preferred genres from the checkboxes.
   - Adjust the minimum rating slider (0–5).
   - Choose a publication year from the dropdown (1900–2024).
   - Click "Load Inference Results" to generate recommendations.
   - Scroll through the book cards displaying title, author, rating, genres, publication date, and description.

## Project Structure
- **`Logic.py`**: Contains the knowledge base, facts, rules, and inference logic.
  - **Facts**: Predefined book data (e.g., "Hamlet", "Dune").
  - **Rules**: Logical implications for recommendations.
  - **Inference**: Uses forward and backward chaining to suggest books.
- **`interface.py`**: GUI implementation with `Tkinter`.
  - **UI Setup**: Frames, widgets, and book card display.
  - **API Integration**: Fetches book details from Google Books API.
- **`GoogleBooksApiCall.py`**: External module (not included here) for API interactions.

## Customization
- **Book Data**: Add or modify books in `facts` list in `Logic.py`.
- **Rules**: Extend `rules` list for additional recommendation logic (e.g., based on series or publisher).
- **Genres**: Update `self.genres` in `interface.py` to include different categories.
- **UI Layout**: Adjust `geometry`, columns, or card styles in `interface.py`.

## Example Output
- **GUI**: A window (1920x1080) with a top panel for filters and a scrollable bottom panel showing book cards.
- **Book Card**: Displays a thumbnail (if available), title, author(s), rating, genres, publication year, and truncated description.

## Limitations
- Hardcoded paths in `sys.path` (e.g., `C:\Users\LENOVO\Code\AI\ES_Project`) must match your local setup.
- Requires internet for Google Books API calls; offline mode relies solely on predefined `facts`.
- Rating filter simplifies to "High" (≥4.0) or "Low" (<4.0); no granular control.
- Year filter fetches all books from the selected year onward unless refined.

## Contributing
Submit issues or pull requests to enhance the knowledge base, improve inference, or refine the UI!

## License
This project is open-source under the [MIT License](LICENSE).
