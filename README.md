# NYC-Parcel-VKT-Estimation

This repository gives the code and data involved in the process of estimating the New York City parcel delivery service induced vehicle-kilometer-traveled (VKT). This project first estimate the number of residential parcels generated from the whole NYC area. Figure 1 illustrate the daily delivery volume distribution across the whole city by census tract.

<p align="center">
  <img src="https://github.com/BUILTNYU/NYC-Parcel-VKT-Estimation/blob/main/Figure/volume.png",width="600" height="400">
  <br>
  <em>Figure 1. NYC daily residential parce delivery volume.</em>
</p>

After getting the result, volume and stops information for Amazon, Fedex, UPS, and USPS are generated. The distribution center information is obtained from July, 2022 and the corresponding service areas are estimated based on shortest distance. Figure 2 presents the facility locations and their corresponding service areas.

<p align="center">
  <img src="https://github.com/BUILTNYU/NYC-Parcel-VKT-Estimation/blob/main/Figure/area.png",width="600" height="600">
  <br>
  <em>Figure 2. Service Area of (a) USPS, (b) UPS, (c) FedEx, and (d) Amazon defined by census tract.</em>
</p>

We fit a continous approximation (CA) model to estimate the area-level VKT based on the stops information without generating detailed delivery tours for every stops. By applying the fitted CA model, the city level and area-level VKT can be estimated. Figure 3 shows the VKT density by Neighborhood Tabulation Areas.

<p align="center">
  <img src="https://github.com/BUILTNYU/NYC-Parcel-VKT-Estimation/blob/main/Figure/VKT.png",width="600" height="600">
  <br>
  <em>Figure 3. Average daily total VKT per squared kilometer by NTA.</em>
</p>

The parcel information is also used to evaluate the impact of potential E-cargo bike deployment. Figure 4 is a result of the potential VKT reduction by replacing some trucks with cargo bikes.

<p align="center">
  <img src="https://github.com/BUILTNYU/NYC-Parcel-VKT-Estimation/blob/main/Figure/bike.png",width="300" height="600">
  <br>
  <em>Figure 4. Workflow of the FD simulator process.</em>
</p>

Files includes:

"Stops_with_volume.zip": Estimated stops across NYC with pickup and delivery volume assigned for each courrier company. <br>
"Shapfile.zip": Shapefiles containing different geographic features of NYC. <br>
"Centroid_OSM.zip": OSM maps storing the centroid of NYC census tracts. <br>
"NTA_dist.zip": VKT result based on NTA. <br>
"CT assignment with OR-Tool.ipynb": Randomly selecting sample areas for CA fitting.<br>
"CA fitting.ipynb": Using the CA fitting result to calculate parcel volume.<br>
"Bikelane_network.ipynb": Evaluating bike line infrastructure for cargo bike operation in NYC.<br>

## License
The NYU NON-COMMERCIAL RESEARCH LICENSE is applied to the NYC parcel project. Please contact Joseph Chow (joseph.chow@nyu.edu) for commercial use.

For questions about the code, please contact: Hai Yang (hy1236@nyu.edu).
