# Sensor data mining

| | **Status** |
|---|:----|
| **circleCI** |[![CircleCI](https://circleci.com/gh/asw-i3a/sensor-data-mining.svg?style=svg)](https://circleci.com/gh/asw-i3a/sensor-data-mining)
| **code coverage** | _NOT NEED_
| **code quality** |_NOT NEED_
| **latest build** |_NOT NEED_

**Welcome to our sensor data mining micro-service**

> **Important:**  This micro-service is contained inside the domain of the i3a system, if you dont knoe what it is please, refer to the main page of the [poject](https://github.com/asw-i3a).

This repository contains a micro-service that is intended to mine data from the incidents submitted by sensors in order to get the most relevat metrics about it. Also it calculates some statistical important information that clients can use as desired.

### Autors
- [Guillermo Facundo Colunga](https://github.com/thewilly)
- [Carlos García Hernández](https://github.com/CarlosGarciaHdez)
- [Victor Suárez Fernández](https://github.com/ByBordex)

### Problem to mine
We have sensors, that are a type of agents but with int type set to 3. As every other sensor it has a sensorId, and submmits incidents to the system regularly. In order to increase eficiency, we must show the progress of the sensor readings, so me must (1) filter other agent's kind and the sensor's kind. And (2) compute all data for the sensor to get the metric the sensor is reading, and therefore return only the readings but not all the incidents data.

### Mining algorithm
As you can see in the code is a very simple algorithm, but perfectly valid for our porpouses.
1. The algorithm will get all the incidents sibmitted by the given sensorId.
2. From the sensor data the algorithm deduces which kind of sensor is and assigns a metric for it.
3. For every incident submitted by that sensor add the value of the metric selected, if exists, and the data of the reading as a timestamp in a map.
4. Retrun the map with all the readings and the selected metric.

**Complexity:** Search incidents + Compute data = O(n) + O(n). Being *n* the number of incidents submitted by the agent.

### Next version
Will include filtering by dates so you can get the same result as before but adding a lower data filter and a greater data filter. That is, all incidents between A and B, being A & B dates. (20/02/2018 00:21:34 - 20/02/2019 00:21:34) for one year data.
