# Keyboard and Mouse Controls for Mpv Media Player

## Seek Controls
- **LEFT and RIGHT**: Seek backward/forward 5 seconds.  
  `Shift + LEFT/RIGHT`: Exact seek backward/forward 1 second.
- **UP and DOWN**: Seek forward/backward 1 minute.  
  `Shift + UP/DOWN`: Exact seek forward/backward 5 seconds.
- **Ctrl + LEFT/RIGHT**: Seek to the previous/next subtitle (may have restrictions).
- **Ctrl + Shift + LEFT/RIGHT**: Adjust subtitle delay to sync subtitles to audio.
- **PGUP and PGDWN**: Seek to the beginning of the previous/next chapter.  
  `Shift + PGUP/PGDWN`: Seek backward/forward 10 minutes.

## Playback Speed Controls
- **[ and ]**: Decrease/increase playback speed by 10%.
- **{ and }**: Halve/double playback speed.
- **BACKSPACE**: Reset playback speed to normal.
- **Shift + BACKSPACE**: Undo the last seek (if the playlist entry hasn’t changed).
- **Shift + Ctrl + BACKSPACE**: Mark the current position for later revert.

## Playlist Navigation
- **< and >**: Go backward/forward in the playlist.
- **ENTER**: Go forward in the playlist.

## Playback Controls
- **p / SPACE**: Pause (pressing again unpauses).
- **.**: Step forward (frame-by-frame).
- **,**: Step backward (frame-by-frame).
- **q**: Stop playing and quit.
- **Q**: Stop playing, quit, and store the current playback position for later resume.

## Volume Controls
- **/ and ***: Decrease/increase volume.
- **9 and 0**: Decrease/increase volume.
- **m**: Mute sound.

## Track Selection
- **_**: Cycle through available video tracks.
- **#**: Cycle through available audio tracks.
- **j and J**: Cycle through available subtitles.

## Subtitle Controls
- **v**: Toggle subtitle visibility.
- **z and Z**: Adjust subtitle delay by +/- 0.1 seconds.
- **r and R**: Move subtitles up/down.
- **u**: Toggle SSA/ASS subtitle style overrides.
- **V**: Toggle subtitle VSFilter aspect compatibility mode.

## Screenshot Controls
- **s**: Take a screenshot.
- **S**: Take a screenshot without subtitles.
- **Ctrl + s**: Take a screenshot as the window shows it (with subtitles, OSD, and scaled video).

## Video Controls
- **f**: Toggle fullscreen.
- **ESC**: Exit fullscreen mode.
- **T**: Toggle stay-on-top.
- **w and W**: Decrease/increase pan-and-scan range.
- **A**: Cycle aspect ratio override.
- **d**: Activate/deactivate deinterlacer.
- **Ctrl + h**: Toggle hardware video decoding.

## Pan and Zoom
- **Alt + LEFT/RIGHT/UP/DOWN**: Move the video rectangle (panning).
- **Alt + +/–**: Change video zoom.
- **Alt + BACKSPACE**: Reset pan/zoom settings.

## Advanced Controls
- **l**: Set/clear A-B loop points.
- **L**: Toggle infinite looping.
- **Ctrl + +/–**: Adjust audio delay (A/V sync) by +/- 0.1 seconds.
- **o / P**: Show progression bar, elapsed time, and total duration on the OSD.
- **O**: Toggle OSD states between normal and playback time/duration.
- **i / I**: Show/toggle statistics overlay (use `0,1,2,3,4` keys to cycle through stats).

## Video Adjustment (if supported)
- **1 and 2**: Adjust contrast.
- **3 and 4**: Adjust brightness.
- **5 and 6**: Adjust gamma.
- **7 and 8**: Adjust saturation.
- **Alt + 0**: Resize video window to half its original size.
- **Alt + 1**: Resize video window to its original size.
- **Alt + 2**: Resize video window to double its original size.

## Multimedia Keys (if available)
- **PAUSE**: Pause.
- **STOP**: Stop playing and quit.
- **PREVIOUS/NEXT**: Seek backward/forward 1 minute.

## Mouse Controls
- **Button 3 and 4**: Seek backward/forward 1 minute.
- **Button 5 and 6**: Decrease/increase volume.

## Notes
- Some key bindings may vary depending on the media player or platform.
- For older key bindings, refer to `etc/restore-old-bindings.conf` in the mpv git repository.
