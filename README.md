
# BigDataInsights_CrimeTrends_in_India

## Project Overview
**BigDataInsights_CrimeTrends_in_India** is a comprehensive big data analysis project focused on understanding crime trends in India. This project leverages **Amazon S3** for large-scale data storage, **Databricks** for scalable data processing and analytics, and **Apache Spark** within Databricks for efficient handling of the dataset. The main goal is to analyze the crime data from various Indian districts over multiple years to extract meaningful insights and trends.

## How Amazon S3 Is Utilized
Amazon S3 serves as the primary data storage solution in this project, offering several key advantages:
- **Scalability**: As the dataset is large and may grow in size, Amazon S3 provides unlimited storage capacity. This makes it an ideal choice for storing and retrieving large volumes of data seamlessly.
- **Accessibility**: S3’s cloud-based architecture allows easy integration with platforms like Databricks. The dataset is stored in a publicly accessible bucket, so it can be directly used in your Databricks notebooks without requiring local storage.
- **Cost-Effectiveness**: By hosting the dataset in S3, the need for maintaining physical storage infrastructure is eliminated. This reduces cost, especially when working with large datasets in big data analysis projects.
- **Reliability**: Amazon S3 ensures high availability and durability of the data. This guarantees that the dataset is securely stored and can be accessed at any time for analysis.

### Hosted Bucket Information
I have hosted the dataset in an Amazon S3 bucket named **bigdataprojectty**, which can be accessed publicly for the purpose of this project. The entire Jupyter notebook (`.ipynb`) file, as well as other data processing scripts, are designed to utilize this S3 bucket directly.

### Using S3 in Databricks
To access the dataset stored in S3 from your Databricks environment, you can use the following code to load the data directly:

```python
# Loading the dataset from the public S3 bucket
crimes_df = spark.read.csv("s3a://bigdataprojectty/crime_dataset/", header=True, inferSchema=True)

# Perform further operations on crimes_df
crimes_df.show()
```

## Workflow
1. **Data Storage in Amazon S3**:  
   The dataset is stored in the **bigdataprojectty** S3 bucket. This ensures that the data is accessible from anywhere, enabling smooth interaction with the Databricks platform for processing.

2. **Data Processing in Databricks**:  
   The data stored in the S3 bucket is accessed and processed within **Databricks**. Databricks, built on top of **Apache Spark**, enables large-scale data processing and analytics tasks.

3. **Evaluation using Apache Spark**:  
   **Apache Spark** is utilized to process and evaluate the dataset. This distributed computing framework allows for efficient handling of large-scale data, including aggregations, transformations, and predictive modeling.


## Dataset
The dataset contains records of various crimes across districts in India, covering the years from 2001 to 2012. It includes detailed statistics on different crime types, including murder, theft, dacoity, crimes against children, etc. Given the dataset's size, it’s hosted on **Amazon S3** for easier access and efficient processing.

Alternatively, the **.zip** file is available in this repository if you prefer to download it locally.

## Key Technologies
- **Amazon S3**: Used as a scalable cloud storage solution to host the dataset.
- **Databricks**: Utilized for scalable data processing, built on **Apache Spark**.
- **Apache Spark**: Responsible for distributed data processing and efficient analysis of the large dataset.

## Installation and Setup

### Prerequisites
- **Databricks account**: You will need access to Databricks to run the Spark jobs and analyze the dataset.
- **Amazon S3 access**: The dataset is hosted publicly in the **bigdataprojectty** S3 bucket. Ensure your Databricks environment is configured to access S3.

### Steps
1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/BigDataInsights_CrimeTrends_in_India.git
   ```
   
2. **Databricks Setup**
   - Load the dataset from the S3 bucket using the URL: `s3://bigdataprojectty/crime_dataset/`.
   - Set up a **Databricks Cluster** with **Apache Spark** enabled.
   - Import the **Jupyter notebooks** from this repository into Databricks.

3. **Amazon S3 Integration**
   - Ensure your Databricks environment has the correct permissions to access the publicly hosted **bigdataprojectty** S3 bucket.

4. **Running the Analysis**
   - Use the notebooks in Databricks to load, transform, and analyze the dataset. The analysis will generate crime trends and visualizations, which can be viewed in the Flask app.

## Visualizations
This project includes visualizations such as:
- Crime trends by year (total crimes per year).
- Breakdown of crime types by district and year.
- Insights into specific crime categories like crimes against children etc.
  
These visualizations help identify trends and patterns in criminal activities across different regions of India.

## Future Work
- Expand the dataset beyond 2012 by incorporating additional sources.
- Implement machine learning models to predict future crime trends.
- Create interactive dashboards using Flask for real-time crime analysis.

