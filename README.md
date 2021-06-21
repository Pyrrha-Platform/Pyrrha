[![License](https://img.shields.io/badge/License-Apache2-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0) [![Community](https://img.shields.io/badge/Join-Community-blue.svg)](https://developer.ibm.com/callforcode/solutions/projects/get-started/)

# ![Pyrrha](/img/prometeo.png?raw=true)

In the face of natural disasters, such as wildfires, Pyrrha (created by Prometeo) protects those who protect us - the firefighters. With our solution, we've developed a prototype sensor which sends environmental telemetry (temperature, humidity, and smoke concentration). This data is processed by a machine learning algorithm which is able to predict firefighter health, indicating if they are OK, soon to be in danger, or in danger. The goal is to track real-time status, and eventually use aggregated data to make suggestions that improve health outcomes in the long run.


## Original Prometeo Team
| Name | Title | Github | Slack |
| --- | --- | --- | --- |
| Josep Ràfolse | --- | --- | @joraco |
| Marco Emilio Rodriguez Serrano | --- | [Marco](https://github.com/mrodrise) | @Marco.rodriguez.serra |
| Salome Valero Cumplido | --- | [Salome](https://github.com/svaleroc) | @Salaome.valero |
| Joan Herrera | --- | --- | --- |
| Vicenç Ferrés | --- | --- | --- |

## IBM Call for Code Team
| Name | Title | Github | Slack |
| --- | --- | --- | --- |
| Daniel Krook | CTO | [Daniel](https://github.com/krook) | @@Krook |
| Upkar Lidder | Technical Lead | [Upkar](https://github.com/upkarlidder) | @Upkarlidder |
| Taeson Black | Tech. Solution Specialist Intern | [Tae](https://github.com/TaeBlack) | @Tae.black|
| Alejandro Quijada | Tech. Solution Specialist Intern | [Alejandro](https://github.com/Aquijada52) | @Alejandro.Quijada |

## Prometeo Platform S.L. Team
| Name | Title | Github | Slack |
| --- | --- | --- | --- |
| Marco Emilio Rodriguez Serrano | --- | [Marco](https://github.com/mrodrise) | @Marco.rodriguez.serra |
| Salome Valero Cumplido | --- | [Salome](https://github.com/svaleroc) | @Salaome.valero |
| Joan Herrera | --- | --- | --- |

## IBM Service Corps Team
| Name | Title | Github | Slack |
| --- | --- | --- | --- |
| ? | ? | ? | ? |

## Public Tools

* Will use [Slack in the Call for Code workspace](https://callforcode.org/slack) for chat in between meetings

## Pyrrha Platform v1 (By-Prometeo)

The first version of the Pyrrha project is nearing completion, and will soon be a Call for Code® with The Linux Foundation project. The project will carry on as a separate name distinct from the Prometeo trademark, Pyrrha, who is the daughter-in-law of Prometheus in Greek mythology.


## Pyrrha Projects
| Name | Git Repo |
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

## The Story 
Watch this video to understand the Pyrrha solution based on Prometeo Call for Code winning application:

[![Story-Video](https://user-images.githubusercontent.com/84807697/120705678-21671e80-c486-11eb-8e6c-888dc98fab23.png)](https://www.youtube.com/watch?v=vOgCOoy_Bx0)

## Built with:
*[IBM IoT Platform](https://www.ibm.com/cloud/internet-of-things)

*[MariaDB](https://mariadb.org/)

*[Express.js](https://expressjs.com/)

*[React.js](https://reactjs.org/)

*[Flask](https://palletsprojects.com/p/flask/)

*[Pandas](https://pandas.pydata.org/)

*[IBM App ID](https://www.ibm.com/cloud/app-id?lnk=STW_US_STESCH&lnk2=learn_CloudAppID&pexp=DEF&psrc=NONE&mhsrc=ibmsearch_a&mhq=app%20id%20ibm%20cloud)

*[IBM Cloud Kubernetes Service](https://www.ibm.com/cloud/kubernetes-service)


## Solution at a Glance : Architecture
![prometeo:pyrrha diagram](https://user-images.githubusercontent.com/3187457/122242264-08903d00-ce78-11eb-944f-804ba4dc683d.png)
1. The firefighter logs into the mobile phone. The credentials are authenticated with IBM App ID. The next steps assume that authentication was successful. Then the firefighter scan for Prometeo devices with the mobile app and connect to the device thought bluetooth low energy.
2. The device sensor captures gas levels. The device sends to the mobile application sensor values at regular intervals.
3. The mobile application sends data to the IBM IoT platform.
4. The MQTT Client service listens for incoming messages on the IBM IoT platform.
5. The MQTT Client stores the data in the MariaDB relational database.
6. The MQTT client sends the data to the WebSocket server.
7. The RulesDecision service wakes up every minute to calculate the 10 mins, 30 mins, 60 mins, 4 hours, and 8 hours time-weighted averages for each gas.
8. The dashboard queries the database to show the historical data.
9. The dashboard connects to the WebSocket Server to show live data and alerts the user if the levels go above certain pre-determined thresholds.
10. The central control can view the dashboard using the web browser.
11. The mobile application regularly requests firefighter status from the RulesDecision service and shows the result using the LED on the hardware device.

## Important Links
| Description | Link |
| --- | --- |
| Pyrrha Website| https://pyrrha-platform.org |


## License
This project is licensed under the Apache 2 License - see the [LICENSE](https://github.com/Pyrrha-Platform/Pyrrha/blob/main/LICENSE) file for details.
