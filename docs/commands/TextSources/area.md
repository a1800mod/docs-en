---
title: Area
layout: home
parent: Textsources
grand_parent: Lua-Commands
---
## Area
```ts.Area.GetArea({SessionID=SID:int,AreaIndex=AID:int,IslandID=IID:int})```
>

```ts.Area.GetAreaFromID(ID:int16)```
> ID is the bitshifted integer of the SessionID, AreaIndex and IslandID combined. Returns the defined area as an object.

### CurrentSelectedArea (Current)
Effects the area your window is hovering over and displaying the Name of the Island.
```ts.Area.Current.CityName```
>Holds the current city name.

```ts.Area.Current.IsFireUnlocked```
>Boolean, gets if fires can take place, probably only relevant for OW where u can skip fires.

```ts.Area.Current.ID```
>Holds table with IslandID, AreaIndex, SessionID

```ts.Area.Current.KontorID```
>Hold table with AsyncObjectFlag, AreaID (see ID), EditorFlag, ObjectID, EditorChunkID

```ts.Area.Current.Economy.SetCheatItem(GUID:Int)```
>Adds the Item with _GUID_ to the island storage.

```ts.Area.Current.AddAmount(GUID:Int, Amount:Int)```
```ts.Area.Current.AddAmount(Amount:Int)```
>Adds (or substracts) either only the amount for the GUID or for every unlocked source to the island storage.

```ts.Area.Current.Economy.SetCheatChangeWorkforceNet(500:Boolean)```
>True -> adds 500 workforce (every tier)
>False -> substracts 500 workforce (every tier)

```ts.Area.Current.Economy.ClearIslandStorage()```
>Wipes all goods of current island...

## AreaManager
```ts.AreaManager.AreaFestival.SetTriggerFestival()```
>triggers random festival

```ts.AreaManager.AreaFestival.SetStopFestival()```
>stops current festival

```ts.AreaManager.AreaFestival.GetRemainingDurationEstimation()```
>returns the eta of the current running festival in ms

```ts.AreaManager.AreaFestival.SetIncreasePool(Duration:int)```
>increases or (if negative value) decreases the duration of the current festival. its not in ms, testing and calculating didnt bring results as how it is calculated, inserting a big number results in a long festival

## AreaPopulation
```ts.AreaPopulation.PopulationCount```
>gives the current Population

```ts.AreaPopulation.SetFillAllResidencesOnIsland()```
>fills all residences to maximum

## AreaResidenceConsumption
```ts.AreaResidenceConsuption.GetIsDistributionPaused(GUID: int, Population_GUID:int)```
>returns true if selected good is paused.