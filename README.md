# TMDB Interactive Movie EDA 🎬📊

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)  
[![Python Version](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)  
[![TMDB API](https://img.shields.io/badge/TMDB-API-yellow.svg)](https://www.themoviedb.org/documentation/api)

---

## 📖 Project Overview
Interactive Exploratory Data Analysis (EDA) of movies using The Movie Database (TMDB) API. Fetch real-world data on box office, ratings, and more, then explore trends with dynamic, interactive charts directly in a Jupyter Notebook.

---

## 📋 Table of Contents
- [Features](#-features)
- [Technologies](#-technologies)
- [Requirements](#-requirements)
- [Installation](#-installation)
- [TMDB API Setup](#-tmdb-api-setup)
- [Usage](#-usage)
- [Demo](#-demo)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## ✨ Features
- 📊 **Interactive Visualizations:** Scatter plots, bar charts, and line graphs with hover details.
- 🔎 **Dynamic Filters:** Filter by year, genre, popularity, and more using `ipywidgets` controls.
- 📈 **Data Insights:** Analyze box office trends, rating distributions, and popularity metrics.
- 🔄 **Automated Data Pipeline:** Fetch, clean, and preprocess data from TMDB with `pandas` and `requests`.

> *Why include an API section?*  
> Highlighting API integration shows practical skills in real-world data retrieval and backend communication—qualities recruiters value for data-centric roles.

---

## 🛠 Technologies
- **Language:** Python 3.8+
- **Notebook Environment:** Jupyter Notebook
- **Libraries:**
  - `pandas` for data manipulation
  - `requests` for API calls
  - `plotly-express` for interactive charts
  - `ipywidgets` for user controls

---

## 📦 Requirements
- Python 3.8 or higher
- TMDB account and API key
- `pip` package manager

---

## 🚀 Installation
```bash
# Clone this repository
git clone https://github.com/viniciusrodriguesai/TMDB-Interactive-Movie-EDA.git
cd TMDB-Interactive-Movie-EDA

# (Optional) Create and activate a virtual environment
python -m venv venv
# Linux/macOS
source venv/bin/activate
# Windows
venv\\Scripts\\activate

# Install dependencies
pip install -r requirements.txt
````

---

## 🔑 TMDB API Setup

1. Sign up for a free account at [TMDB](https://www.themoviedb.org/).
2. Generate an API key under **Settings → API**.
3. Add your API key to the notebook or a `.env` file:

```python
import os
os.environ['TMDB_API_KEY'] = 'YOUR_API_KEY_HERE'
```

> **Note:** Including an API setup section demonstrates your ability to work with external services and configure environments, which recruiters often look for.

---

## 🎓 Usage

1. Launch the Jupyter Notebook:

   ```bash
   jupyter notebook Notebooks/TMDB_EDA.ipynb
   ```
2. Run all cells in sequence to:

   * Download and preprocess data
   * Generate interactive visualizations
   * Use widgets for custom filtering

---

## 📸 Demo

> Example: Action Movies Released in 2020
The screenshot previously referenced here is not tracked. Run the notebook locally to inspect the interactive charts.

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repo
2. Create a new branch: `git checkout -b feature-name`
3. Commit your changes: `git commit -m 'Add new feature'`
4. Push to your branch: `git push origin feature-name`
5. Open a Pull Request

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 📬 Contact

Vinícius Mangueira – [GitHub](https://github.com/Vinicius-Mangueira) – [LinkedIn](https://www.linkedin.com/in/vinicius-mangueira-0b8285224/) – [viniciusmangueira04@gmail.com](mailto:viniciusmangueira04@gmail.com)

## Portfolio validation

The processed CSV stores genres as text representations of lists. The financial summary now safely decodes these lists before exploding them: 509 movies produce 1,408 movie/genre rows, rather than treating each genre combination as one category. Financial totals across genres overlap because a movie may belong to multiple genres.

The rating regression is compared with a training-mean baseline on the same fixed 80/20 split. Recomputed on the tracked CSV: model MSE 2.467321, baseline MSE 2.630154. This modest reduction on one split does not establish generalization; the popular-movie snapshot is a selected sample.

Only the genre-summary and regression cells were rerun during this check. Their old saved outputs were cleared after editing; the full live-API workflow and interactive widgets were not rerun.

Large embedded Plotly JavaScript outputs in the summary-chart cell were removed; the connected renderer avoids repeatedly bundling the library. The notebook decreased from about 14.5 MB to about 0.10 MB. The charts use a network connection for Plotly's browser library and should be rendered again locally.
