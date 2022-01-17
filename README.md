# Beat Saber Configs

This repo contains the configs I use for Beat Saber.

## Recording setup

I use OBS for recording, primarily to enable reviewing high-quality frame-by-frame gameplay. I use 3 input sources:

1. A browser source for my custom overlay https://github.com/chenxiaolong/beatsaber-overlay. This pulls data via BSDataPuller's websocket and displays the song information in the lower left corner of the recording. It's rendered at 1080p with a scale factor of 1.25.
2. A camera source with a Sony HDR-XR550V connected to an Elgato 4K60Pro Mk.2. The camera is captured at 1080p60Hz with the camera's OSD set to the device's screen only for a clean output.
3. Beat Saber itself.

All 3 inputs and the audio capture are timed to be (almost) frame perfect. I did this by first finding the most delayed source, which by far is SteamVR's audio mirroring. Using that as the basis, I set a render delay filter on the game capture. The delay was computed by recording a few seconds of Beat Saber's audio delay menu and then adjusting the render delay so that the progress bar's indicator hits the edges when there's a peak in the audio waveform.

The camera is then timed to the game by pointing the camera at the HMD lens, still in the audio delay menu. I just count the number of frames between the game capture and the camera capture using a fixed point on the progress bar as a frame of reference. While the latency of all the hardware I use is very consistent across recordings/restarts, the camera captures at 60Hz and it sometimes lines up with the odd-numbered 120fps-frames and other times, the even-numbered 120fps-frames. It's either frame-perfect or off by 1 frame.

I do not use a microphone, so that is not A/V synced at all.

OBS encoding settings:

* Output:
    * Recording:
        * Encoder: NVIDIA NVENC H.264 (new)
        * Rate control: VBR
        * Bitrate: 60Mbps
        * Max bitrate: 100Mbps
        * Keyframe interval: 2 seconds
        * Preset: Quality
        * Profile: High
        * Max b-frames: 0
    * Audio:
        * Audio bitrate: 320Kbps
* Audio:
    * Sample Rate: 48kHz
* Video:
    * Base/output resolution: 1920x1080
    * FPS: 120
* Advanced:
    * Renderer: Direct3D 11
    * Color format: NV12
    * Color space: 709
    * Color range: Full

## Controller settings

I use the Valve Index with the default grip with adjustment notch on the 2nd slot from the handle. My SaberTailor settings are [here](UserData/SaberTailor.json).

I prefer to play with the controllers being approximately in the middle row of notes in conserve stammina. Because I'm shorter than Beat Saber's reference height and the height settings appear to be logarithmic, I cannot sufficiently hit my preferred note height using the in-game height settings. I use OVR Advanced Settings to adjust the Y room offset a little bit. Unlike Beat Saber's built in room offset, this does not cause rendering issues with ScoreSaber replays.

## Colors

I use colors from the Catppuccin code editor theme: https://github.com/catppuccin/catppuccin

| Type                  | Preview     | RGB             |
|-----------------------|-------------|-----------------|
| Left saber            | ![green]    | `171, 233, 179` |
| Right saber           | ![blue]     | `150, 205, 251` |
| Primary environment   | ![lavender] | `201, 203, 255` |
| Secondary environment | ![peach]    | `248, 189, 150` |
| Walls                 | ![pink]     | `245, 194, 231` |

[green]: https://raw.githubusercontent.com/catppuccin/catppuccin/dev/assets/palette/circles/green.png
[blue]: https://raw.githubusercontent.com/catppuccin/catppuccin/dev/assets/palette/circles/blue.png
[lavender]: https://raw.githubusercontent.com/catppuccin/catppuccin/dev/assets/palette/circles/lavender.png
[peach]: https://raw.githubusercontent.com/catppuccin/catppuccin/dev/assets/palette/circles/peach.png
[pink]: https://raw.githubusercontent.com/catppuccin/catppuccin/dev/assets/palette/circles/pink.png

## Plugins

