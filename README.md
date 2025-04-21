# my configrations for MPV Media Player 

## Keyboard and Mouse Controls
### Seek Controls
- **LEFT and RIGHT**: Seek backward/forward 5 seconds.  
  `Shift + LEFT/RIGHT`: Exact seek backward/forward 1 second.
- **UP and DOWN**: Seek forward/backward 1 minute.  
  `Shift + UP/DOWN`: Exact seek forward/backward 5 seconds.
- **Ctrl + LEFT/RIGHT**: Seek to the previous/next subtitle (may have restrictions).
- **Ctrl + Shift + LEFT/RIGHT**: Adjust subtitle delay to sync subtitles to audio.
- **PGUP and PGDWN**: Seek to the beginning of the previous/next chapter.  
  `Shift + PGUP/PGDWN`: Seek backward/forward 10 minutes.

### Playback Speed Controls
- **[ and ]**: Decrease/increase playback speed by 10%.
- **{ and }**: Halve/double playback speed.
- **BACKSPACE**: Reset playback speed to normal.
- **Shift + BACKSPACE**: Undo the last seek (if the playlist entry hasn't changed).
- **Shift + Ctrl + BACKSPACE**: Mark the current position for later revert.

### Playlist Navigation
- **< and >**: Go backward/forward in the playlist.
- **ENTER**: Go forward in the playlist.

### Playback Controls
- **p / SPACE**: Pause (pressing again unpauses).
- **.**: Step forward (frame-by-frame).
- **,**: Step backward (frame-by-frame).
- **q**: Stop playing and quit.
- **Q**: Stop playing, quit, and store the current playback position for later resume.

### Volume Controls
- **/ and ***: Decrease/increase volume.
- **9 and 0**: Decrease/increase volume.
- **m**: Mute sound.

### Track Selection
- **_**: Cycle through available video tracks.
- **#**: Cycle through available audio tracks.
- **j and J**: Cycle through available subtitles.

### Subtitle Controls
- **v**: Toggle subtitle visibility.
- **z and Z**: Adjust subtitle delay by +/- 0.1 seconds.
- **r and R**: Move subtitles up/down.
- **u**: Toggle SSA/ASS subtitle style overrides.
- **V**: Toggle subtitle VSFilter aspect compatibility mode.

### Screenshot Controls
- **s**: Take a screenshot.
- **S**: Take a screenshot without subtitles.
- **Ctrl + s**: Take a screenshot as the window shows it (with subtitles, OSD, and scaled video).

### Video Controls
- **f**: Toggle fullscreen.
- **ESC**: Exit fullscreen mode.
- **T**: Toggle stay-on-top.
- **w and W**: Decrease/increase pan-and-scan range.
- **A**: Cycle aspect ratio override.
- **d**: Activate/deactivate deinterlacer.
- **Ctrl + h**: Toggle hardware video decoding.

### Pan and Zoom
- **Alt + LEFT/RIGHT/UP/DOWN**: Move the video rectangle (panning).
- **Alt + +/–**: Change video zoom.
- **Alt + BACKSPACE**: Reset pan/zoom settings.

### Advanced Controls
- **l**: Set/clear A-B loop points.
- **L**: Toggle infinite looping.
- **Ctrl + +/–**: Adjust audio delay (A/V sync) by +/- 0.1 seconds.
- **o / P**: Show progression bar, elapsed time, and total duration on the OSD.
- **O**: Toggle OSD states between normal and playback time/duration.
- **i / I**: Show/toggle statistics overlay (use `0,1,2,3,4` keys to cycle through stats).

### Video Adjustment (if supported)
- **1 and 2**: Adjust contrast.
- **3 and 4**: Adjust brightness.
- **5 and 6**: Adjust gamma.
- **7 and 8**: Adjust saturation.
- **Alt + 0**: Resize video window to half its original size.
- **Alt + 1**: Resize video window to its original size.
- **Alt + 2**: Resize video window to double its original size.

### Multimedia Keys (if available)
- **PAUSE**: Pause.
- **STOP**: Stop playing and quit.
- **PREVIOUS/NEXT**: Seek backward/forward 1 minute.

### Mouse Controls
- **Button 3 and 4**: Seek backward/forward 1 minute.
- **Button 5 and 6**: Decrease/increase volume.

## Configuration Files

MPV uses several configuration files to customize behavior:

### Main Configuration Files
- **mpv.conf**: Main configuration file
  - Location (Windows): `%APPDATA%\mpv\mpv.conf`
  - Location (Linux/macOS): `~/.config/mpv/mpv.conf`
  - via snap (linux): ```nano ~/snap/mpv/current/.config/mpv/mpv.conf```
- **input.conf**: Custom key bindings
  - Location (Windows): `%APPDATA%\mpv\input.conf`
  - Location (Linux/macOS): `~/.config/mpv/input.conf`

### Essential Configuration Options for mpv.conf

#### Video Settings
```
# Video Settings
profile=gpu-hq               # High quality video rendering preset
scale=ewa_lanczossharp       # High quality video scaling
cscale=ewa_lanczossharp      # High quality colorspace scaling
video-sync=display-resample  # Sync video to display refresh rate
interpolation                # Frame interpolation for smoother playback
tscale=oversample            # Filter for interpolation
hwdec=auto-safe              # Hardware video decoding when possible

# Resolution and display
geometry=50%                 # Start with window 50% of screen size
autofit-larger=90%x90%       # Don't allow window larger than 90% of screen
fullscreen=no                # Don't start in fullscreen mode

# OSD Settings
osd-level=1                  # Display time and duration
osd-duration=2000            # Show OSD for 2 seconds
osd-font='Sans'              # OSD font
osd-font-size=32             # OSD font size
osd-color='#FFFFFF'          # OSD font color
osd-border-color='#000000'   # OSD border color
osd-bar-h=2                  # Height of OSD bar
osd-bar-w=90                 # Width of OSD bar as percentage
osd-bar=yes                  # Show OSD bar during seek
```

#### Audio Settings
```
# Audio Settings
volume=80                    # Default volume (0-100)
volume-max=100               # Maximum volume
audio-channels=auto          # Use audio file's native channel layout
audio-device=auto            # Use default audio device
audio-pitch-correction=yes   # Pitch correction during audio speed change
af=scaletempo2=min-speed=0.25:max-speed=4.0  # Audio filter for speed changes
alang=eng,en,jpn,jp          # Audio language priority
```

#### Subtitle Settings
```
# Subtitle Settings
sub-auto=fuzzy               # Load subtitles automatically
sub-file-paths=sub:subs:subtitles  # Look for subtitles in these folders
slang=eng,en                 # Subtitle language priority
sub-font='Sans'              # Subtitle font
sub-font-size=48             # Subtitle font size
sub-color='#FFFFFF'          # Subtitle font color
sub-border-color='#000000'   # Subtitle border color
sub-border-size=2            # Subtitle border size
sub-pos=95                   # Subtitle position (lower is higher on screen)
```

#### Screenshot Settings
```
# Screenshot Settings
screenshot-format=png        # Screenshot format (png, jpg, etc.)
screenshot-png-compression=7 # PNG compression level (0-9)
screenshot-template='%F-%P-%n'  # Filename template
screenshot-directory=~/Pictures  # Save screenshots here
```

#### Performance & Cache Settings
```
# Cache Settings
cache=yes                    # Enable cache
demuxer-max-bytes=400MiB     # Max size of cache
demuxer-max-back-bytes=150MiB  # Max size for backward cache

# GPU Rendering
gpu-api=auto                 # GPU API (auto, opengl, vulkan, d3d11)
vulkan-async-compute=yes     # Use async compute with Vulkan
vulkan-async-transfer=yes    # Use async transfers with Vulkan
```

#### Miscellaneous Settings
```
# Miscellaneous
keep-open=yes                # Don't close player after file ends
save-position-on-quit=yes    # Remember position when quitting
watch-later-directory=~/.config/mpv/watch_later  # Save position here
autoload-files=yes           # Load related files automatically
loop-playlist=inf            # Loop playlist infinitely
reset-on-next-file=pause     # Reset pause status when loading next file

# UI Behavior
cursor-autohide=1000         # Hide cursor after 1 second
fit-border=no                # Don't add border when fitting window

# Network Settings
user-agent="Mozilla/5.0"     # User agent for HTTP streams
ytdl-format=bestvideo[height<=?1080]+bestaudio/best  # YouTube-dl format selection
```

### Script Settings
MPV supports Lua scripts for extending functionality. Scripts go in:
- Windows: `%APPDATA%\mpv\scripts\`
- Linux/macOS: `~/.config/mpv/scripts/`

### Common Useful Scripts
1. **sponsorblock.lua** - Skips sponsored segments in YouTube videos
2. **autoload.lua** - Automatically loads all videos in the current directory into a playlist
3. **stats.lua** - Shows detailed playback statistics
4. **modernx.lua** - Modern UI overlay for MPV
5. **mpv-thumbnail-script** - Shows thumbnails when hovering over the timeline

### Profile Configuration
Profiles allow you to have different settings for different types of content:

```
# High quality profile for movies
[high-quality]
profile=gpu-hq
scale=ewa_lanczossharp
cscale=ewa_lanczossharp
video-sync=display-resample
interpolation
tscale=oversample

# Low-quality profile for old content
[low-quality]
profile=fast
scale=bilinear
cscale=bilinear
dscale=bilinear
interpolation=no
correct-downscaling=no

# YouTube profile with specific settings for streaming
[youtube]
ytdl-format=bestvideo[height<=?1080]+bestaudio/best
force-window=immediate
script-opts=ytdl_hook-try_ytdl_first=yes
demuxer-lavf-o=reconnect=1:reconnect_streamed=1:reconnect_delay_max=5

# Apply profiles based on file patterns
[extension.webm]
loop-file=inf

[extension.gif]
loop-file=inf

# Apply profile for 4K content
[4k]
profile-cond=width >= 3840
hwdec=auto
```

## Advanced Features

### Hardware Acceleration
To enable hardware acceleration:
```
hwdec=auto-safe       # Try all hardware decoding methods
```
For specific hardware:
```
hwdec=nvdec           # NVIDIA GPU acceleration
hwdec=vaapi           # Intel/AMD GPU acceleration on Linux
hwdec=dxva2           # Windows DirectX Video Acceleration
hwdec=videotoolbox    # macOS hardware acceleration
```

### HDR Playback Support
For HDR video playback:
```
# HDR settings
target-trc=pq         # HDR10 transfer function
hdr-compute-peak=yes  # Dynamic HDR tone mapping
tone-mapping=mobius   # HDR to SDR tone mapping algorithm
gamut-mapping-mode=desaturate  # Color space mapping algorithm
```

### Upscaling Settings
For high-quality upscaling:
```
# High quality upscaling
glsl-shaders="~/.config/mpv/shaders/FSRCNNX_x2_8-0-4-1.glsl"  # AI upscaling shader
scale=ewa_lanczossharp
cscale=ewa_lanczossharp
dscale=mitchell
correct-downscaling=yes
linear-downscaling=yes
sigmoid-upscaling=yes
```

### Audio Enhancement
For better audio:
```
# Audio enhancement
af=loudnorm=I=-16:TP=-3:LRA=4   # Audio normalization
audio-spdif=ac3,dts,eac3,dts-hd  # Pass through lossless audio to receiver
```

### Protocol-Specific Settings
```
# Network protocols settings
[protocol.http]
hls-bitrate=max       # Use maximum quality for HLS streams
cache=yes
demuxer-max-bytes=150MiB
demuxer-readahead-secs=20

[protocol.https]
profile=protocol.http

[protocol.ytdl]
profile=protocol.http
```

### Automatic Recovery from Playback Errors
```
# Error recovery
hr-seek-framedrop=yes     # Drop frames when seeking for smoother playback
demuxer-thread=yes        # Use a separate thread for demuxing
demuxer-readahead-secs=10 # Read ahead to prevent stuttering
```

### Custom Shader Support
For film grain, denoising, or other effects:
```
# Shader examples
glsl-shaders="~/.config/mpv/shaders/KrigBilateral.glsl:~/.config/mpv/shaders/adaptive-sharpen.glsl"  # Multiple shaders
```

## Troubleshooting Tips

1. **Playback Issues**
   - Try different hwdec values: `hwdec=no`, `hwdec=auto`, or specific ones like `hwdec=nvdec`
   - Reduce settings: `profile=fast`
   - Disable fancy scaling: `scale=bilinear`, `cscale=bilinear`

2. **Performance Problems**
   - Reduce cache settings: `demuxer-max-bytes=50MiB`
   - Disable interpolation: `interpolation=no`
   - Use faster scaling algorithms: `scale=bilinear`
   - Enable hardware decoding: `hwdec=auto-safe`

3. **Audio Sync Issues**
   - Adjust audio sync: `audio-delay=0.05` (50ms delay)
   - Try different video-sync modes: `video-sync=audio`

4. **Subtitles Not Loading**
   - Check subtitle paths: `sub-file-paths=sub:subs:subtitles`
   - Enable verbose logging: `--msg-level=sub=trace`
