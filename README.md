<p align="center"><a href="README.en.md">English</a> · <a href="README.ru.md">Русский</a> · <a href="README.md">Original README</a></p>

<p align="center"><b>PUBLIC PROJECT · ПУБЛИЧНЫЙ ПРОЕКТ</b><br>
<a href="https://github.com/svllvsxprod/librertc-core">Original repository / Оригинальный репозиторий ↗</a> · <a href="https://github.com/svllvsx">Portfolio / Портфолио</a></p>

> **RTC tunneling runtime.** Движок RTC-туннелей.
> This is a README showcase. Source code, releases and development instructions belong to the original repository.
> Это README-витрина. Исходники, релизы и команды разработки относятся к оригинальному репозиторию.

---

# LibreRTC Core

LibreRTC Core is the runtime engine used by LibreRTC Node. It provides the `olcrtc` command-line binary that opens WebRTC-based server and client tunnels over supported carriers and transports.

This repository is published as a standalone LibreRTC project. The command name and URI scheme remain `olcrtc` for protocol compatibility with existing clients and generated subscriptions.

## Status

Early server-side runtime integration for LibreRTC.

## Build

Build the Linux amd64 runtime binary:

```sh
CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -trimpath -ldflags="-s -w" -o build/olcrtc-linux-amd64 ./cmd/olcrtc
```

Run tests:

```sh
go test ./...
```

Build the Docker image:

```sh
docker build -t librertc-core:local .
```

## Runtime Data

The runtime expects carrier data files from `data/`. The Docker image copies these files into `/usr/share/olcrtc`.

## Integration

LibreRTC Node currently embeds this runtime binary into its Docker image. Keep the binary name `olcrtc` unless all consumers are updated together.

## License

MIT

