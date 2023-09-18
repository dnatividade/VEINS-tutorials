# VEINS TIPS AND TRICS
```
2020-06-01
```

### VEINS
**Calculate transmission range**
```
https://groups.google.com/forum/#!topic/omnetpp/m9rFqQ92-OA
https://groups.google.com/forum/#!topic/omnetpp/7MzAR3iqy74
https://stackoverflow.com/questions/55172247/change-the-transmission-signal-strength-for-a-specific-set-of-vehicles-during-th/55173632#55173632

NEW
https://stackoverflow.com/questions/58042512/how-to-fix-the-transmission-range-of-rsu-1000m-and-vehicles300m-in-veins-5-0
https://stackoverflow.com/questions/55172247/change-the-transmission-signal-strength-for-a-specific-set-of-vehicles-during-th
```

**Seed and random numbers**
```
https://stackoverflow.com/questions/37190939/omnet-uniform-random-number-generation
https://stackoverflow.com/questions/46442677/cant-generate-random-number-in-omnetpp
https://stackoverflow.com/questions/4414528/specifying-the-seed-for-a-random-number-in-omnet
```

**Change message size**
```
https://stackoverflow.com/questions/35564083/changing-wsmwave-short-message-packet-size-in-veins/35576940#35576940
```

**Step less than 1 second**
```
https://stackoverflow.com/questions/59038058/how-to-get-vehicle-information-in-less-than-one-second
```

**SUMO**
```
https://sumo.dlr.de/docs/Tutorials/quick_start.html
https://sumo.dlr.de/docs/Basics/Using_the_Command_Line_Applications.html
```

**Vehicles teleport**
```
https://stackoverflow.com/questions/59058236/how-to-keep-the-vehicle-stopped-on-the-road-for-1000-seconds
https://sourceforge.net/p/sumo/mailman/message/28272523/
https://sumo.dlr.de/docs/Simulation/Why_Vehicles_are_teleporting.html
```

**Question aboute create flow**
```
https://stackoverflow.com/questions/49777285/how-to-randomly-generate-flow-in-sumo-simulation-given-a-fixed-vehicle-number
```

**Definition of Vehicles, Vehicle Types, and Routes**
```
https://sumo.dlr.de/wiki/Definition_of_Vehicles,_Vehicle_Types,_and_Routes
```

**Tutorials/Driving in Circles**
```
https://sumo.dlr.de/wiki/Tutorials/Driving_in_Circles
```

**OMNeT++**
```
Adding Statistics Collection
https://docs.omnetpp.org/tutorials/tictoc/part5/
```

**C++**
```
Map and Multimap
https://gist.github.com/marcoscastro/34ceed299b0165434384

Unordered MAP
https://www.geeksforgeeks.org/unordered_map-in-cpp-stl/

Hash table implementation
https://www.digitalocean.com/community/tutorials/hash-table-in-c-plus-plus

```

**Vanet Researchers**
```
Aziza Ben Mosbah:
https://www.researchgate.net/profile/Aziza_Ben_Mosbah2

Azza Ben Mosbah
https://www.researchgate.net/profile/Azza_Ben_Mosbah
```

### DICAS
```
- Para rodar em linha de comando, é necessário alterar o compilador para o modo "relesase": no eclipse, clique com o botão direito na pasta raíz do projeto -> Build COnfigurations -> Set Active -> gcc-release

- Para determinar o fim da simulação, usar a tag <end value="xxx"/> no arquivo .sumo.cfg

- Ao alterar as configurações de rotas e fluxo de veiculos no SUMO, pode-se dar um erro ao tentar rodar a simulação no OMNet++. A solução é deletar os arquivos binários gerados na pasta exemples/veins/
(Source: dnatividade (2019)
```

### Métodos diversos
```
 traciVehicle->slowDown(2, simTime())
 traciVehicle->getMaxSpeed()
 traciVehicle->setMaxSpeed(30)
 traciVehicle->getSpeed()
 traciVehicle->setSpeed(0)
 
 traci->lane("30350450#1_0").getMaxSpeed()
 traci->lane("30350450#1_0").getWidth()
 getLaneId();
 traciVehicle->setMaxSpeed(30);
 traciVehicle->setSpeed(30);

	myMacAddress = getParentModule()->getParentModule()->getIndex();
	myId = getParentModule()->getParentModule()->getFullPath();
```

