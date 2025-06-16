                                                         🔐 Cybersecurity: Suspicious Web Threat Interactions
This project analyzes AWS CloudWatch-style web traffic logs to detect and investigate suspicious patterns that may indicate security threats or potential attacks.

## 🎯 Objectives
- Clean and analyze web traffic logs  
- Visualize request patterns and anomalies  
- Detect suspicious traffic using anomaly detection models  
- Classify traffic using machine learning  
- Extract actionable insights to support cybersecurity awareness

## 📁 Dataset Overview
- **File:** `CloudWatch_Traffic_Web_Attack.csv`  
- **Source:** Web traffic collected via AWS CloudWatch  
- **Columns Include:** `src_ip_country_code`, `protocol`, `bytes_in`, `bytes_out`, `detection_types`, `creation_time`, etc.

## 📊 Exploratory Data Analysis (EDA)
- Count of traffic by protocol and country  
- Bytes In vs Bytes Out distribution  
- Detection types by country  
- Anomaly detection visualization using Isolation Forest
- 
## 🤖 Model Approach
### ✅ Anomaly Detection (Unsupervised)
- **Model:** Isolation Forest  
- **Input:** `bytes_in`, `bytes_out`, `duration_seconds`  
- **Output:** Labeled each session as `Suspicious` or `Normal`

### ✅ Classification (Supervised)
- **Model:** Random Forest  
- **Target:** `detection_types == 'waf_rule'`  
- **Performance:** High accuracy on imbalanced dataset  

## 💡 Key Insights Summary
- **HTTPS** is the dominant protocol in the dataset.  
- Most traffic originates from **US, CA, and DE**.  
- The **Bytes In vs Bytes Out** histogram shows traffic distribution, with some extreme spikes.  
- The **Anomaly Detection plot** highlights suspicious sessions with abnormal byte patterns.  
- **Detection Types by Country** confirms that **'waf_rule'** threats are mostly from US, CA, and DE.  
➡️ Overall, there's a clear concentration of suspicious activity from a few countries, and anomaly detection helps visually flag these unusual patterns.
## 🧰 Tools Used
- Python  
- Google Colab  
- pandas, seaborn, matplotlib  
- sklearn (IsolationForest, RandomForestClassifier)
