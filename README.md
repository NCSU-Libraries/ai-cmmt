<div align="center">

<a href="https://www.lib.ncsu.edu/" aria-label="nc state university libraries logo"><img src="assets/lib_logo_whiteBG.svg" width="400" alt="NC State University Libraries Logo" /></a>

<h2>NC State University Libraries Python Workshops</h2>

<a href="https://www.lib.ncsu.edu/workshops"><img alt="NC State Libraries Workshops" src="https://img.shields.io/badge/NC%20State%20Libraries-Workshops-red"></a>
<a href="https://www.lib.ncsu.edu/staff/department/data-science-services"><img alt="Data Science Services" src="https://img.shields.io/badge/Data%20Science%20Services-Libraries-red"></a>
<a href="https://go.ncsu.edu/getdatahelp"><img alt="GetDataHelp" src="https://img.shields.io/badge/Get%20Data%20Help-go.ncsu.edu%2Fgetdatahelp-red"></a>
<a href="mailto:getdatahelp@ncsu.edu"><img alt="Email: getdatahelp@ncsu.edu" src="https://img.shields.io/badge/Email-getdatahelp%40ncsu.edu-red"></a>

<br/>

</div>

# AI-Powered Cell Microscopy Analysis & Cell Type Annotation

This repository demonstrates the application of **artificial intelligence and machine learning techniques** for biological image analysis and cell type identification. The project showcases two complementary workflows that leverage AI/ML methods to automate and enhance cellular research.

## 🎯 Project Overview

This project demonstrates how AI can be used to:
1. **Automate image analysis** of cell microscopy data using computer vision techniques
2. **Annotate cell types** from gene expression data using pattern matching and scoring algorithms

Both workflows showcase practical applications of AI in biological research, reducing manual labor and enabling reproducible, quantitative analysis.

---

## 📓 Notebooks

### 1. Image Analysis Workflow
**Notebook:** `CMMTP_Image_Analysis.ipynb`

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/NCSU-Libraries/ai-cmmt/blob/main/CMMTP_Image_Analysis.ipynb)

#### What This Notebook Does

This notebook demonstrates **AI-powered image segmentation and quantitative analysis** of cell microscopy images. It uses computer vision algorithms to:

- **Automated Cell Detection**: Uses Otsu's thresholding algorithm (an unsupervised machine learning method) to automatically identify cells in microscopy images
- **Noise Reduction**: Applies Gaussian filtering to denoise images before analysis
- **Quantitative Measurements**: Calculates integrated density (total fluorescence intensity) for each detected cell
- **Batch Processing**: Automatically processes entire directories of images, demonstrating scalability
- **Statistical Comparison**: Compares test cells vs. control cells using distribution analysis and visualization

#### Key AI/ML Techniques Used

1. **Otsu's Thresholding**: An unsupervised learning algorithm that automatically determines the optimal threshold for binary segmentation
2. **Gaussian Filtering**: Image preprocessing using convolution operations to reduce noise
3. **Pattern Recognition**: Automated identification of cell boundaries without manual annotation

#### Workflow Steps

1. **Single Image Analysis**: Demonstrates the analysis pipeline on one example image
2. **Visualization**: Shows original image, segmentation mask, and overlay
3. **Batch Processing**: Processes all images in a zip archive
4. **Statistical Analysis**: Generates histograms and violin plots comparing cell populations

#### Output

- `cell_analysis_results.csv`: Quantitative measurements for all processed images
- Visualizations comparing test vs. control cell populations

---

### 2. Cell Type Annotation Workflow
**Notebook:** `CMMTP_cell_type.ipynb`

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/NCSU-Libraries/ai-cmmt/blob/main/CMMTP_cell_type.ipynb)

#### What This Notebook Does

This notebook demonstrates **AI-driven cell type identification** using gene expression marker patterns. It uses pattern matching and scoring algorithms to:

- **Automated Cell Type Prediction**: Matches cluster-specific genes against a curated marker database
- **Pattern Recognition**: Identifies cell types based on characteristic marker gene expression
- **Multi-Cluster Analysis**: Processes multiple cell clusters simultaneously
- **Evidence-Based Scoring**: Provides confidence scores and evidence for each prediction

#### Key AI/ML Techniques Used

1. **Pattern Matching**: Compares unknown cell clusters against known marker gene patterns
2. **Scoring Algorithm**: Quantifies the strength of cell type predictions based on marker overlap
3. **Data Filtering**: Uses statistical thresholds (p-value, log-fold change) to identify significant markers

