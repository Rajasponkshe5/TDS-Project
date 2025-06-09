# IITM BS Degree: TDS Virtual TA Project

## Project Overview

This project aims to build a virtual Teaching Assistant (TA) for the "Tools in Data Science" (TDS) course offered by IIT Madras' Online Degree in Data Science. The goal is to create an API that can automatically answer student questions based on official course content and discussions from the TDS Discourse forum.

## Background

As a student enrolled in the "Tools in Data Science" course, I've decided to develop this automated TA to assist my fellow students and teaching assistants by providing quick, accurate responses to common queries.

## Data Sources

The virtual TA will leverage information from two primary sources:

1.  **Course Content:** Content for TDS Jan 2025 as on 15 Apr 2025.
    * **URL:** `https://tds.s-anand.net/`
2.  **TDS Discourse Posts:** Content from 1 Jan 2025 - 14 Apr 2025 from the official TDS Discourse Knowledge Base.
    * **URL:** `https://discourse.onlinedegree.iitm.ac.in/c/courses/tds-kb/34`

## Project Structure

This repository will be organized as follows:

* `data/`: Stores raw and processed data.
    * `data/raw/`: Contains the directly scraped content (e.g., `course_content.txt`, `discourse_posts.json`).
    * `data/processed/`: Will contain cleaned, preprocessed, and potentially indexed data ready for the QA model.
* `src/`: Contains the Python scripts for different functionalities.
    * `src/scrape_course_content.py`: Script to scrape data from `https://tds.s-anand.net/`.
    * `src/scrape_discourse_posts.py`: Script to scrape data from the Discourse forum API.
    * `src/processing.py`: Scripts for cleaning and preprocessing the scraped data.
    * `src/api.py`: The FastAPI/Flask application that will serve the virtual TA.
    * `src/qa_model.py`: (Optional) Core logic for the Question Answering model.
* `notebooks/`: (Optional) Jupyter notebooks for exploration, testing, and model development.
* `requirements.txt`: Lists all Python dependencies required to run the project.
* `.gitignore`: Specifies files and directories that Git should ignore.
* `README.md`: This file, providing an overview of the project.
* `LICENSE`: The license under which the project is released.

## Getting Started (Local Setup)

To set up and run this project locally:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Rajasponskhe5/TDS-Project.git](https://github.com/Rajasponskhe5/TDS-Project.git)
    cd TDS-Project
    ```
2.  **Create and activate a virtual environment:**
    ```bash
    python -m venv venv
    # On Windows:
    .\venv\Scripts\activate
    # On macOS/Linux:
    source venv/bin/activate
    ```
3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
4.  **Scrape the data:**
    * **For Discourse:** Obtain your Discourse API key and username from the IITM Online Degree Discourse forum. Set them as environment variables:
        ```bash
        # On Windows:
        set DISCOURSE_API_KEY="YOUR_API_KEY"
        set DISCOURSE_API_USERNAME="YOUR_USERNAME"
        # On macOS/Linux:
        export DISCOURSE_API_KEY="YOUR_API_KEY"
        export DISCOURSE_API_USERNAME="YOUR_USERNAME"
        ```
    * Run the scraping scripts:
        ```bash
        python src/scrape_course_content.py
        python src/scrape_discourse_posts.py
        ```
    * The raw data will be saved in the `data/raw/` directory.

## Next Steps

* Implement data cleaning and preprocessing in `src/processing.py`.
* Develop the core Question Answering logic.
* Build the FastAPI/Flask API.
* Deploy the API.

## Contributing

Feel free to fork this repository, open issues, or submit pull requests.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---
**Note:** This project is for academic purposes as part of the IITM Online Degree in Data Science.
