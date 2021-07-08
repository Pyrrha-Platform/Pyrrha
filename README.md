[![License](https://img.shields.io/badge/License-Apache2-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0) [![Community](https://img.shields.io/badge/Join-Community-blue.svg)](https://developer.ibm.com/callforcode/solutions/projects/get-started/)

Created by the [Prometeo Solutions S.L.](https://prometeoplatform.com/) team as a [Call for Code winning project](https://developer.ibm.com/callforcode/solutions/prometeo/), the *Pyrrha open source project* is built to protect the firefighters who protect us from the threat of wildfires and bushfires. 

We've developed a prototype sensor which collects environmental telemetry (carbon monoxide, nitrogen dioxide, temperature, and humidity readings). This data is then processed by a machine learning algorithm which is able to assess firefighter status, indicating if they are OK now or at risk from prolonged exposure.

Pyrrha tracks real-time status and use captures long-term averages to make suggestions that can improve health outcomes in the long run.

## Get started
- [Get started](#get-started)
- [Pyrrha v1 (Prometeo v4)](#pyrrha-v1-prometeo-v4)
- [Pyrrha Projects](#pyrrha-projects)
- [The Story](#the-story)
- [Built with:](#built-with)
- [Get Involved](#get-involved)
- [Solution at a Glance : Architecture](#solution-at-a-glance--architecture)
- [Important Links](#important-links)
- [Original Prometeo Team](#original-prometeo-team)
- [IBM Call for Code Team](#ibm-call-for-code-team)
- [Prometeo Platform S.L. Team](#prometeo-platform-sl-team)
- [IBM Service Corps Team](#ibm-service-corps-team)
- [Public Tools](#public-tools)
- [License](#license)


## Pyrrha v1 (Prometeo v4)

The first version of the Pyrrha project is nearing completion, and will soon be released as a Call for Code® with The Linux Foundation project. The project will carry on as a separate name distinct from the Prometeo Solutions trademark - Pyrrha - the [flame-colored haired daughter-in-law of Prometheus in Greek mythology](https://www.greekmythology.com/Myths/Mortals/Pyrrha/pyrrha.html).


## Pyrrha Projects
| Name | Repository |
| --- | --- |
| Pyrrha | [Pyrrha](https://github.com/Call-for-Code/Pyrrha-Platform/Pyrrha) |
| Pyrrha-Firmware| [Firmware](https://github.com/Pyrrha-Platform/Pyrrha-Firmware) |
| Pyrrha-Dashboard | [Dashboard](https://github.com/Pyrrha-Platform/Pyrrha-Dashboard) |
| Pyrrha-Database | [Database](https://github.com/Pyrrha-Platform/Pyrrha-Database) |
| Pyrrha-Rules-Decision | [Rules-Decision](https://github.com/Pyrrha-Platform/Pyrrha-Rules-Decision) |
| Pyrrha-Watch-App | [Watch-App](https://github.com/Pyrrha-Platform/Pyrrha-Watch-App) |
| Pyrrha-Mobile-App | [Mobile-App](https://github.com/Pyrrha-Platform/Pyrrha-Mobile-App) |
| Pyrrha-Websocket-Server | [WebSocket-Server](https://github.com/Pyrrha-Platform/Pyrrha-WebSocket-Server) |
| Pyrrha-MQTT-Client | [MQTT-Client](https://github.com/Pyrrha-Platform/Pyrrha-MQTT-Client) |
| Pyrrha-Sensor-Simulator | [Sensor-Simulator](https://github.com/Pyrrha-Platform/Pyrrha-Sensor-Simulator) |
| Pyrrha-Website | [Website](https://github.com/Pyrrha-Platform/Pyrrha-Website) |


## The Story 
Watch this video to understand the Pyrrha solution based on Prometeo's original Call for Code 2019 winning application:

[![Story-Video](https://user-images.githubusercontent.com/84807697/120705678-21671e80-c486-11eb-8e6c-888dc98fab23.png)](https://www.youtube.com/watch?v=vOgCOoy_Bx0)


## Get Involved
Please read [GET_INVOLVED.md](GET_INVOLVED.md) to understand how you can contribute to the Pyrrha Project.

## Built with:
- [IBM IoT Platform](https://www.ibm.com/cloud/internet-of-things)
- [MariaDB](https://mariadb.org/)
- [Express.js](https://expressjs.com/)
- [React.js](https://reactjs.org/)
- [Flask](https://palletsprojects.com/p/flask/)
- [Pandas](https://pandas.pydata.org/)
- [IBM App ID](https://www.ibm.com/cloud/app-id?lnk=STW_US_STESCH&lnk2=learn_CloudAppID&pexp=DEF&psrc=NONE&mhsrc=ibmsearch_a&mhq=app%20id%20ibm%20cloud)
- [IBM Cloud Kubernetes Service](https://www.ibm.com/cloud/kubernetes-service)


## Solution at a Glance : Architecture
![prometeo:pyrrha diagram](https://user-images.githubusercontent.com/3187457/122242264-08903d00-ce78-11eb-944f-804ba4dc683d.png)
1. The firefighter logs into the mobile phone. The credentials are authenticated with IBM App ID. They scan for sensor devices with the mobile app and connect to the device thought Bluetooth Low Energy.
2. The device sensor captures toxin and environmental readings. The device sends to the mobile application sensor values at regular intervals (about once a minute).
3. The mobile application sends data to the IBM IoT platform.
4. The MQTT client service listens for incoming messages on the IBM IoT platform.
5. The MQTT client stores the data in the MariaDB database.
6. The MQTT client sends the data to the WebSocket server.
7. The Rules Decision service wakes up every minute to calculate the 10 min, 30 min, 60 min, 4 hour, and 8 hour time-weighted averages for each gas.
8. The dashboard queries the database to show the historical data.
9. The dashboard connects to the WebSocket server to show live data and alerts the user if the levels go above certain pre-determined thresholds.
10. The command center can view the dashboard using the web browser on a laptop or tablet in the field or at headquarters.
11. The mobile application regularly polls firefighter status from the Rules Decision service and shows the result using the LED on the hardware device.


## Important Links
| Description | Link |
| --- | --- |
| Pyrrha Website| https://pyrrha-platform.org |


## Original Prometeo Team
| Name | Title | GitHub | Slack |
| --- | --- | --- | --- |
| Josep Ràfols | --- | --- | @joraco |
| Marco Emilio Rodriguez Serrano | --- | [Marco](https://github.com/mrodrise) | @marco.rodriguez.serra |
| Salome Valero Cumplido | --- | [Salome](https://github.com/svaleroc) | @salome.valero |
| Joan Herrera | --- | --- | --- |
| Vicenç Ferrés | --- | --- | --- |


## IBM Call for Code Team
| Name | Title | GitHub | Slack |
| --- | --- | --- | --- |
| Daniel Krook | CTO | [Daniel](https://github.com/krook) | @krook |
| Upkar Lidder | Technical Lead | [Upkar](https://github.com/upkarlidder) | @upkarlidder |
| Taeson Black | Tech. Solution Specialist Intern | [Tae](https://github.com/TaeBlack) | @tae.black|
| Alejandro Quijada | Tech. Solution Specialist Intern | [Alejandro](https://github.com/Aquijada52) | @alejandro.quijada |


## Prometeo Platform S.L. Team
| Name | Title | Github | Slack |
| --- | --- | --- | --- |
| Marco Emilio Rodriguez Serrano | --- | [Marco](https://github.com/mrodrise) | @marco.rodriguez.serra |
| Salome Valero Cumplido | --- | [Salome](https://github.com/svaleroc) | @salome.valero |
| Joan Herrera | --- | --- | --- |


## IBM Service Corps Team
| Name |
| --- |
| Brandi Boatner |
| Dina Tawil |
| George Zacharakis-Jutz |
| John Segrave-Daly |
| Laura J Mokrzycki |
| Laura Visochek |
| Marisol Elizabeth Santillan |
| Nithya Renganathan |
| Samantha Davis |
| Upkar Lidder |
| Vince Siu |


## Public Tools

* We use [Slack in the Call for Code workspace](https://callforcode.org/slack) #prometeo-pyrrha channel for discussion.


## License
This project is licensed under the Apache 2 License - see the [LICENSE](https://github.com/Pyrrha-Platform/Pyrrha/blob/main/LICENSE) file for details.
