# Sounds

Adding (new) sounds to Anno 1800 via mods is a new feature with GameUpdate 18.2.

## Programs needed

Audio Kinetic https://www.audiokinetic.com/en/download/

Within AudioKinetic install WWise Version 2019.2.15.7667.

!> it has to be Version 2019.2.15.7667.

## Optional Programs

https://audio.online-convert.com/convert-to-wav
Audacity https://www.audacityteam.org/

## WWise

Quick Tutorial https://www.youtube.com/watch?v=jIPWDSSsG2I

### Init Setup

Create a new Project (name it as you like).
Add Actor-Mixer to Actor-Mixer-Hierarchy and name it "SFX Mixxer" for SFX, or "Voice Mixxer" for all non-SFX-sounds.

<img  src="./img/ActorMixer.png">

Import sound file (.wav) to Mixer. Wave file must not be 8-bit our you will get an error. Convert it to higher bitrate.

<img  src="./img/import.png">

Add an Play-Event to the imported audio-file.

<img  src="./img/playevent.png">

Sync with game volume by adding game parameter. Name it "Menu_Volume_SFX" or "Menu_Volume_VO" or "Menu_Volume_Master. Change default to 100.

<img  src="./img/gameparameter.png">

Add parameter to Mixxer (Tab RTPC > Voice Volume)

<img  src="./img/rtpc.png">

Add work Unit to Soundbanks, name it as you like.

<img  src="./img/soundbankworker.png">

In SoundBankManager (switch Layout [Designer F5/SoundBankManager F7]) drag&drop Event-Default Work Unit to Hierarchy Inclusion.

<img  src="./img/hierarchy.png">

### Adding Languages

<img  src="./img/language.png">

<img  src="./img/language_2.png">

Currently known values:

1. en_us (default)
2. de_de
3. fr_fr

Anno 1800 can only use 4 audiolanguages. Adding Ru to the list above.

### Adding Range to audio

## SoundsForAnno

This tool reads the given (created by wwise) files to xml.

https://github.com/anno-mods/soundsforanno

PS C:\Users\Client\Documents\WwiseProjects\serp66> C:\Users\Client\Downloads\SoundsForAnno\SoundsForAnno.exe -f .\en_us\2254188251.json .\de_de\2254188251.json -g 1500001900 -a -s .\de_de\2254188251.bnk .\en_us\2254188251.bnk

## Resources

https://github.com/anno-mods/modding-guide/blob/main/guides/Add%20Sounds.md