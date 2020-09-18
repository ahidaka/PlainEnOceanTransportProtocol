# PlainEnOceanTransportProtocol

Plain EnOcean Transport Protocol (PETP) is a plain, simple and easy protocol to transport EnOcean telegrams on TCP.

This protocol was inspired by EnOcean over IP protocol.
EnOcean Over IP is a very good and smart protocol for all gateways and services, and or all purpose.
But this protocol is complex and needs many resource and workload.
This proposes simple and easy way for small gateways, equipments, and services.

### cf. EnOcean over IP
- EnOcean over IP Specification v1.0 (PDF)<br/>
https://www.enocean-alliance.org/ip/

- EnOcean over IP Specification Introduction v0.91 (PDF)
https://www.enocean-alliance.org/ip/introduction/

<br/>

## How to transfer

It is usually intended to use Berkeley sockets over TCP / IP for unidirectional or bidirectional communication.

The send / receive port is arbitrary. It is also possible to use UDP, MQTT, AMQP and secure methods implemented on TSL.

<br/>

## Sample format for Data Telegram

```json
{
	"dataTelegram" : {
		"deviceId" : "01234567",
		"friendlyId" : "EnOceanTemperature",
		"timestamp" : "2016-05-09 12:57:08",
		"direction" : "from",
		"security" : "1",
		"profile" : "A5-02-01",
		"functions" : [
			{
				"key" : "TP",
				"value" : 25.10,
				"unit" : "°C"
			},
			{
				"key" : "HU",
				"value" : 25.10,
				"unit" : "%"
			}
		],
		"telegramInfo" : {
			"data" : "00005F08",
			"status" : "0",
			"dbm" : -80,
			"rorg" : "A5"
		}
	}
}
```

<br/>

## Sample format for Teach-In Telegram

```json
{
	"teachInTelegram" : {
		"deviceId" : "01234567",
		"friendlyId" : "EnOceanTemperature",
		"timestamp" : "2016-05-09 12:57:08",
		"direction" : "from",
		"security" : "1",
		"profile" : "A5-02-01",
		"manId" : "00B",
		"telegramInfo" : {
			"data" : "00005F08",
			"status" : "0",
			"dbm" : -80,
			"rorg" : "62"
		}
	}
}
```

<br/>
