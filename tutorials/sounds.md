# Sounds

Adding (new) sounds to Anno 1800 via mods is a new feature with GameUpdate 18.2.

## Programs needed

Audio Kinetic https://www.audiokinetic.com/en/download/

Within AudioKinetic install WWise Version 2019.2.15.7667.

!> it has to be Version 2019.2.15.7667.

## Optional Programs

1. https://www.fosshub.com/TAudioConverter.html (has portable version)
2. https://audio.online-convert.com/convert-to-wav (max 3/batch)
3. https://www.audacityteam.org/
4. https://www.kabuusoft.com/product/detail/2/kabuu-audio-converter (untested)

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

## Asset.xml

The minimum changes to the asset are:

1. Adding the the new soundbank to the game [ref](/en/tutorials/sounds?id=soundbank)
2. Adding the new soundbank to the regions. [ref](/en/tutorials/sounds?id=soundbank)
3. Add the wwise-id of your sound to an existing audio template

### Soundbank

First you need your generated soundbank .json and .bnk and a [new guid](https://github.com/anno-mods/GuidRanges?tab=readme-ov-file#personal-guid-range).

The name of your soundbankfiles must be the same as the soundbankid. You can find the soundbankid in your generated .json file e.g.
```json
"SoundBanks": [
   {
    "Id": "2912941678",
```

<img  src="./img/name_soundbanks.png">

This id needs also to be put as the wwiseid in the soundbank. Minimal Soundbanktemplate (made by serp):

```xml
<ModOp Type="addNextSibling" GUID="235864">
<Asset>
    <Template>SoundBank</Template>
    <Values>
    <Standard>
        <GUID>2001000000</GUID><!--personal guid range-->
        <Name>BNK_VO_WC2</Name>
        <IconFilename>test_data/graphics/wwise_icons/soundbank.png</IconFilename>
    </Standard>
    <SoundBank>
        <SoundBankLocalized>1</SoundBankLocalized>
    </SoundBank>
    <WwiseStandard>
        <WwiseID>2912941678</WwiseID>
    </WwiseStandard>
    </Values>
</Asset>
</ModOp>
```

Thereafter we have to load the new soundbank to our designated regions.

```xml
<ModOp Type="add" GUID="5000001,5000000,160001,114327" Path="/Values/RequiredSoundBanks/SoundBanks">
<Item>
    <Bank>2001000000</Bank><!--personal guid range-->
</Item>
</ModOp>
<ModOp Type="add" GUID="133700001" Path="/Values/RequiredSoundBanks/SoundBanks" Condition="@133700001">
<Item>
    <Bank>2001000000</Bank><!--personal guid range-->
</Item>
</ModOp>
```

With this you have successfully added your new soundbank to all (current) regions and can play your sound anywhere in the game.

### WwiseID

To get the wwiseid of your sound, that you want to play, you have two options.

1. use [SoundsForAnno](/en/tutorials/sounds?id=SoundsForAnno) and look into the generated audio.xml
2. look into the generated .json soundbankfile. Therein your Event-ID is your wwiseid

```json
"IncludedEvents": [
     {
      "Id": "897965722",
      "Name": "Play_AsYouWish",
```

## Resources

https://github.com/anno-mods/modding-guide/blob/main/guides/Add%20Sounds.md