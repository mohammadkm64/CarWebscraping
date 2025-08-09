# CarWebscraping
This repository is designed for a web scraping project focused on a car sales website.

**Features
**Collects title, model, price, year, mileage, and location for each listing.
*Stores data in a SQLite database.

*Downloads images for each car.

*Automatically organizes images into folders based on car model (e.g., car_images/206/).

*Uses Chrome Headless with Selenium for browsing.

*Prevents downloading duplicate images or exceeding the set limit per model.

🛠️ Requirements
Before running, make sure you have:

Python 3.8+

Google Chrome

ChromeDriver (matching your Chrome version)

Required Python packages:

pip install requests beautifulsoup4 selenium pillow

⚙️ Configuration
Inside the script, you can adjust the following variables:
BASE_URL = "https://divar.ir/s/iran/car"  # Search URL
IMAGE_DIR = "car_images"                  # Images directory
DB_NAME = "car_data.db"                    # Database name
MAX_IMAGES_PER_MODEL = 200                 # Image limit per model

The car models are defined here and can be edited or expanded:

CAR_MODELS = {
    "206": "206",
    "207": "207",
    "405": "405",
    "پراید": "Peride",
    ...
}

🚀 How to Run
After installing the dependencies, run:

python car_scraper.py

The script will:

Open and browse listing pages.

Extract metadata for each car.

Download images into the correct model folder.

Save all data into the SQLite database.

car_images/
├── 206/
│   ├── 1.jpg
│   ├── 2.jpg
├── Peride/
│   ├── 1.jpg
│   ├── 2.jpg
├── Unknown/
│   ├── 1.jpg
│   ├── 2.jpg
car_data.db

car_images/ → Main image folder.

car_data.db → Database containing all listings.

Notes
This project is for educational purposes only. Commercial use or violating the website’s terms is prohibited.

Delays between requests are included to avoid IP blocking.


