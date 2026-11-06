# Maritime Vessel Trajectory Prediction

## Project Overview
This project focuses on predicting future geographical positions of maritime vessels using AIS (Automatic Identification System) data and machine learning.

## Technologies Used
- Python 3.11
- Pandas and NumPy
- Scikit-learn
- PyTorch
- Jupyter Notebook
- Matplotlib

## Dataset
- Dataset: Danish AIS Data
- Date: 6 March 2025
- Original records: 24,168,735
- Unique vessels: 4,548
- Selected MMSI: 352001823

The original 4.13 GB dataset is not included in this repository.

## Data Preprocessing
- Data cleaning
- Timestamp consolidation
- Missing-value investigation
- GPS anomaly investigation
- Resampling to 10-second intervals
- Interpolation across eligible gaps
- Trajectory segmentation

## Feature Engineering
1. Latitude
2. Longitude
3. Speed Over Ground (SOG)
4. COG_sin
5. COG_cos

## Sequence Preparation
- Input window: 30 observations (5 minutes)
- Prediction horizon: 6 future positions (1 minute)
- Training sequences: 5,621
- Validation sequences: 1,196
- Testing sequences: 1,256

## Models Implemented
- Persistence baseline
- Constant-velocity baseline
- LSTM baseline

### LSTM Architecture
- Two LSTM layers
- Hidden size: 64
- Dropout: 0.2
- Optimizer: Adam
- Learning rate: 0.001
- Loss: Mean Squared Error

## Evaluation Results

Corrected constant-velocity baseline:

| Metric | Result |
|---|---:|
| ADE | 9.26 metres |
| Median Error | 3.53 metres |
| Maximum Error | 246.42 metres |

Evaluation used 2,199 original AIS future target points.

The LSTM baseline showed poor generalization due to geographic distribution shift.

## Current Progress
- Data preprocessing completed
- Feature engineering completed
- Sequence generation completed
- LSTM baseline trained
- Baseline evaluation completed
- Checkpoint recovery implemented

## Future Work
- Investigate vessel movement patterns
- Improve movement-related features
- Experiment with advanced prediction architectures
- Improve model generalization
- Visualize predicted trajectories
- Develop an interactive application

## Project Domain
Artificial Intelligence and Machine Learning



## Environment Setup

Follow these steps to set up the project on your local machine.

### 1. Clone the repository

```bash
git clone https://github.com/bhuvankv2912-alt/Maritime-Vessel-Trajectory-Prediction.git
cd Maritime-Vessel-Trajectory-Prediction
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

### 3. Activate the virtual environment

**Windows (PowerShell):**

```powershell
.\.venv\Scripts\Activate.ps1
```

### 4. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 5. Dataset

The original AIS dataset is not included in this repository because of its large file size.

Obtain the `aisdk-2025-03-06.csv` dataset separately and place it inside:

```text
data/
└── aisdk-2025-03-06.csv
```

### 6. Open the notebook

Open the project folder in VS Code, select the `.venv` Python interpreter, and run:

```text
notebooks/01_ais_exploration.ipynb
```

**Note:** The project was developed using Python 3.11.9. A compatible Python environment is recommended.