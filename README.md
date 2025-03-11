# Cloud-Based Exoplanet Discovery

A cloud-based platform for analyzing exoplanet data using AI and machine learning, deployed as a web application on Google Cloud Platform.

## Project Overview

This project aims to build a scalable, cloud-based system that can:
1. Process light curve data from Kepler and TESS missions
2. Apply machine learning algorithms to detect exoplanet transit signals
3. Visualize results through an interactive web interface
4. Allow users to explore and analyze potential exoplanet candidates

## Architecture

- **Cloud Provider**: Google Cloud Platform (GCP)
- **Storage**: Google Cloud Storage
- **Compute**: Google AI Platform / Vertex AI
- **Deployment**: Google App Engine
- **ML Framework**: TensorFlow
- **Visualization**: Plotly, Dash

## Project Structure

```
exoplanet-discovery/
│
├── data/
│   ├── raw/                  # Raw Kepler and TESS datasets
│   └── processed/            # Processed datasets
│
├── notebooks/
│   ├── data_preprocessing.ipynb
│   ├── model_training.ipynb
│   └── visualization.ipynb
│
├── scripts/
│   ├── preprocess.py         # Data preprocessing script
│   ├── train.py              # Model training script
│   └── app.py                # Web app script
│
├── models/                   # Saved models
│
├── README.md                 # Project documentation
└── requirements.txt          # Python dependencies
```

## Project Phases

### Phase 1: Planning and Setup
- Define project scope (Kepler and TESS data)
- Set up GCP environment
- Configure cloud storage buckets
- Set up development environment

### Phase 2: Data Collection and Storage
- Download sample light curve data from NASA's Exoplanet Archive
- Preprocess data (clean, normalize, extract features)
- Upload processed data to GCP storage

### Phase 3: AI/ML Analysis
- Train ML models to identify exoplanet transit signals
- Evaluate model performance
- Generate candidate exoplanet list

### Phase 4: Visualization
- Create interactive visualizations of light curves
- Highlight detected transit events
- Develop dashboards for data exploration

### Phase 5: Deployment
- Build web application using Dash
- Deploy to Google App Engine
- Set up CI/CD pipeline

### Phase 6: Testing and Optimization
- Test application functionality
- Optimize cloud resource usage
- Implement cost monitoring

### Phase 7: Documentation and Sharing
- Document codebase
- Create user guides
- Share on GitHub

## Getting Started

### Prerequisites
- Google Cloud Platform account
- Python 3.8+
- Git

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/exoplanet-discovery.git
   cd exoplanet-discovery
   ```

2. **Set up Python environment**
   ```bash
   python -m venv exoplanet-env
   source exoplanet-env/bin/activate  # On Windows: exoplanet-env\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Configure GCP**
   ```bash
   gcloud auth login
   gcloud config set project exoplanet-discovery
   ```

4. **Download sample data**
   ```bash
   mkdir -p data/raw/kepler data/raw/tess
   # Download Kepler sample
   wget -P data/raw/kepler https://exoplanetarchive.ipac.caltech.edu/data/KeplerData/008/008120/008120608/kplr008120608-2009131110544_llc.fits
   # Download TESS sample
   wget -P data/raw/tess https://archive.stsci.edu/missions/tess/tid/s1/2018/270/1-1/tess2018270142941-s0001-0000000150428135-0120-s_lc.fits
   ```

5. **Upload to GCP**
   ```bash
   gsutil cp data/raw/kepler/* gs://exoplanet-data/raw/kepler/
   gsutil cp data/raw/tess/* gs://exoplanet-data/raw/tess/
   ```

## Data Sources

- [NASA Exoplanet Archive](https://exoplanetarchive.ipac.caltech.edu/)
- [Kepler Mission Data](https://archive.stsci.edu/kepler/)
- [TESS Mission Data](https://archive.stsci.edu/tess/)

## Machine Learning Approach

This project uses several techniques to detect exoplanet transits:
1. Feature engineering from light curves
2. Convolutional Neural Networks (CNNs) for pattern recognition
3. Time series analysis for periodic signal detection

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- NASA for providing open access to exoplanet data
- The astronomy community for research and tools
- Google Cloud Platform for infrastructure