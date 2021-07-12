# trv-vtex-proxy


Download

- [Linux](https://github.com/Trivod/trv-vtex-proxy/raw/master/bin/TrivodProxy-linux)
- [MacOS](https://github.com/Trivod/trv-vtex-proxy/raw/master/bin/TrivodProxy-macos)
- [Windows](https://github.com/Trivod/trv-vtex-proxy/raw/master/bin/TrivodProxy-win.exe)

## Cli params
```
-f   => File with config
-p   => Port for HTTPS server
```

## Config example

config.json

```json
{
    "vtex": {
        "store": "vtex-store-name-id",
      }
}
```


## Example

```shell
./TrivodProxy-macos -f ./config.json -p 443
```