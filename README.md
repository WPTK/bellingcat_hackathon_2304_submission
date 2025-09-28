##### bellingcat_hackathon_2304_submission

# BOMBARDIER WATCH

_Bellingcat Hackathon 2023.04 submission_

## Team Members
Jack Kerr — https://github.com/jckkrr

Group name: Jackmaster

## Tool Description
The unfiltered, crowd‑sourced flight‑tracking service ADS‑B Exchange offers an excellent view of air traffic movements. But finding out who is on board is another matter. This tool provides one possible solution: by showing which business jets arrived or departed from the same location on the same day, it may be possible to infer who met whom.

Development notes:
- Data source: ADS‑B Exchange.
- This prototype uses data from a single day, sampled at the start of each minute.
- Results are filtered to include Bombardier, Gulfstream, Dassault, and Embraer business jets that are shown as "grounded".


## Installation
Access the app via your browser:

https://jckkrr-bellingcat-hackathon-2304-submissio-streamlit-app-4xfjl3.streamlit.app/

Part of my philosophy when building intelligence tools is that people with few technological skills (like journalists and lawyers) should be able to use them. Therefore, I make my tools available via Streamlit, which allows Python scripts to be deployed online. It can be buggy, however. In any case, no installation is required.

Optional: run locally
- Clone this repository.
- Create and activate a virtual environment.
- Install dependencies and start the app.

```powershell
python -m venv .venv
. .\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
streamlit run streamlit_app.py
```


## Usage

![image](https://user-images.githubusercontent.com/69304112/233846351-947c5fde-e061-49f5-8d02-b3de6450d0ca.png)

As this is a prototype with limited access to data, only one day is available; therefore the date dropdown is disabled.

![image](https://user-images.githubusercontent.com/69304112/233846488-2f688dff-dda6-4054-b826-e37b7451fb00.png)

The globe shows where business jets were recorded on the ground. This can surface unusual locations where business jets may appear.

![image](https://user-images.githubusercontent.com/69304112/233846567-abb6242c-c742-44d2-b6d2-f346bbcfe628.png)

This section lets you choose a location where jets were recorded and examine the results for interesting matches. Unfortunately, the majority of planes are registered to charter companies, but this tool should still produce interesting results over time.

![image](https://user-images.githubusercontent.com/69304112/233846689-4f8a14da-3bd5-435c-8cb8-e6b9cd720443.png)

Lastly, you can check by company to see which other registered owners had jet(s) in the same location.

## Additional Information

ADS‑B Exchange makes historical data available in 5‑second snapshots—17,280 files per day. A few hours of observations, when combined, can result in massive dataframes with millions of rows. Accessing this full‑resolution data would be ideal. This repository includes one notebook for downloading a day’s data, one for compiling it into a dataframe, and another for cleaning and adding plane registrant details. In that second stage, filters are applied so that only business jets are included in the concatenated dataframe, keeping it to a more manageable size. While data at 5‑second resolution is available, this app currently uses data sampled every 60 seconds.

