---
title: session
layout: home
parent: Lua-Commands
---
# session
```session.toggleResidentView()```
>goes into first Person mode to current selected Building

```session.killGameObject()```
forces ruins to current selected Object (Player or NPC) or destroys ship. Does not Work on stuff like Emperor Ketemas buildings.

```session.getSessionGUID()```
>returns... a number
```session.forceWeather(Weather:string)```
>forces the weather of the current session to Weather
> Possible values:
> - "Snow"
> - "Rain"
> - "Apocalyptic"
> - "Default"