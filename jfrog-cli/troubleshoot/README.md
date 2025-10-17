# Troubleshooting

## Ping the default server

```bash
jf rt ping
```

## Ping a specific server by ID

Pings the configured Artifactory server with the ID rt-server-1.

```bash
jf rt ping --server-id=rt-server-1
```

## Ping a specific server by URL

Pings the Artifactory server accessible at the specified URL.

```bash
jf rt ping --url=https://my-rt-server.com/artifactory
```
