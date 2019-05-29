# Sumo tutorial
#### Tutorial to create an exported OpenStreetMap map and flow of vehicles.

## Exporting map from OpenStreetMap
- Open https://www.openstreetmap.org/ and navigate to the desired location;
- Click in *Export* -> *Manually select a different area*;
- Select the desired area and click in *Export*;

![Screenshot from 2019-05-28 21-55-40](https://user-images.githubusercontent.com/43869367/58521663-8bf86c00-8193-11e9-8d35-e91e582982c9.png)

- Save the map in OSM format, such as: *ufla.osm*.


## Importing map to SUMO
- Convert OSM file to SUMO format:
- - `netconvert --osm-files map.osm -o map.net.xml`
- Copy *osmPolyconvert.typ.xml* file (in this GitHub directory) to your project directory;
- - this file is a template for creating map polygons, such as buildings, trees, etc.
- Create map polygons (using the template copied before):
- - `polyconvert --net-file ufla.net.xml --osm-files ufla.osm --type-file osmPolyconvert.typ.xml -o ufla.poly.xml`


## Create a flow of vehicles
- Create an environment variable named *SUMO_HOME*, with the SUMO path, as follows:
- - `export SUMO_HOME=~/src/sumo/`
- - OBS.: Check correct path from your SUMO installation;
- Create a sumo configuration file:
- - Use the file "create-sumo-config1.sh" to create a file called *ufla.sumo.cfg* with the structure as follows:
```xml
<configuration>
	<input>
		<net-file value="ufla.net.xml"/>
		<additional-files value="ufla.poly.xml"/>
	</input>
</configuration>
```
- Create a flow configuration file, called *myflow.rou.xml*, as follows:
```xml
<routes>
	<flow id="flow1" color="red"   begin="0" end="120" number="10" departLane="random" from="" to=""/>
	<flow id="flow2" color="green" begin="0" end="120" number="15" departLane="random" from="" to=""/>
</routes>
```
- Open SUMO-GUI to get lanes names to create the flows:
- - `sumo-gui ufla.sumo.cfg`
- - Copy the lanes names and paste into the *myflow.rou.xml*, such as the animation:

![get-lanes](https://user-images.githubusercontent.com/43869367/58526377-30cf7500-81a5-11e9-9bed-fe8bb46dd131.gif)

- Close *sumo-gui*;
- Create the flows:
- - `duarouter -n ufla.net.xml -r myflow.rou.xml --randomize-flows -o ufla.rou.xml`
- Put the line `<route-files value="ufla.rou.xml"/>` into the *ufla.sumo.cfg*, as follows:
```xml
<configuration>
	<input>
		<net-file value="ufla.net.xml"/>
		<route-files value="ufla.rou.xml"/>
		<additional-files value="ufla.poly.xml"/>
	</input>
</configuration>
```
- Done!
