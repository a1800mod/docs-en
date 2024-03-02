# Mod folders

There are three folders, where the internal modbrowser of Anno 1800 will look for mods:
1. in the Anno 1800 installation folder <mark>\mods</mark>
2. <mark>%USERPROFILE%\Documents\Anno 1800\mods</mark>
3. <mark>%PUBLIC%\mod.io</mark>

The <mark>mod.io</mark> path can be switched by editing the <mark>globalsettings.json</mark> in <mark>%localappdata%\mod.io</mark>

> Default: <mark>{"RootLocalStoragePath":"C:/Users/Public/mod.io/"}</mark>

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