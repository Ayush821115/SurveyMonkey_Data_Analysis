# SurveyMonkey_Data_Analysis
This project demonstrates a real-world data cleaning and processing using Excel and Python.

 📁 Project Structure

- `Raw_data.xlsx`: The initial unprocessed survey data.
- `Data - Survey Monkey Output.xlsx`: Cleaned and partially arranged version of the raw data using Excel.
- `Data_Modifier.ipynb`: Jupyter Notebook that automates the data transformation, reshaping, and column mapping.
- `Final Output.xlsx`: Final version of the dataset after all transformations.

---

## 🔄 Data Processing Steps

### 📊 Initial Setup
- Loaded the cleaned Excel data from the **"Edited Data"** sheet in `Data - Survey Monkey Output.xlsx`.
- Set display options for better visibility during development.

### 🧹 Data Cleaning & Preparation
- Created a copy of the dataset to preserve the original.
- Dropped irrelevant columns that weren’t useful for analysis:
  - `Start Date`, `End Date`, `Email Address`, `First Name`, `Last Name`, `Custom Data 1`.

### 🔃 Reshaping the Data
- Performed a **melt operation** using `pandas.melt()` to reshape from wide to long format:
  - `id_vars`: First 8 identity columns.
  - `value_vars`: All survey question columns.
  - Result: Two new columns — `Question + subquestion` and `Answer`.

### 🔗 Mapping with Metadata
- Loaded the **"Questions"** sheet to retrieve human-readable labels for survey questions.
- Dropped unnecessary columns from the metadata.
- Renamed `Question+Subquestion` to match the melted data.
- Merged the melted dataset with the questions metadata using a common key.

### 🧽 Filtering and Cleanup
- Removed rows with missing answers (`NaN`) to keep only valid responses.

### 📊 Aggregation (New Step)
- Counted the number of **respondents who gave the same answer** to the same `Question + subquestion`.
- Created a frequency distribution table useful for plotting or further analysis.

  ## 🧪 Tools & Technologies Used

| Tool          | Purpose                                   |
|---------------|-------------------------------------------|
| **Excel**     | Initial manual cleaning and inspection    |
| **Python**    | Data transformation and automation        |
| **Pandas**    | Data wrangling and manipulation           |
| **Jupyter**   | Interactive scripting and documentation   |