#### Workflow Steps

1. **Marker Database**: Defines known cell type markers (T-cells, B-cells, Macrophages, etc.)
2. **Data Loading**: Reads differential gene expression data from Excel files
3. **Statistical Filtering**: Filters genes by significance (p-value < 0.05) and fold-change
4. **Pattern Matching**: Scores each cluster against marker database
5. **Annotation**: Predicts most likely cell type for each cluster

#### Output

- `annotated_clusters.csv`: Cell type predictions with evidence for each cluster

---

## 📚 Workshop Materials

The slide deck `AI Tools for Research - CMMTP.pdf` provides an introduction to the workshop and covers the concepts and techniques demonstrated in these notebooks.

## 🚀 Getting Started

### Prerequisites

- Python 3.9 or higher
- Jupyter Notebook or JupyterLab
- Required Python packages (see `pyproject.toml`)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/NCSU-Libraries/ai-cmmt.git
   cd ai-cmmt
   ```

2. **Install dependencies using uv (recommended):**
   ```bash
   uv sync
   ```

   Or using pip:
   ```bash
   pip install jupyter matplotlib numpy openpyxl pandas scikit-image seaborn
   ```

3. **Launch Jupyter:**
   ```bash
   jupyter notebook
   ```

### Running the Notebooks

1. **For Image Analysis:**
   - Open `CMMTP_Image_Analysis.ipynb`
   - Ensure `CMMTP_example_images.zip` is in the same directory
   - Run cells sequentially

2. **For Cell Type Annotation:**
   - Open `CMMTP_cell_type.ipynb`
   - Ensure `rank_genes_groups_by_cluster_JP.xlsx` is in the same directory
   - Run all cells

---

## 📁 Project Structure

```
ai-cmmt/
├── CMMTP_Image_Analysis.ipynb          # Image analysis workflow
├── CMMTP_cell_type.ipynb               # Cell type annotation workflow
├── CMMTP_example_images.zip            # Example microscopy images
├── rank_genes_groups_by_cluster_JP.xlsx # Gene expression data
├── Result of Result of SUM_CL586_1.nd2 - CL586_1.nd2 (series 01) - C=0.tif  # Example image
├── AI Tools for Research - CMMTP.pdf   # Workshop slide deck
├── pyproject.toml                       # Project dependencies
├── uv.lock                              # Dependency lock file
└── README.md                            # This file
```

---

## 🤖 AI/ML Demonstration Highlights

This project demonstrates several key aspects of AI in biological research:

### 1. **Automation**
   - Eliminates manual cell counting and annotation
   - Processes hundreds of images automatically
   - Reduces human error and bias

### 2. **Reproducibility**
   - Standardized analysis pipelines
   - Consistent parameter settings
   - Version-controlled code

### 3. **Quantitative Analysis**
   - Objective measurements (integrated density, marker scores)
   - Statistical comparisons between groups
   - Data-driven decision making

### 4. **Scalability**
   - Batch processing capabilities
   - Handles large datasets efficiently
   - Extensible to new cell types and markers

### 5. **Pattern Recognition**
   - Identifies complex patterns in image data
   - Matches gene expression signatures
   - Learns from curated marker databases

---

## 📊 Example Results

### Image Analysis
- **Input**: Microscopy images of cells (TIFF format)
- **Output**: Quantitative measurements of fluorescence intensity
- **Comparison**: Statistical distributions of test vs. control cells

### Cell Type Annotation
- **Input**: Differential gene expression data (Excel format)
- **Output**: Predicted cell types with confidence scores
- **Evidence**: List of matching marker genes

---

## 🔬 Scientific Context

This workflow is designed for:
- **Cell Biology Research**: Quantitative analysis of cell microscopy data
- **Immunology**: Identification of immune cell types from gene expression
- **Biomedical Research**: Comparison of experimental conditions (test vs. control)

---

## 📝 Notes

- The example data files are included for demonstration purposes
- Results files (`cell_analysis_results.csv`, `annotated_clusters.csv`) are generated when running the notebooks
- Marker databases can be customized for specific research needs

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

NC State Libraries Data Science Services

---

## 🔗 Quick Links

- [Open Image Analysis in Colab](https://colab.research.google.com/github/NCSU-Libraries/ai-cmmt/blob/main/CMMTP_Image_Analysis.ipynb)
- [Open Cell Type Annotation in Colab](https://colab.research.google.com/github/NCSU-Libraries/ai-cmmt/blob/main/CMMTP_cell_type.ipynb)


