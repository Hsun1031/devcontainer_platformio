# Devcontainer for PlatformIO

This is a devcontainer for [PlatformIO](https://platformio.org/) with [Visual Studio Code](https://code.visualstudio.com/).

## devcontainer.json

Use `Dockerfile` as the build file for the devcontainer.

```json
{
    "name": "PlatformIO devcontainer",
	"build": {
        "dockerfile": "Dockerfile"
    }
    ...
}
```

Use `hsun1031/devcontainer_platformio` as the base image.

```json
{
    "name": "PlatformIO devcontainer",
	"image": "hsun1031/devcontainer_platformio:latest",
    ...
}
```

## How to use this devcontainer on GitHub Codespaces
Init platformio project. [board list](https://docs.platformio.org/en/latest/boards/index.html)

```bash
pio init --ide vscode --board <your board>
```

Login platformio account.

```bash
pio account login
```

[Remote MCU] Connect to the device.

```bash
pio remote agent start
``` 

[Codespace] List for remote devices.

```bash
pio remote device list
```

Flash and Monitor.

```bash
pio remote run --target upload --environment <your board>
pio remote device monitor 
```
## esp-web-flash-server

[Github](https://github.com/esp-rs/esp-web-flash-server)

### Command

```bash
web-flash --chip <Yor Chip> .pio/build/<Your ENV>/firmware.elf
```

example:

```bash
web-flash --chip esp32 .pio/build/esp32doit-devkit-v1/firmware.elf
```

