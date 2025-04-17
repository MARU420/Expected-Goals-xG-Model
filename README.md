# ⚽ Expected Goals (xG) Model

This project builds a machine learning model to estimate the **probability of a goal** being scored from a given shot in football (soccer), known as **Expected Goals (xG)**. It uses real match data and key shot features to predict goal likelihood using logistic regression.

## 📊 Dataset

The dataset includes over 8,000 shots, with features like:

- **Shot coordinates** (`x`, `y`)
- **Game context** (`period`, `Zone`, `BigChance`, `Penalty`, etc.)
- **Shot type** (`Volley`, `Head`, `LeftFoot`, `RightFoot`)
- **Play context** (`SetPiece`, `FastBreak`, `ThrowinSetPiece`, etc.)
- **Target**: `is_goal` (boolean)

The dataset is available as `xg_model.csv`.

## 🧠 Model

A **logistic regression model** is trained to estimate the xG value for each shot.

### Metrics used:
- **Log Loss**
- **ROC AUC**
- **Brier Score**

### Visuals:
- Shot map plotting using [`mplsoccer`](https://mplsoccer.readthedocs.io/) for intuitive game analysis.

## 🚀 Usage

### 1. Install dependencies

```bash
pip install -r requirements.txt
```

Or install key packages manually:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn mplsoccer
```

### 2. Run the notebook

Open and run `cleaned_xg_model.ipynb` in Jupyter or VS Code. It walks through:

- Data cleaning
- Feature engineering
- Model training
- Performance evaluation
- Shot map plotting

### 3. Data preview

Sample rows from `xg_model.csv`:

| x   | y   | is_goal | Zone   | Volley | BigChance |
|-----|-----|---------|--------|--------|------------|
| 80.8 | 51.6 | False   | Center | 0      | 1          |
| 79.3 | 24.2 | False   | Center | 0      | 0          |

## 📈 Output

- Model predicts probability scores (`xG`) for each shot.
- Visual heatmaps and pitch plots show high xG zones and shot efficiency.

## 📂 File Structure

```
.
├── cleaned_xg_model.ipynb     # Jupyter notebook with full modeling workflow
├── xg_model.csv               # Dataset used for training and analysis
├── README.md                  # Documentation
└── requirements.txt           # Python dependencies (optional)
```

## 📜 License

MIT License.
