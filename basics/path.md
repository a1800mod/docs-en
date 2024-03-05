# Mod folders

There are three folders, where the internal modbrowser of Anno 1800 will look for mods:
1. in the Anno 1800 installation folder <mark>\mods</mark>
2. <mark>%USERPROFILE%\Documents\Anno 1800\mods</mark>
3. <mark>%PUBLIC%\mod.io</mark>

The <mark>mod.io</mark> path can be switched by editing the <mark>globalsettings.json</mark> in <mark>%localappdata%\mod.io</mark>

> Default: <mark>{"RootLocalStoragePath":"C:/Users/Public/mod.io/"}</mark>

# Logs

There are two interesting log types:

1. mod-loader.log
2. Anno1800-....log

## mod-loader.log

This log contains information about logs and its status of loading.

>Path: %USERPROFILE%\Documents\Anno 1800\log

Info means the mod was successfully loaded.

> [date-time] [info] Load [Misc] InstantShipBuild (0.0.1, InstantShipBuild) from C:\Users\Public\mod.io\4169\mods\3595702\InstantShipBuild

Warning means the mod contains error in the programming, this may mean it contains wrong paths (e.g. wrong GUID), or contains stuff for unused other mods. A warning may indicate that a mod will not work as intented, it was loaded at least.

> [date-time] [warning] [Misc] Buildable Residences: No matching node for Path "//Asset[Values/Standard/GUID='112791']/Values/ConstructionCategory/BuildingList/Item[Building = '112685']" (data/config/export/main/asset/assets.xml:40)

Errors mean a mod was not loaded due to various reasons and needs to be checked.

!>[2024-02-29 19:32:11.229] [error] modinfo.json of [lonelyPorter] Building materials at Traders has errors

# Paths in a mod

the minimal structure of a mod is:
```
|───[modfolder]
│   └─data
│     └─config
│       └─export
│         └─main
│           └─asset
│             └─assets.xml
│   └─modinfo.json
```

## assets.xml

The assets.xml is the core for modding, it contains the <mark>\<ModOp></mark> with the information where and what to modify.

## modinfo.json

the modinfo.json contains basic information about the mod, like the versionnumber.
>a mod can be installed locally without a modinfo.json