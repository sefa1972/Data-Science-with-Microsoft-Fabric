# Data Science with Microsoft Fabric

This lab demonstrates a complete data science workflow in Microsoft Fabric, training machine learning models on diabetes data and comparing their performance.

## 📋 Lab Steps

1. **Create a Workspace**
   - Set up a new workspace in Fabric portal
   - Select Premium capacity

2. **Create Notebook**
   - Initialize a new notebook
   - Add markdown and code cells

3. **Ingest Data**
   ```python
   # Load diabetes dataset from Azure Open Datasets
   blob_account_name = "azureopendatastorage"
   blob_container_name = "mlsamples"
   blob_relative_path = "diabetes"
   df = spark.read.parquet(f"wasbs://{blob_container_name}@{blob_account_name}.blob.core.windows.net/{blob_relative_path}")

4. **Explore Data** 

Visualize with display(df)

Create box plot visualizations

5. **Prepare Data**

Convert Spark DataFrame to Pandas

Use Data Wrangler to create new column:

df['Risk'] = (df['Y'] > 211.5).astype(int)

6. **Train Machine Learning Models**

Regression Model (Linear Regression)

Classification Model (Logistic Regression)

Track experiments with MLflow

7. **Evaluate Experiments**

Compare regression and classification metrics

Analyze model performance

8. **Save Best Model**

Register top-performing model as ML Model

9. **Clean Up**

Save notebook

Terminate Spark session

Delete workspace
