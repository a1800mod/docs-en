# Sounds

## WWise

https://www.youtube.com/watch?v=jIPWDSSsG2I

Create a new Project (name it as you like).
Add Actor-Mixer to Actor-Mixer-Hierarchy and name it "SFX Mixxer" for SFX, or "Voice Mixxer" for all non-SFX-sounds.
<img  src="./img/ActorMixer.png">
Import Sound file (.wav) to Mixer. Wave file must not be 8-bit our you will get an error. Convert it to higher bitrate.
<img  src="./img/import.png">
Add an Play-Event to the imported audio-file.
<img  src="./img/playevent.png">
Sync with game volume by adding game parameter. Name it "Menu_Volume_SFX" or "Menu_Volume_VO" or "Menu_Volume_Master. Change default to 100.
<img  src="./img/gameparameter.png">
Add parameter to SFX_Mixxer (Tab RTPC > Voice Volume)
<img  src="./img/rtpc.png">

### range

## SoundsForAnno

https://github.com/anno-mods/soundsforanno