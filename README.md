# Does Money Buy Years?

This is my ECON 3916 midterm project on GDP per capita and life expectancy across 186 countries from 2000 to 2015.

[Open the notebook in Colab](https://colab.research.google.com/drive/1uH2OgyHFs89N3S8dT_kQUmlWdOBoCM-w?usp=sharing)

## Question

Across countries from 2000 to 2015 do countries with higher GDP per capita have a longer life expectancy at birth if I hold adults' mean years of schooling and the year fixed?

## Hypothesis

Income buys food and clean water and sanitation and health care so I expect a positive coefficient on log GDP per capita that gets smaller once I hold schooling fixed because schooling raises both income and health.

## Data

| File | Source | What it holds |
|---|---|---|
| `data/wb_life_expectancy.csv` | [World Bank SP.DYN.LE00.IN](https://data.worldbank.org/indicator/SP.DYN.LE00.IN) | life expectancy at birth in years from the UN Population Division |
| `data/wb_gdppc_ppp.csv` | [World Bank NY.GDP.PCAP.PP.KD](https://data.worldbank.org/indicator/NY.GDP.PCAP.PP.KD) | GDP per capita in constant 2021 PPP dollars |
| `data/wb_health_share.csv` | [World Bank SH.XPD.GHED.GE.ZS](https://data.worldbank.org/indicator/SH.XPD.GHED.GE.ZS) | government health spending as a percent of government spending from WHO |
| `data/wb_countries.csv` | the country file that comes in each World Bank download | which codes are countries and which are regional totals |
| `data/hdr25_time_series.csv` | [UNDP Human Development Report 2025](https://hdr.undp.org/data-center/documentation-and-downloads) | mean years of schooling for adults 25 and older |

The World Bank last updated its three data files on 2026-10-08 and I downloaded them and the UNDP file on 2026-11-07 and I saved the UNDP file as UTF-8 and the three World Bank data files as they downloaded except I deleted the four title lines above the header so each file starts at its column names.

## How to run

1. Open the notebook in Colab with the link above and run the cells from top to bottom.
2. The data cells before Section 1 read the five files in `data/` straight from this repository so the notebook doesn't change when the World Bank or UNDP revise their numbers.

The notebook's last code cell (Numbers my report quotes) prints every number in the report so you can check each one against the PDF.

## Finding

Before I hold schooling fixed a country with twice the GDP per capita has a life expectancy 4.36 years higher and once I hold adults' schooling and the year fixed that falls to 3.41 years (95% CI 2.84 to 3.99 with N = 2,904 country-years in 186 countries) and the government health spending share explains only a little more of it. Within a country over time the link is less than half as large at 1.52 years per doubling (95% CI 0.55 to 2.49) so the estimate is a conditional association that doesn't show the causal effect of income.
