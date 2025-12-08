<div align="center">

<a href="https://www.lib.ncsu.edu/" aria-label="nc state university libraries logo"><img src="assets/lib_logo_whiteBG.svg" width="400" alt="NC State University Libraries Logo" /></a>

<h2>Data Science Services</h2>

<a href="https://www.lib.ncsu.edu/workshops"><img alt="NC State Libraries Workshops" src="https://img.shields.io/badge/NC%20State%20Libraries-Workshops-red"></a>
<a href="https://www.lib.ncsu.edu/staff/department/data-science-services"><img alt="Data Science Services" src="https://img.shields.io/badge/Data%20Science%20Services-Libraries-red"></a>
<a href="https://go.ncsu.edu/getdatahelp"><img alt="GetDataHelp" src="https://img.shields.io/badge/Get%20Data%20Help-go.ncsu.edu%2Fgetdatahelp-red"></a>
<a href="mailto:getdatahelp@ncsu.edu"><img alt="Email: getdatahelp@ncsu.edu" src="https://img.shields.io/badge/Email-getdatahelp%40ncsu.edu-red"></a>

<br/>

</div>

# AI-Powered Cell Microscopy Analysis & Cell Type Annotation

This project demonstrates AI and machine learning applications for biological image analysis and cell type identification. The repository includes two complementary workflows: automated cell microscopy analysis and gene expression-based cell type annotation.

## Project Overview

This project demonstrates:
1. **Automated image analysis** of cell microscopy data using computer vision
2. **Cell type annotation** from gene expression data using pattern matching

Both workflows automate cellular research tasks, reduce manual effort, and enable reproducible analysis.

---

## Slide Deck

The slide deck `AI Tools for Research - CMMTP.pdf` provides an introduction to the workshop and covers the concepts and techniques demonstrated in these notebooks.

---

## Notebooks

### Image Analysis Workflow
**Notebook:** `CMMTP_Image_Analysis.ipynb`

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/NCSU-Libraries/ai-cmmt/blob/main/CMMTP_Image_Analysis.ipynb)

#### What This Notebook Does

Demonstrates automated cell detection and quantitative analysis of microscopy images:
- Otsu's thresholding for cell identification
- Gaussian filtering for noise reduction
- Integrated density measurements for each cell
- Batch processing of image directories
- Statistical comparison of cell populations

#### Key AI/ML Techniques Used

- **Otsu's Thresholding**: Unsupervised algorithm for optimal binary segmentation
- **Gaussian Filtering**: Noise reduction via convolution operations
- **Pattern Recognition**: Automated cell boundary identification

#### Workflow Steps

1. Single image analysis with visualization
2. Batch processing of images from a zip archive
3. Statistical analysis with histograms and violin plots

#### Output

- `cell_analysis_results.csv`: Quantitative measurements for all processed images
- Visualizations comparing test vs. control cell populations

---

### Cell Type Annotation Workflow
**Notebook:** `CMMTP_cell_type.ipynb`

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/NCSU-Libraries/ai-cmmt/blob/main/CMMTP_cell_type.ipynb)

#### What This Notebook Does

Demonstrates automated cell type identification using gene expression patterns:
- Pattern matching against marker gene databases
- Confidence scoring for predictions
- Multi-cluster analysis
- Statistical filtering (p-value, log-fold change)

#### Key AI/ML Techniques Used

- **Pattern Matching**: Comparing cell clusters against known marker genes
- **Scoring Algorithm**: Quantifying prediction strength based on marker overlap
- **Statistical Filtering**: Using significance thresholds to identify relevant markers

#### Workflow Steps

1. Load marker database and differential expression data
2. Filter genes by statistical significance
3. Score clusters against marker patterns
4. Predict cell types with confidence scores

#### Output

- `annotated_clusters.csv`: Cell type predictions with evidence for each cluster

---

## Working Locally (not in Colab)

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

## Notes

- The example data files are included for demonstration purposes
- Results files (`cell_analysis_results.csv`, `annotated_clusters.csv`) are generated when running the notebooks
- Marker databases can be customized for specific research needs

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

NC State Libraries Data Science Services

---

