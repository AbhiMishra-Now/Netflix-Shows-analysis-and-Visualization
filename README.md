# 🍿 Netflix Data Analysis with AWS QuickSight 📊

This project provides a comprehensive analysis of the Netflix movies and TV shows dataset. Using **Amazon S3** for data storage and **AWS QuickSight** for visualization, I've created an interactive dashboard to uncover trends and insights from the Netflix library. 📈

## 🏛️ Project Architecture

The architecture for this project is simple, scalable, and leverages key AWS analytics services. 🏗️

1.  **Data Storage** 🗄️: The `netflix_titles.csv` dataset is stored in an **Amazon S3 bucket**.
2.  **Data Manifest** 📄: A `manifest.json` file is used to define the location and format of the dataset in S3, allowing QuickSight to discover and connect to it.
3.  **Data Visualization** 🎨: **Amazon QuickSight** connects to the S3 data source, ingesting the data to build the interactive visualizations and dashboards.

-----

## 🚀 How to Recreate This Project

You can replicate this analysis by following these steps.

### ✅ Prerequisites
<img width="1123" height="327" alt="architecture-diagram" src="https://github.com/user-attachments/assets/3c4efdfb-f2a0-4af9-9795-c9b82ee1e472" />

  * An AWS Account ☁️
  * The `netflix_titles.csv` file from this repository 📁

### Step 1: Store the Dataset in S3

1.  Create a new **S3 bucket** in your AWS account. 🪣
2.  Upload the `netflix_titles.csv` file to the root of your new bucket. 📤

### Step 2: Create and Upload the Manifest File

1.  Create a new local file named `manifest.json`. 📝

2.  Copy and paste the following JSON into the file. **Remember to replace `your-bucket-name` with the actual name of your S3 bucket.**

    ```json
    {
        "fileLocations": [
            {
                "URIs": [
                    "s3://your-bucket-name/netflix_titles.csv"
                ]
            }
        ],
        "globalUploadSettings": {
            "format": "CSV",
            "delimiter": ",",
            "textqualifier": "\"",
            "containsHeader": "true"
        }
    }
    ```

3.  Upload this `manifest.json` file to the same S3 bucket. 📤

### Step 3: Connect QuickSight and Visualize

1.  Navigate to the **Amazon QuickSight** service in your AWS console. ➡️
2.  From the dashboard, select **Datasets** \> **New dataset**.
3.  Choose **S3** as the data source.
4.  Give your data source a name (e.g., "NetflixData") and point it to the `manifest.json` file you just uploaded. Click **Connect**. 🔗
5.  Once the data source is created, click **Visualize** to enter the QuickSight Analysis workspace. ✨
6.  You are now ready to build your charts\! You can recreate the dashboard by creating visuals like:
      * A **Pie chart** 🥧 for the `type` field (Movie vs. TV Show).
      * A **Bar chart** 📊 for the `listed_in` field to see top genres.
      * A **Line chart** 📈 showing the count of titles by `release_year`.
<img width="2556" height="2466" alt="Analytics" src="https://github.com/user-attachments/assets/2dad3bd9-7ae2-41b9-b9e3-2539603a65cb" />

Enjoy exploring the data and creating your own insights\! 🎉
