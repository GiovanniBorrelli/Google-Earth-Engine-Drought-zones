# **SPEI and Fire Risk Analysis for Sicily**  

This script is designed to run on **Google Earth Engine (GEE)** and analyzes the **Standardized Precipitation-Evapotranspiration Index (SPEI)** over **Sicily**, along with historical fire occurrences. It uses **TerraClimate** and **FireCCI** datasets to assess drought conditions and fire risk.

---

## **How to Run the Script**  

### **1. Open Google Earth Engine**  
Ensure you have access to [Google Earth Engine Code Editor](https://code.earthengine.google.com/).  

### **2. Create a New Script**  
- Click on the "Scripts" tab on the left panel.  
- Click **"New"** > **"File"** and select **"JavaScript"**.  

### **3. Copy & Paste the Code**  
Copy the script provided in this file and paste it into the Code Editor.

### **4. Run the Script**  
Click the **"Run"** button at the top of the editor.  

---

## **Description of the Script**  

### **1. Define Time Window and Target Date**  
- The **SPEI** is calculated for a **90-day period** ending on **August 21, 2017**.  

### **2. Load and Filter Data**  
- **TerraClimate dataset** provides precipitation (`pr`) and evapotranspiration (`pet`).  
- The script filters data for **Sicily** from **FAO GAUL** administrative boundaries.  
- Fire occurrences are extracted from **ESA FireCCI** dataset.  

### **3. Compute SPEI (Drought Index)**  
- Calculates the **water balance** (Precipitation - Evapotranspiration).  
- Standardizes the values to derive **SPEI**, indicating drought severity.  

### **4. Visualize Data on the Map**  
- **SPEI index** is color-coded from **extreme drought (-2.0)** to **extreme wet conditions (+2.0)**.  
- **Fire events** are classified into:  
  - **High drought areas with fires** (black)  
  - **Low drought areas with fires** (grey)  

### **5. Risk Classification**  
- Areas are categorized into **high/low drought** with and without fire occurrence.  
- A **legend** is added for better interpretation.  

---

## **Expected Output**  
After running the script, you will see:  
- A **color-coded drought map** of Sicily.  
- Burn areas overlaid on the **drought regions**.  
- A **legend** explaining the drought and fire risk levels.  

---

## **Customization Options**  
- **Change the target date** by modifying:  
  ```js
  var targetDate = '2017-08-21';
  ```
- **Adjust the time window** (default = 90 days):  
  ```js
  var timescaleDays = 90;
  ```
- **Filter a different region** by changing the administrative boundary filter:  
  ```js
  .filter(ee.Filter.eq('ADM1_NAME', 'Sicilia'))
  ```

---

## **Requirements**  
- A **Google Earth Engine** account.  
- Internet connection to access remote datasets.  

---

## **License**  
This script is provided **as-is** for research and educational purposes. Modify and use it at your own discretion.

<p align="center">
  <img src="https://github.com/user-attachments/assets/56efae54-d0d5-4f49-bab5-0a26802052c7" width="20%">
</p>


