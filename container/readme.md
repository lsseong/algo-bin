To improve robustness of system, there are two main processes to run independently:
1. A container that runs a trading strategy (algo-container.jar)
2. A controller that provides events streaming endpoints to external client (algo-controller.jar)
These fat jars are built in Eclipse using Maven by right click on the project -> Run As -> Maven Install


> java -jar algo-container-1.0.0-SNAPSHOT.jar

 * This will start a default strategy called AlternateBuySellStrategy that do an alternate buy and sell of 1000k EUR/USD (see pom.xml)
 * Aeron streaming port is opened on 7000
 * Log to /temp/simulation/AlternateBuySellStrategy
 * REST points as follows:
 ** http://localhost:2222/service/strategy/performances
 ** http://localhost:2222/service/strategy/statuses

> java -jar algo-controller-1.0.0-SNAPSHOT.jar
 * This will start a controller process that caches all the events from container and expose an SSE stream
 * Stream URL is http://localhost:2020/service/<strategy_id>
 ** http://localhost:2020/service/AlterBuySell-EURUSD
 * REST points as follows (URL is same as container, just on different port):
 ** http://localhost:2020/service/strategy/statuses

> java -cp algo-container-1.0.0-SNAPSHOT.jar com.algo.demo.fxhedger.RunFxAutohedgerSimulation
