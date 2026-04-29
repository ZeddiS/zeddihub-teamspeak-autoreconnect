# AutoReconnect

TS3 plugin: auto-reconnect to server after unexpected disconnects with exponential backoff.

Part of the [ZeddiHub TeamSpeak Addons](https://github.com/ZeddiS/zeddihub-teamspeak-addons) collection.
Built with C++17 + Qt 5.12.12. Multi-API support (23 / 24 / 25 / 26).

## Stazeni

Vyber zip podle sve TS3 verze v [Releases](../../releases):

| TS3 client | API | Stahni |
|---|---|---|
| 3.5.0 | 23 | `AutoReconnect-v1.1.0-TS3-3.5.0-api23.zip` |
| 3.5.1 - 3.5.5 | 24 | `AutoReconnect-v1.1.0-TS3-3.5.1-3.5.5-api24.zip` |
| **3.5.6** | 25 | `AutoReconnect-v1.1.0-TS3-3.5.6-api25.zip` |
| 3.6.x+ | 26 | `AutoReconnect-v1.1.0-TS3-3.6+-api26.zip` |

## Instalace

1. Rozbal zip
2. Zkopiruj DLL do `%APPDATA%\TS3Client\plugins\`
3. V TS3 -> Settings -> Plugins -> Reload All -> zaskrtni Enabled

## Build ze zdrojaku

```powershell
# Setup (once)
py -m pip install aqtinstall
py -m aqt install-qt windows desktop 5.12.12 win64_msvc2017_64 -O C:\Qt --archives qtbase
git clone https://github.com/TeamSpeak-Systems/ts3client-pluginsdk.git ts3sdk_clone
Move-Item ts3sdk_clone/include ts3sdk/include

# Build
cmake -S . -B build_api25 -G "Visual Studio 17 2022" -A x64 `
      -DCMAKE_PREFIX_PATH="C:\Qt\5.12.12\msvc2017_64"
cmake --build build_api25 --config Release
```

## License

MIT.

---

zeddis.xyz | (C) 2026 ZeddiHub.eu | https://zeddihub.eu
