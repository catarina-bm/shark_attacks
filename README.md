# Shark Attacks – Coastal Tourism Safety

Ironhack Data Analytics Bootcamp – Mini project

## About the project

We cleaned and analysed the Global Shark Attack File, a public dataset with shark incidents from around the world. The data had a lot of problems, like dates in different formats, inconsistent country names, free-text activities and missing values.

We used Python and pandas to clean the data and then answered a few questions about it.

## Business case

We looked at the data from the point of view of a coastal tourism authority. They want to know where and during which activities shark incidents happen the most, so they can decide where to put lifeguards and warning signs and which activities need more safety information.

## Hypotheses

- **H1 – Geographic concentration:** The USA and Australia account for the majority of recorded shark incidents.
- **H2 – Activity:** Surfing is the activity associated with the highest number of recorded shark incidents.
- **H3 – Incident type:** Unprovoked incidents account for the majority of provoked and unprovoked incidents combined.
- **H4 – Fatality:** Most recorded shark incidents with known outcomes are non-fatal.

## Dataset

- Source: [Global Shark Attack File](https://www.sharkattackfile.net/incidentlog.htm)
- File: `GSAF5.xls`
- 7,125 rows and 23 columns
- Columns we used: `date`, `year`, `type`, `country`, `state`, `activity`, `fatal`

## Data cleaning

- Cleaned the column names (removed spaces, lowercase, renamed `Fatal Y/N` to `fatal`)
- Kept only the columns we needed
- `type`: grouped uncertain categories (Questionable, Invalid, Unverified…) into `Unconfirmed`
- `year`: changed from decimal to whole numbers and removed impossible years like 0 or 77
- `country`: fixed capital letters and different names for the same country (for example USA, Usa and United States)
- `state`: fixed capital letters and filled missing values with `Unknown`
- `activity`: grouped the free text into categories like Surfing, Swimming and Fishing using keywords
- `date`: extracted the month using regex
- `fatal`: kept only `Y` and `N`, everything else became `Unknown`
- Checked for duplicates

## Results

**H1 – supported**

- The USA has 2,597 incidents (36.4%) and Australia has 1,538 (21.6%). Together they have 58% of all incidents.
- The year with the most incidents in the USA was 2015 (73).
- Florida is the state with the most incidents (1,200).
- In Florida, the year with the most incidents was 2003 (45) and the month with the most incidents was September (187).

**H2:** [to be completed]

**H3: – supported**

- We analysed 2,506 provoked and unprovoked incidents from 2000 onwards.
- 2,274 were unprovoked (90.7%) and 232 were provoked (9.3%).
- Most incidents happened without the person interacting with the shark.

**H4: – supported**
- Out of 2,506 incidents, 2,483 had a known outcome. The 23 with an unknown outcome were left out of the percentages.
- 2,230 were non-fatal (89.8%) and 253 were fatal (10.2%).
- Most shark incidents did not result in death.

## Limitations

- The data shows reported incidents, not the real risk. We don't know how many people were in the water.
- Recent years may not be complete yet, because new cases are added later.

## Files

- `GSAF5.xls` – original dataset
- `shark_attack_[name of each group member].ipynb` – notebook with the cleaning and analysis
- `README.md` – this file

## Presentation

Slides: [https://docs.google.com/presentation/d/1N94bQWtUjDHFXKy2xSwaIaPm4xqhpBOtrG41ZD_uiJY/edit?usp=sharing]

## Team

- Catarina Braga Macedo
- Nwobodo Chiagoziem
- Telma Guerreiro
