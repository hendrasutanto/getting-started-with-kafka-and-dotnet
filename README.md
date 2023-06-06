# getting-started-with-kafka-and-dotnet
Getting Started with Apache Kafka and .NET

## **Clone this repository**
```bash
git clone https://github.com/hendrasutanto/getting-started-with-kafka-and-dotnet.git
```

## **Create a topic in Kafka**
Create a new topic, <code>purchases</code>, which we will use to produce and consume events.

## **Configuration**
When using Confluent Cloud you will be required to provide an API key and secret authorizing your application to produce and consume. You can use the Confluent Cloud Console to create a key for you by navigating to the <code>API Keys</code> section under <code>Cluster Overview</code>.

Copy and paste the following configuration data into a file named <code>getting-started.properties</code>, substituting the API key and secret that you just created for the <code>sasl.username</code> and <code>sasl.password</code> values, respectively.

Example:
```bash
bootstrap.servers=pkc-ldvr1.asia-southeast1.gcp.confluent.cloud:9092
security.protocol=SASL_SSL
sasl.mechanisms=PLAIN
sasl.username=SHAVECLYYCVX54PA
sasl.password=8UxP3/gEOCkeQcaxEn3sPbnXdTI70oM+VfBWMp2TsCvBhdIp4EdHz5UVid1G8mbF
debug=all
```

## **Build Producer**
In the <code>producer</code> directory, compile the producer with:
```bash
cd producer
dotnet build producer.csproj
```

## **Build Consumer**
In the <code>consumer</code> directory, compile the consumer with:
```bash
cd consumer
dotnet build consumer.csproj
```

## **Produce Events**
In order to run the producer, use the <code>dotnet run</code> command passing in the configuration file created above:
```bash
cd producer
dotnet run $(pwd)/../getting-started.properties
```

## **Consume Events**
In order to run the consumer, use the <code>dotnet run</code> command passing in the configuration file created above:
```bash
cd consumer
dotnet run $(pwd)/../getting-started.properties
```
Once you are done with the consumer, press <code>ctrl-c</code> to terminate the consumer application.
