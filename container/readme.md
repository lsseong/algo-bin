
> java -jar algo-container-1.0.0-SNAPSHOT.jar

 * This will start a default strategy called AlternateBuySellStrategy that do an alternate buy and sell of 1000k EUR/USD (see pom.xml)
 * Aeron streaming port is opened on 7000
 * Log to /temp/simulation/AlternateBuySellStrategy
 * REST points as follows:
 ** http://localhost:2222/service/strategy/performances
 ** http://localhost:2222/service/strategy/statuses

> java -jar algo-controller-1.0.0-SNAPSHOT.jar
 * 

  http://localhost:2222/service/strategy/statuses
  Streaming URL: http://localhost:2222/service/AlternateBuySell-EURUSD 

> java -cp algo-container-0.0.1-SNAPSHOT.jar com.algo.demo.cookbook.RunTwoBuySellStrategies

  http://localhost:2222/service/strategy/statuses
  Streaming URL: http://localhost:2222/service/AlternateBuySell-EURUSD
  Streaming URL: http://localhost:2222/service/AlternateBuySell-IBM
 
> java -cp algo-container-0.0.1-SNAPSHOT.jar com.algo.demo.fxhedger.RunFxAutohedgerSimulation
