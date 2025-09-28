# Bombardier Watch  
### Bellingcat Hackathon Submission (April 2023)  

**Team:** Jackmaster  
**Member:** [Jack Kerr](https://github.com/jckkrr)  

---

## Overview  
Bombardier Watch is a prototype tool that analyzes business jet movements using data from [ADS-B Exchange](https://www.adsbexchange.com/).  

While ADS-B Exchange provides an unfiltered, crowd-sourced view of global air traffic, identifying *who* is on board is a different challenge. This tool offers one approach: by showing which jets arrived or departed from the same locations on the same day, it may be possible to infer meetings and connections between individuals or organizations.  

---

## Development Notes  
- Data source: **ADS-B Exchange**  
- Prototype model uses **one day of data**, recorded at the start of each minute  
- Results are filtered to only include **Bombardier, Gulfstream, Dassault, and Embraer** business jets that are listed as **“grounded”**  

---

## Installation  
You can access the app directly in your browser via Streamlit:  
👉 [Launch the App](https://jckkrr-bellingcat-hackathon-2304-submissio-streamlit-app-4xfjl3.streamlit.app/)  

Streamlit was chosen so that people without technical skills (such as journalists or lawyers) can use the tool easily. No installation is required. Note: Streamlit deployments can occasionally be unstable.  

---

## Usage  

### Example Visualizations  
![Jet List](https://user-images.githubusercontent.com/69304112/233846351-947c5fde-e061-49f5-8d02-b3de6450d0ca.png)  

As this is a prototype with limited access to data, only **one day** is available. The **date dropdown** has been disabled.  

![Globe View](https://user-images.githubusercontent.com/69304112/233846488-2f688dff-dda6-4054-b826-e37b7451fb00.png)  

The **globe visualization** shows where business jets were recorded as being on the ground, highlighting unusual or noteworthy locations.  

---

### Location Search  
This section allows you to choose a location where jets were recorded and review potential matches. While many planes are registered to charter companies, meaningful patterns can still emerge over time.  

![Location Example](image-placeholder.png)  

---

### Company Search  
You can also search by **company/owner** to see which other registered owners their jets shared a location with.  

![Company Example](image-placeholder.png)  

---

## Additional Information  
ADS-B Exchange provides historical data in **5-second snapshots**, totaling 17,280 files per day. Combining just a few hours of this data can produce dataframes with millions of rows. Accessing the full dataset would be ideal for scaling the tool.  

This repository includes:  
- A script for **downloading a day’s worth of data**  
- A script for **compiling data into a dataframe**  
- A script for **cleaning data and adding registrant details**  

During the cleaning stage, filters ensure only business jets are included in the concatenated dataframe, keeping it manageable in size. While data is available every 5 seconds, this app currently uses snapshots taken every 60 seconds.  

---

## License  
This project is licensed under the [MIT License](LICENSE).  
