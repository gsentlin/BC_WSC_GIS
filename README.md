# BC_WSC_GIS
WSC Station Catchment Polygons

This project is intended to grow and refine the catchments for WSC stations in BC.

This is the first pass at the project.  The current .shp file includes catchments provided by Brad Sparks with BC MOE, Judy Kwan from Env.Canada, Dave West from EcoFish Research Ltd, and Gabe Sentlinger from Aquarius R&D Inc.

If you find errors, or would like to suggest improvements or additions, please contact the owner of this repository, Gabe Sentlinger.

Contents:
BC_WSC_Catchments_V1: This file currently consists of 465 catchments delineated at from 1:20k mapping.  This database only includes the station ID and catchment area.

BC_WSC_Catchments_vAtt_V1: This is the same file as BC_WSC_Catchments_V1 but has many derived attributes.  The spatial data sources used to derive catchment attributes are as follows:
1.	Digital Elevation Model (DEM): We used elevation data primarily provided by GeoBase and is the 1:50k Canadian Digital Elevation Data (CDED).  This data is very good for BC: we have found that elevation contours are within 10m of BC Terrain Resource Inventory Mapping (TRIM) contours.  However, it is very time consuming to process for larger areas.  For this study, we chose to use a coarser gridded Shuttle Radar Topography Mission DEM.  It has recently become available at 30m for most of the globe, but we chose to derive watershed parameters from a coarser (500m) resolution product because:
•	We were able to derive watershed parameters using the 500m product that were highly correlated with parameters previously derived from the higher resolution CDED product.  
•	We wanted to derive the key parameters for all WSC polygons within the province of BC and for those catchments that span provincial and international boundaries.  
1.	Several layers are derived from the DEM
a.	The hillshade image (using an azimuth of 180° and elevation of 45° with shadows, a.k.a. Solar Exposure), 
b.	Slope in % (rise/run)
c.	Median Elevation, 

2.	Glacier coverage: We used the 1:50k NTS glacier coverage database
3.	Lake coverage: We used the Freshwater Atlas (FWA) lake polygons
4.	PRISM Monthly Precipitation (ppt): Produced by the Oregon Climate Center (Daly 2002).  This regression model uses local long-term meteorological stations along with DEM data to estimate the local (1km² pixels) monthly precipitation.  We provide the Annual ppt and June-September ppt.
5.	Potential Evapo-Transpiration (PET) (Trabucco 2009): This product has been found to be very effective for estimating key watershed parameters.
6. 	Obedkoff Zone: This the Zone from Bill Obedkoff's excellent streamflow inventory work for BC.  The Zone corresponds to the centroid of the catchment, although many catchments span multiple zones.

