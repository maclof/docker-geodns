# docker-geodns
A GeoDNS server written in Go, inside a Docker container.

## Quick Start

You can launch a GeoDNS container with the following command:

```bash
docker run -d --name=geodns -p 53:53/udp -v /dns:/dns maclof/geodns:latest
```

You should put the JSON zone files inside /dns, for example (/dns/maclof.com.json):

```bash
{
	"data": {
		"": {
			"ns": [
				"ns1.maclof.com",
				"ns2.maclof.com"
			],
			"a": [
				[
					"146.185.128.95"
				]
			]
		}
	}
}
```

You can find out more information about the GeoDNS server here: https://github.com/abh/geodns
