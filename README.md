# 🐦 **X (formerly Twitter) Sentiment Analysis and Bot Detection** 🚀

This repository contains code, datasets, and models for analyzing Twitter data, performing sentiment analysis, and detecting bot accounts using machine learning models. The main focus is on utilizing a trained **SetFit** model and other data-driven approaches to process and evaluate Twitter data.

---

## 📝 **Project Overview**

The project is centered around analyzing **company-related Twitter data** to:

1. 🔍 Detect bots vs. human accounts 🤖👤  
2. 🧠 Perform sentiment analysis using a **SetFit** machine learning model 💬  
3. 📈 Provide insights into company mentions and opinions 📊  

The repository includes notebooks for data preprocessing, analysis, model training, and evaluation, along with preprocessed datasets for ease of use.

---
## 🛠️ **Environment and Requirements**

### 🐦 **X Profile Required + Chrome Browser**  
- A **X account** is required to scrape tweets.
- You'll need to have Chrome installed on your machine to be able to load X cookies for the data scraping 

### ⚠️ **Important: Main Notebook Requires Local Execution**  

The **Main_Company_Twitter_Opinions.ipynb** notebook requires **local execution** on your own machine.  
- Run locally on your machine (or one with access to Chrome) since this notebook opens a **(private) Chrome tab** to collect cookies for X (formerly Twitter) scraping.  
- Just ensure you have Google Chrome installed
#### **Run in a virtual environment using Python Virtual Environment version: 3.12.7 (tested)**

To ensure smooth execution of the notebooks, we recommend the following setup:
### 
### 💻 **⚠️ ONLY FOR `SetFit_Model_Train.ipynb` - Google Colab (Recommended)**  
- For computationally intensive tasks like **SetFit model training** (e.g., `SetFit_Model_Train.ipynb`), we recommend running the notebooks in **Google Colab**.  
- Google Colab provides free access to GPUs (T4), which will significantly speed up the model training process. 🚀  

   **How to Run in Google Colab:**  
   - Upload the notebook to Google Drive.  
   - Open it in Google Colab.  
   - Connect to a GPU runtime:  
     - Navigate to **Runtime** > **Change runtime type** > Select **GPU**.  
- Estimated runtime of `SetFit_Model_Train.ipynb` with 10,000 samples: 22 minuttes


### 🔑 **Together API Key Required**  
To run parts of the analysis (e.g.,the sentiment analysis), you must provide a **Together API Key**.  
- **Free API Key**: Sign up for a free account here: [Together API Sign-Up](https://api.together.ai/signin) (no credit card required 💳❌).  
- **Setup**: Add your API Key to the designated variable `TOGETHER_API_KEY` in the notebook.  

   **Note**: Adding a credit card increases your API rate limits, allowing faster data processing (from 60 to 600).

- Estimated costs for running 750 tweets: 0.03 dollars (so you'll have plenty of try's with 5$ free credit)

---
---

### 1. 🧹 **EDA_training.ipynb**  
This notebook performs **Exploratory Data Analysis (EDA)** on the X (formerly Twitter) dataset.  
- Cleans and preprocesses the Twitter data.  
- Provides an overview of the data structure, missing values, and distribution.  
- Outputs cleaned datasets ready for model training.  

---

### 2. 🐦 **Main_Company_Twitter_Opinions.ipynb**  
This notebook focuses on **company-related Twitter analysis**.  
- Allows users to **scrape Twitter data** based on user-specified keywords using the `TwiKit` library.  
- Performs keyword-based data filtering and sentiment analysis.  
- Provides visualizations and insights into the opinions about specific companies and topics.  

**User Setup Instructions**:  
- Input your search keywords (e.g., `['Novo Nordisk', 'Ozempic', 'WeGovy']`) and desired number of tweets.  
- Manage Twitter API usage limits to avoid rate-limiting.  

---

### 3. 🧠 **SetFit_Model_Train.ipynb**  
This notebook is dedicated to **training the SetFit model** on labeled Twitter data.  
- Loads preprocessed datasets containing labeled user tweets `TwitterData_Joined.csv`.  
- Implements and fine-tunes the SetFit model for sentiment analysis or bot detection tasks.  
- Outputs a trained model ready for predictions saved as `setfit_model`.  

---

### 4. ✅ **SetFit_Dataset_Validation.ipynb**  
This notebook performs **validation and evaluation** of the trained SetFit model for bot detection and sentiment analysis.  
- Benchmarks the model performance using labeled dataset of X (formerly Twitter) users, based on the **TwiBot-22** dataset, where we then scrape user tweets based on the TwiBot-22 labeled profiles as validation dataset.
   - 📄 **Reference**:  
   - Feng, S., Tan, Z., Wan, H., Wang, N., Chen, Z., Zhang, B., Zheng, Q., Zhang, W., Lei, Z., Yang, S., Feng, X., Zhang, Q., Wang, H., Liu, Y., Bai, Y., Wang, H., Cai, Z., Wang, Y., Zheng, L., Ma, Z., Li, J., & Luo, M. (2023). *TwiBot-22: Towards graph-based Twitter bot detection*. arXiv. [https://doi.org/10.48550/arXiv.2206.04564](https://doi.org/10.48550/arXiv.2206.04564)

- Evaluates key metrics such as **accuracy**, **precision**, **recall**, and **F1-score**.  
- Provides insights into the model's ability to generalize to real-world data.
  
---

## File Structure 📂:

```bash
.
├── setfit_model/                       # Directory for SetFit model files
├── EDA_training.ipynb                  # Notebook for exploratory data analysis (EDA) and training preparation
├── Main_Company_Twitter_Opinions.ipynb # Analysis of company X mentions and opinions
├── README.md                           # This documentation file
├── SetFit_Dataset_Validation.ipynb     # Validation of SetFit dataset and model outputs
├── SetFit_Model_Train.ipynb            # Training the SetFit model
├── requirements.txt                    # List of dependencies and required Python libraries
│
Data Files:
├── TwitterData_Joined.csv                          # Combined X data
├── novo_bots_llm_processed.json                    # LLM-processed bot data
├── novo_humans_llm_processed.json                  # LLM-processed human data
├── scraped_novo_twitterdata.csv                    # Raw scraped X data
├── scraped_novo_with_setfit_predictions.csv        # Data with SetFit model predictions
├── scraped_validation_human_bot_twitter_dataset.csv # Validation dataset for humans and bots
├── userid_labels-(twi-bot_22).csv                  # UserID labels for bot detection
│
└── .gitignore                           # Specifies files to ignore in Git version control
```
