# SZ-EQ-trigger-stats
A project to explore shallow-deep seismicity interactions in subduction zones

## Requirements
Project was written as Jupyter Notebooks in Python 3, and latest run was in Python 3.9. The following packages are essential (version in brackets):
- numpy(==1.20.3)
- matplotlib (==3.4.2)
- scipy(==1.7.0)
- scikit-learn(==0.24.2)
- pandas(==1.3.0)
- geopandas(==
- obspy(==1.2.2)
- shapely(==1.7.1)

## Contents
The project works using 2 Jupyter notebooks:
- EQ_declustering.ipynb - this notebook contains routines necessary to perform EQ declustering using the methods by Zaliapin (e.g Zaliapin and Ben-Zion, 2013) and the ETAS method (utilising code by Mizrahi et al. (2021). The Mizrahi routines are incomplete, and will need further development until they can be fully effective on a large catalog. The notebook also includes starter functions to expand Zaliapin declustering to 3D (incorporating EQ depth).
- EQ_triggering_figs.ipynb - includes routines necessary to perform analyses and plot figures using the declustered catalogs. Also includes routines to sort earthquakes into subregions.

## File structure
The notebooks included in this project both work with a certain file structure. It is expected that for every region (e.g. SAM, Japan), the following folders will be present in the folder containing the notebooks:
- {region}_EQ_data
	- figs-PDF (subfolders get created by figure plotting routines)
		- GR_plots
		- sync_coeffs
		- sync_coeffs_bars
		- periodograms
		- rates
	- Mizrahi_ETAS_decluster (Mizrahi ETAS declustered catalogs - gets created by declustering routine)
	- Mizrahi_ETAS_inversion (inversion results for Mizrahi ETAS - gets created by declustering routine)
	- Zaliapin_decluster (gets populated with CSV files produced by 		          declustering routines)
	- zonal_cat (gets created by geographical sorting routine)
		- zones (individual folders for each subregion, containing raw                     and declustered catalogs produced by location sorting routine                    in EQ_triggering_figs.ipynb)
	- raw_catalog_data.csv (produced by ISC data search function)
	- large_eq.csv (contains large EQs you want marked on figures)

## Usage
The file `SAM_EQ_data` is included for testing all the code. This can be accessed by most functions using region code 'SAM'.
