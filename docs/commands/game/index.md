---
title: game
layout: default
parent: Lua-Commands
---

# game
```game.getCorporationTime()```
>get Session? time in ms

```game.environmentSetSnowDensity(Percent:float)```
>Sets the snow density in the ARCTIC (only) to int (0-1 with ',' instead of '.'). 0 is lowest but not gone...
everywhere else it just flickers snow for 1 gametick.

```game.environmentSetWindDir(Direction:int)```
>Changes wind direction to set direction 0 is NE 90 is NW etc.

```game.GUIManager.isUIStartUpPastSceneCreation()```
>returns a bool; with console probably always true
>from log: rdui::SendTelemetryMarker: UI-Flow: Startup Complete (A)
after that it always returns true, probably impossible to get a false with lua

```game.TextSourceManager.setDebugTextSource(EmbedString:string)```
> 