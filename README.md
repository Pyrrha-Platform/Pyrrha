# Pyrrha

[![License](https://img.shields.io/badge/License-Apache2-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0) [![Slack](https://img.shields.io/static/v1?label=Slack&message=%23prometeo-pyrrha&color=blue)](https://callforcode.org/slack)

Created by the [Prometeo Solutions S.L.](https://prometeoplatform.com/) team as a [Call for Code winning project](https://developer.ibm.com/callforcode/solutions/prometeo/), the _Pyrrha open source project_ is built to protect the firefighters who protect us from the threat of wildfires and bushfires.

We've developed a prototype sensor which collects environmental telemetry (carbon monoxide, nitrogen dioxide, temperature, and humidity readings). This data is then processed by a machine learning algorithm which is able to assess firefighter status, indicating if they are OK now or at risk from prolonged exposure.

Pyrrha tracks real-time status and use captures long-term averages to make suggestions that can improve health outcomes in the long run.

## Get started

- [Get Started](#get-started)
- [Pyrrha v1 (Prometeo v4)](#pyrrha-v1-prometeo-v4)
- [Pyrrha Projects](#pyrrha-projects)
- [The Story](#the-story)
- [Built With](#built-with)
- [Get Involved](#get-involved)
- [Solution at a Glance](#solution-at-a-glance)
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

| Name                             | Repository                                                                      |
| -------------------------------- | ------------------------------------------------------------------------------- |
| Pyrrha                           | [Pyrrha](https://github.com/Call-for-Code/Pyrrha-Platform/Pyrrha)               |
| Pyrrha-Dashboard                 | [Dashboard](https://github.com/Pyrrha-Platform/Pyrrha-Dashboard)                |
| Pyrrha-Database                  | [Database](https://github.com/Pyrrha-Platform/Pyrrha-Database)                  |
| Pyrrha-Deployment-Configurations | [Deployment-Configurations](https://github.com/Pyrrha-Platform/Pyrrha-Deployment-Configurations) |
| Pyrrha-Firmware                  | [Firmware](https://github.com/Pyrrha-Platform/Pyrrha-Firmware)                  |
| Pyrrha-Hardware                  | [Hardware](https://github.com/Pyrrha-Platform/Pyrrha-Hardware)                  |
| Pyrrha-Mobile-App                | [Mobile-App](https://github.com/Pyrrha-Platform/Pyrrha-Mobile-App)              |
| Pyrrha-MQTT-Client               | [MQTT-Client](https://github.com/Pyrrha-Platform/Pyrrha-MQTT-Client)            |
| Pyrrha-Rules-Decision            | [Rules-Decision](https://github.com/Pyrrha-Platform/Pyrrha-Rules-Decision)      |
| Pyrrha-Sensor-Simulator          | [Sensor-Simulator](https://github.com/Pyrrha-Platform/Pyrrha-Sensor-Simulator)  |
| Pyrrha-Watch-App                 | [Watch-App](https://github.com/Pyrrha-Platform/Pyrrha-Watch-App)                |
| Pyrrha-Website                   | [Website](https://github.com/Pyrrha-Platform/Pyrrha-Website)                  |
| Pyrrha-Websocket-Server          | [WebSocket-Server](https://github.com/Pyrrha-Platform/Pyrrha-WebSocket-Server)  |

## The Story

Watch this video to learn about the Pyrrha solution based on Prometeo's original Call for Code 2019 winning application:

[![Story-Video](https://user-images.githubusercontent.com/84807697/120705678-21671e80-c486-11eb-8e6c-888dc98fab23.png)](https://www.youtube.com/watch?v=vOgCOoy_Bx0)

## Get Involved

Please read [GET_INVOLVED.md](GET_INVOLVED.md) to understand how you can contribute to the Pyrrha Project.

## Built With

- [IBM IoT Platform](https://www.ibm.com/cloud/internet-of-things)
- [MariaDB](https://mariadb.org/)
- [Express.js](https://expressjs.com/)
- [React.js](https://reactjs.org/)
- [Flask](https://palletsprojects.com/p/flask/)
- [Pandas](https://pandas.pydata.org/)
- [IBM App ID](https://www.ibm.com/cloud/app-id?lnk=STW_US_STESCH&lnk2=learn_CloudAppID&pexp=DEF&psrc=NONE&mhsrc=ibmsearch_a&mhq=app%20id%20ibm%20cloud)
- [IBM Cloud Kubernetes Service](https://www.ibm.com/cloud/kubernetes-service)

## Solution at a Glance

![prometeo:pyrrha diagram](https://user-images.githubusercontent.com/3187457/122242264-08903d00-ce78-11eb-944f-804ba4dc683d.png)

1. The firefighter logs into the ruggedized Samsung smartphone via IBM App ID. Devices are paired through Bluetooth.
2. The device sensors capture toxin levels. The device sends stored readings to the phone at regular intervals.
3. The mobile application relays data to the IBM IoT platform.
4. The MQTT client service listens for incoming messages from the IBM IoT platform.
5. The MQTT client stores the data in the MariaDB relational database.
6. The MQTT client sends the data to the WebSocket server.
7. The Rules-Decision service wakes up every minute to calculate the 10 mins, 30 mins, 60 mins, 4 hours, and 8 hours time-weighted averages for each gas.
8. The dashboard queries the database to show the historical data.
9. The dashboard connects to the WebSocket Server to show live data and alerts the user if the levels go above certain pre-determined thresholds.
10. The command center can view the dashboard using the web browser on a laptop or tablet.
11. The mobile application regularly requests status from the Rules-Decision service and emits the result via device LED and Samsung phone/watch vibrations.

## Important Links

| Description    | Link                        |
| -------------- | --------------------------- |
| Pyrrha Website | https://pyrrha-platform.org |

## Original Prometeo Team

| Name                           | GitHub                                | Slack                  |
| ------------------------------ | ------------------------------------- | ---------------------- |
| Josep Ràfols                   | ---                                   | @joraco                |
| Marco Emilio Rodriguez Serrano | [Marco](https://github.com/mrodrise)  | @marco.rodriguez.serra |
| Salome Valero Cumplido         | [Salome](https://github.com/svaleroc) | @salome.valero         |
| Joan Herrera                   | ---                                   | ---                    |
| Vicenç Ferrés                  | ---                                   | ---                    |

## Prometeo Platform S.L. Team

| Name                           | Title | Github                                | Slack                  |
| ------------------------------ | ----- | ------------------------------------- | ---------------------- |
| Salome Valero Cumplido         | CEO   | [Salome](https://github.com/svaleroc) | @salome.valero         |
| Marco Emilio Rodriguez Serrano | CTO   | [Marco](https://github.com/mrodrise)  | @marco.rodriguez.serra |
| Joan Herrera                   | COO   | ---                                   | ---   

## IBM Call for Code Team

| Name              | Title                            | GitHub                                     | Slack              |
| ----------------- | -------------------------------- | ------------------------------------------ | ------------------ |
| Daniel Krook      | CTO                              | [Daniel](https://github.com/krook)         | @krook             |
| Upkar Lidder      | Technical Lead                   | [Upkar](https://github.com/upkarlidder)    | @upkarlidder       |
| Taeson Black      | Tech. Solution Specialist Intern | [Tae](https://github.com/TaeBlack)         | @tae.black         |
| Alejandro Quijada | Tech. Solution Specialist Intern | [Alejandro](https://github.com/Aquijada52) | @alejandro.quijada |

                 |

## IBM Service Corps Team

| Name                        |
| --------------------------- |
| Brandi Boatner              |
| Dina Tawil                  |
| George Zacharakis-Jutz      |
| John Segrave-Daly           |
| Laura J Mokrzycki           |
| Laura Visochek              |
| Marisol Elizabeth Santillan |
| Nithya Renganathan          |
| Samantha Davis              |
| Upkar Lidder                |
| Vince Siu                   |

## Public Tools

- We use [Slack in the Call for Code workspace](https://callforcode.org/slack) #prometeo-pyrrha channel for discussion.

## License

This project is licensed under the Apache 2 License - see the [LICENSE](https://github.com/Pyrrha-Platform/Pyrrha/blob/main/LICENSE) file for details.
