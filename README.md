# GmE_Laboratory-4
1.What is the total area of all active parcels? 597,759.84 sqm
2. Which parcels exceed a threshold area? 5000 sqm: 57
3. How many parcels per zone?  
   Industrial: 17
   Residential: 35
   Commercial: 27
4. Which parcels intersect a proposed development boundary? (Just use the information of 
zone. e.g. which parcel are residential (or commercial) and suitable for development)
Only the suitable for development was 45 parcels output

Algorithm
1. Start
2. Load parcel shapefile from GeoJSON
    and proposed boundary file
3. Identify Active parcels to ensure we aren't calculating decommissioned land
4. Calculate area compute the area for each parcel(ensuring the coordinates reference system is in meters or feet, not degrees).
	Threshold Analysis Compare individual areas against a user-defined limit.
	Aggregation Group the data by the "Zone" column and count the entries.

5. Spatial Join: Perform a geometric intersection between the parcels and the development boundary, then filter by zone suitability (Residential/Commercial).

Pseudocode
 IMPORT spatial_library (geopandas)

FUNCTION analyze_parcels(parcel_data, boundary_data, threshold):
    # 1. Total Active Area
    active_parcels = parcel_data WHERE status is "Active"
    total_area = SUM of active_parcels.geometry.area
    
    # 2. Exceed Threshold
    large_parcels = active_parcels WHERE area > threshold
    
    # 3. Parcels per Zone
    zone_counts = active_parcels GROUP BY "Zone" COUNT "ID"
    
    # 4. Spatial Intersection & Suitability
    intersecting = SPATIAL_JOIN(active_parcels, boundary_data)
    suitable = intersecting WHERE zone IN ["Residential", "Commercial"]
    RETURN all_results

Pseudocode
 IMPORT spatial_library (geopandas)

FUNCTION analyze_parcels(parcel_data, boundary_data, threshold):
    # 1. Total Active Area
    active_parcels = parcel_data WHERE status is "Active"
    total_area = SUM of active_parcels.geometry.area
    
    # 2. Exceed Threshold
    large_parcels = active_parcels WHERE area > threshold
    
    # 3. Parcels per Zone
    zone_counts = active_parcels GROUP BY "Zone" COUNT "ID"
    
    # 4. Spatial Intersection & Suitability
    intersecting = SPATIAL_JOIN(active_parcels, boundary_data)
    suitable = intersecting WHERE zone IN ["Residential", "Commercial"]
    
    RETURN all_results
Pseudocode
 IMPORT spatial_library (geopandas)

FUNCTION analyze_parcels(parcel_data, boundary_data, threshold):
    # 1. Total Active Area
    active_parcels = parcel_data WHERE status is "Active"
    total_area = SUM of active_parcels.geometry.area
    
    # 2. Exceed Threshold
    large_parcels = active_parcels WHERE area > threshold
    
    # 3. Parcels per Zone
    zone_counts = active_parcels GROUP BY "Zone" COUNT "ID"
    
    # 4. Spatial Intersection & Suitability
    intersecting = SPATIAL_JOIN(active_parcels, boundary_data)
    suitable = intersecting WHERE zone IN ["Residential", "Commercial"]
    
    RETURN all_results


Pseudocode
 IMPORT spatial_library (geopandas)

FUNCTION analyze_parcels(parcel_data, boundary_data, threshold):
    # 1. Total Active Area
    active_parcels = parcel_data WHERE status is "Active"
    total_area = SUM of active_parcels.geometry.area
    
    # 2. Exceed Threshold
    large_parcels = active_parcels WHERE area > threshold
    
    # 3. Parcels per Zone
    zone_counts = active_parcels GROUP BY "Zone" COUNT "ID"
    
    # 4. Spatial Intersection & Suitability
    intersecting = SPATIAL_JOIN(active_parcels, boundary_data)
    suitable = intersecting WHERE zone IN ["Residential", "Commercial"]
    
    RETURN all_results



Pseudocode
 IMPORT spatial_library (geopandas)

FUNCTION analyze_parcels(parcel_data, boundary_data, threshold):
    # 1. Total Active Area
    active_parcels = parcel_data WHERE status is "Active"
    total_area = SUM of active_parcels.geometry.area
    
    # 2. Exceed Threshold
    large_parcels = active_parcels WHERE area > threshold
    
    # 3. Parcels per Zone
    zone_counts = active_parcels GROUP BY "Zone" COUNT "ID"
    
    # 4. Spatial Intersection & Suitability
    intersecting = SPATIAL_JOIN(active_parcels, boundary_data)
    suitable = intersecting WHERE zone IN ["Residential", "Commercial"]
    
    RETURN all_results

#Reflection
1.Where in your system do Sequence, Selection, and Repetition explicitly appear?
This activity was successfully demontrated the application of spatial data processing using python. I was load the parcel.json data in the run_lab4.py, analysis.py and demo.py. And appear in the terminal. 
2.If you removed your algorithm planning step, how would your implementation likely change? 
I learned for this activity If I removed the algorithm planning step would have fundamntal shifted the implementation from the proactive to reactive process. 
3.Where does spatial behavior live in your system, and why is that important? 
Spatial behavior was evaluated the geometric attributes like area_sqm , it is importnat because was tranforms static data into actionable intelligence. Without these programmed rules the coordinates just a number and an area just value by defining behavior. 
4. Why does analysis.py contain structured logic instead of demo.py? 
This activity for the analysis. py contain structure logic because it was designed  to be intersecting parcels wheareas demo.py is typically was analyze land parcels.
5.What would happen if all filtering logic were placed inside the Parcel class? 
I was not able to do the class filtering in this laboratory.  
6. If a new rule is added (e.g., “exclude inactive industrial parcels”), how easily can your current 
design adapt?
The results did not change because the core design logic remained constant, proving that the structural changes do not impact data output unless the execution code are modified.
7. How does separating structured logic from object behavior prevent “God classes”?
For this activity the separating structured logic from object behavior prevents the creation of God classes by adhering the Single Responsibility Pinciple, was eon ensure that the Parcel class only handled data storage. 