* Accuraseal (Not open source)
* [Beat-Saber-Utils](https://github.com/Kylemc1413/Beat-Saber-Utils)
* [BeatSaber-ParticleOverdrive](https://github.com/Shadnix-was-taken/BeatSaber-ParticleOverdrive)
* [BeatSaber-SaberTailor](https://github.com/Shadnix-was-taken/BeatSaber-SaberTailor)
* [BeatSaber_BetterSongList](https://github.com/kinsi55/BeatSaber_BetterSongList)
* [BeatSaber_BetterSongSearch](https://github.com/kinsi55/BeatSaber_BetterSongSearch)
* [BeatSaber_SongDetails](https://github.com/kinsi55/BeatSaber_SongDetails)
* [BeatSaber_Tweaks55](https://github.com/kinsi55/BeatSaber_Tweaks55)
* [BeatSaberMarkupLanguage](https://github.com/monkeymanboy/BeatSaberMarkupLanguage)
* [BeatSaverDownloader](https://github.com/Top-Cat/BeatSaverDownloader)
* [BeatSaverSharper](https://github.com/Auros/BeatSaverSharper)
* [BeatSaverVoting](https://github.com/Top-Cat/BeatSaverVoting)
* [BSIndexHapticFix](https://github.com/hardcpp/BSIndexHapticFix)
* [BSDataPuller](https://github.com/kOFReadie/BSDataPuller)
* [Chroma](https://github.com/Aeroluna/Chroma)
* [CountersPlus](https://github.com/Caeden117/CountersPlus)
* [CustomJSONData](https://github.com/Aeroluna/CustomJSONData)
* [CS_BeatSaber_Camera2](https://github.com/kinsi55/CS_BeatSaber_Camera2)
* [CS_BeatSaber_GottaGoFast](https://github.com/kinsi55/CS_BeatSaber_GottaGoFast)
* [DiTails](https://github.com/Auros/DiTails)
* [FC-Percentage](https://github.com/ChirpyMisha/FC-Percentage)
* [Heck](https://github.com/Aeroluna/Heck)
* [HitScoreVisualizer](https://github.com/ErisApps/HitScoreVisualizer)
* [HitSoundChanger](https://github.com/SamuelTulach/HitSoundChanger)
* [IForgor](https://github.com/ckosmic/IForgor)
* [JDFixer](https://github.com/zeph-yr/JDFixer)
* [MappingExtensions](https://github.com/Kylemc1413/MappingExtensions)
* [MorePlaylists](https://github.com/rithik-b/MorePlaylists)
* [MorePrecisePlayerHeight](https://github.com/ErisApps/MorePrecisePlayerHeight)
* [NoodleExtensions](https://github.com/Aeroluna/NoodleExtensions)
* [PlaylistManager](https://github.com/rithik-b/PlaylistManager)
* [PPCounter](https://github.com/PulseLane/PPCounter)
* [RankedPlaylist](https://github.com/qe201020335/RankedPlaylist)
* [SaberFactory](https://github.com/ToniMacaroni/SaberFactory)
* [ScorePercentage](https://github.com/Idlebawb/ScorePercentage)
* ScoreSaber (Not open source)
* [SearchByCharacters](https://github.com/Kuurama/SearchByCharacters)
* [SiraUtil](https://github.com/Auros/SiraUtil)
* [SliceDetails](https://github.com/ckosmic/SliceDetails)
* [SongCore](https://github.com/Kylemc1413/SongCore)
* [SongPlayHistoryContinued](https://github.com/Shadnix-was-taken/BeatSaber-SongPlayHistoryContinued)
* [TakeMeToResults](https://github.com/rithik-b/TakeMeToResults)
* [Time-Dependence-Counter](https://github.com/PulseLane/Time-Dependence-Counter)

Not yet compatible with 1.19.0:

* [BeatSaviorData](https://github.com/Mystogan98/BeatSaviorData)
* [BeatSaber-SliceVisualizer](https://github.com/m1el/BeatSaber-SliceVisualizer)
* [BeatSaber_ControllerSettingsHelper](https://github.com/kinsi55/BeatSaber_ControllerSettingsHelper)
