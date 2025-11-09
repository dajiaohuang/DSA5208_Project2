# DSA5208 Project 2: Apache Spark ML Model

---

## 📋 Team Members

| Name        | Student ID |
|-------------|------------|
| Sun Yueqi   | A0333495X  |
| Qiao Yichen | A0330197E  |
| Wu Shuwen   | A0330073U  |

---

## 📦 Deliverables

This submission folder contains the following files:

- **`README.md`**  
  This document provides step-by-step instructions on how to set up a Google Dataproc Cluster and run the Jupyter Notebook.

- **`dsa5208_proj2_notebook.ipynb`**  
  Jupyter Notebook containing the machine learning model pipeline implementation using Apache Spark.

- **`MLib_Spark.pdf`**  
  Comprehensive documentation covering data cleaning procedures, machine learning model details, hyperparameter tuning process, and experimental results.

---

## 🚀 Setup Instructions

### Step 1: Set Up Google Cloud Project

1. Log in to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project (e.g., `DSA5208`)
3. Enable the following APIs:
   - **Compute Engine API**
   - **Cloud Dataproc API**

### Step 2: Download and Extract Dataset

1. Download the 2024 dataset from NOAA:
   ```
   https://www.ncei.noaa.gov/data/global-hourly/archive/csv/2024.tar.gz
   ```

2. Extract the tar.gz file to a local folder:
   ```bash
   tar -xvzf 2024.tar.gz -C /path/to/destination/folder
   ```
   
   This will create a folder containing multiple CSV files.

### Step 3: Create GCS Bucket and Upload Data

1. **Create a Cloud Storage bucket:**
   - Navigate to Cloud Storage in the Google Cloud Console
   - Click "Create Bucket" and follow the prompts

2. **Install Google Cloud CLI:**
   - Download and install from: https://cloud.google.com/sdk/docs/install
   - Follow the installation instructions for your operating system

3. **Upload the dataset to GCS bucket:**
   ```bash
   gsutil -m cp -r /path/to/your/local/folder gs://your-bucket-name/
   ```
   
   > **Note:** The `-m` flag enables parallel uploads for faster transfer.

### Step 4: Create Dataproc Cluster and Run Notebook

1. **Create a Dataproc cluster:**
   - Go to Dataproc → Clusters → Create Cluster
   - Enable **Component Gateway**
   - Under "Optional components", select **Jupyter Notebook**
   - In cluster settings, specify the staging bucket created in Step 3

2. **Access JupyterLab:**
   - Once the cluster is running, navigate to the cluster details page
   - Click on "Web Interfaces" tab
   - Select **JupyterLab**

3. **Run the notebook:**
   - In JupyterLab, create a new **PySpark** notebook or upload the existing one
   - Upload `dsa5208_proj2_notebook.ipynb` to the cluster
   - Verify that the CSV folder path is correct before execution
   - Run all cells in the notebook

---

## ⚙️ Prerequisites

- Google Cloud Platform account with billing enabled
- Sufficient GCP quota for Dataproc cluster creation
- Basic familiarity with Jupyter Notebook and Apache Spark

---

## 📝 Notes

- Ensure your GCP project has sufficient permissions and quotas
- The dataset size is substantial; make sure you have adequate storage in your GCS bucket
- Cluster creation may take several minutes
- Remember to **delete the cluster** after use to avoid unnecessary charges

---

## 📧 Contact

For questions or issues, please contact any of the team members listed above.
