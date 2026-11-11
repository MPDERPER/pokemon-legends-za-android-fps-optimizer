# pokemon-legends-za-android-fps-optimizer
Pokémon Legends: Z-A Android optimization pack for Eden Nightly. Dynamic 60 FPS, graphics tweaks, FSR, 2× frame generation, and reduced stuttering. Tested on Snapdragon 8 Gen 2.
Pokémon Legends: Z-A — Android FPS Optimization Pack

An Android-focused optimization preset for Pokémon Legends: Z-A, developed and tested using Eden Nightly.

This repository combines graphics modifications, customized emulator settings, and GPU driver tuning to improve the overall experience of playing Pokémon Legends: Z-A on Android.

The primary objectives are to deliver smoother gameplay, reduce unnecessary graphical effects, minimize flickering and stuttering, and achieve higher displayed frame rates through Eden's frame generation system.

Performance Results

Reported performance: 45–60 displayed FPS with 2× frame generation enabled.

During my testing, this configuration provided:

- Approximately 45–60 displayed FPS.
- Significantly less frequent flickering.
- Reduced stuttering compared with my previous configuration.
- Improved perceived gameplay smoothness.
- A more consistent overall experience.

These results are based on my personal testing and should not be interpreted as guaranteed performance across all devices.

Important: The configuration uses 2× frame generation. Displayed FPS therefore includes generated frames and does not represent the game's native simulation or rendering frame rate.

Tested Hardware and Software

Component| Configuration
Game| Pokémon Legends: Z-A
Title ID| "0100F43008C44000"
Emulator| Eden Nightly
Device| AYN Thor Max
Processor| Snapdragon 8 Gen 2
GPU| Adreno 740
Operating System| Android 13
GPU Driver| MrPurple Turnip T19 (reported test driver)
Rendering API| Vulkan
Console Mode| Handheld
Resolution Scale| 1
Scaling Filter| AMD FidelityFX Super Resolution (FSR)
Frame Generation| Enabled — 2×
Target| Smooth gameplay with reduced stuttering

Different Eden Nightly builds, GPU drivers, devices, and game updates may produce different results.

Included Optimizations

1. Dynamic 60 FPS

Includes a dynamic 60 FPS patch intended to support variable frame rates while maintaining appropriate game timing.

Unlike a traditional static FPS modification, dynamic frame-rate patches are designed to account for changing performance.

The effectiveness depends on the game version, emulator implementation, and actual rendering performance.

2. Improved Field of View

Increases the game's field of view, allowing more of the environment to remain visible.

This primarily improves the viewing experience rather than performance.

3. Reduced Bloom

Reduces excessive bloom effects to provide a cleaner image.

This may reduce visual distraction and improve perceived image clarity.

4. Disabled Depth of Field

Disables depth-of-field effects that intentionally blur certain parts of the image.

This produces a sharper presentation and may reduce some post-processing overhead.

5. Disabled FXAA

Disables the game's FXAA implementation.

This reduces post-processing but may introduce additional aliasing or shimmering around edges.

6. Customized Eden Nightly Configuration

The included "0100F43008C44000.ini" contains my customized game-specific settings.

Rather than using Eden's default configuration, this preset adjusts rendering, synchronization, frame generation, CPU behavior, and GPU-related options.

Important Eden Settings

The following settings are present in my configuration.

Setting| Value
Resolution scaling| 0.75×
Console mode| Handheld
Scaling filter| FSR
FSR sharpening| 0
Frame generation| Enabled
Frame generation multiplier| 2×
Frame generation flow scale| 50
Frame generation queue target| 1
GPU accuracy| "1"
DMA accuracy| "2"
GPU fence behavior| "2"
Asynchronous GPU emulation| Enabled
Asynchronous shaders| Enabled
Asynchronous presentation| Enabled
Disk shader cache| Enabled
Reactive flushing| Disabled
Buffer history| Enabled
Optimized vertex buffers| Disabled
GPU texture unswizzling| Enabled
VSync| Disabled
Custom CPU ticks| 21000
Android pipeline workers| 3

Some settings are experimental, emulator-build-dependent, or may introduce compatibility issues.

These values are provided as a complete tested configuration, not as individually proven performance improvements.

Resolution and FSR

The preset uses 0.75× rendering resolution in handheld mode.

For a nominal 720p rendering target, this corresponds to approximately 540p before upscaling.

FSR is used to improve the presentation of the lower-resolution output.

Actual internal resolution may vary depending on the game's rendering behavior.

Frame Generation

Eden's frame generation is enabled with a 2× multiplier.

This increases the number of frames presented on the display but does not automatically double the game's native rendering performance.

Frame generation can improve perceived smoothness, although latency, interpolation artifacts, and image quality may vary.

Additional Visual Adjustments

The configuration also contains an optional color-grading shader with adjusted brightness, contrast, gamma, and saturation.

These are aesthetic adjustments rather than established performance improvements.

Installation Guide

Requirements

Before installing, make sure you have:

- Pokémon Legends: Z-A and the corresponding game update from your own legally obtained copy.
- A compatible Eden Nightly build for Android.
- A Vulkan-compatible Android GPU.
- An appropriate GPU driver.
- The files provided in this repository.

Step 1 — Download the Optimization Pack

Download the latest release from this repository.

The main files are:

- "Pokemon ZA Mods.zip"
- "0100F43008C44000.ini"

Step 2 — Install the Graphics Patches

1. Extract "Pokemon ZA Mods.zip".
2. Open Eden Nightly.
3. Find Pokémon Legends: Z-A in your game library.
4. Long-press the game and open its configuration or Add-Ons menu.
5. Import the required mod folders, or use the game's mod data location where available.
6. Enable the imported patches.
7. Restart the game.

Each mod must retain its "exefs" folder.

For example:

"[Disable DOF v2.0.2]/exefs/2.0.2.pchtxt"

Do not select an unrelated parent directory when using an importer that expects an "exefs", "romfs", or "cheats" folder.

Step 3 — Apply the Eden Configuration

The file "0100F43008C44000.ini" contains the game-specific emulator configuration.

Back up your existing configuration before replacing it.

Use Eden's per-game configuration import function if your build provides one.

Otherwise, apply the documented settings through the game's configuration menu.

The INI is an emulator configuration file, not an ExeFS mod. Do not import it through the Add-Ons menu.

After applying the preset, verify that the settings were imported correctly.

Step 4 — Configure the GPU Driver

My reported results were obtained using MrPurple Turnip T19.

Download compatible drivers from the original developer:

"https://github.com/MrPurple666/purple-turnip/releases" (https://github.com/MrPurple666/purple-turnip/releases)

Select your installed driver in Eden's GPU driver settings.

Important: The provided INI was exported with a reference to a T26 driver installation. That saved path is device-specific and must not be treated as the recommended driver.

Select T19 manually if you wish to reproduce my reported setup.

I do not include third-party GPU driver binaries in this repository.

Step 5 — Launch and Test

Launch Pokémon Legends: Z-A after applying the configuration.

Check that:

- The intended graphics patches are enabled.
- The GPU driver is correctly selected.
- Frame generation is enabled.
- The resolution scale is set correctly.
- The game behaves normally during movement, battles, and transitions.

For troubleshooting, disable individual patches or experimental settings to identify possible conflicts.

Game Version Compatibility

The graphics archive contains patches identified for the following versions:

Game version| Graphics patch files included
1.0.0–1.0.1| Yes
1.0.2| Yes
2.0.0| Yes
2.0.2| Yes

The Dynamic 60 FPS patch uses a separate build identifier, and compatibility with each listed update has not been independently established.

Having a patch file for a particular version does not guarantee that the complete configuration has been tested successfully with that version.

Recommended: Use the game version corresponding to the patch files and verify the selected patch is actually being applied.

Known Limitations

This is an experimental, device-tested optimization preset.

Possible limitations include:

- Occasional graphical flickering.
- Shader compilation stuttering.
- Frame-generation artifacts.
- Different performance across game areas.
- Additional visual aliasing from disabled FXAA.
- Reduced image quality from lower rendering resolution.
- Compatibility differences between Eden Nightly builds.
- Potential instability from experimental CPU or GPU settings.
- Driver-specific rendering issues.

The pack is intended to reduce these problems, not guarantee their complete elimination.

Troubleshooting

The game crashes on startup

Disable the graphics patches and test the game without them.

Re-enable patches individually to isolate the problem.

Check your game update and patch compatibility.

Performance is worse than expected

Verify your selected GPU driver, rendering resolution, and frame-generation settings.

Test again without additional modifications.

Flickering or visual corruption occurs

Try disabling experimental graphics options or testing another compatible GPU driver.

Not every driver will behave identically.

The game feels slow despite a high FPS reading

Check native performance with frame generation disabled.

Generated frames do not increase the underlying game simulation rate.

Eden does not recognize the mod

Confirm that the selected folder contains an "exefs", "romfs", or "cheats" directory.

Import the individual mod folder rather than an unrelated parent folder.

Contributing and Feedback

Feedback is welcome, particularly from users testing different Snapdragon devices, Eden Nightly versions, and GPU drivers.

When reporting results, please include:

- Device model
- Processor/GPU
- Android version
- Eden Nightly build
- GPU driver version
- Game update version
- Native FPS, if measured
- Displayed FPS with frame generation
- Any crashes, flickering, or stuttering

Performance comparisons with and without this preset are especially useful.

Credits and Acknowledgments

This optimization pack combines third-party graphics modifications with my own emulator configuration, testing, and preset assembly.

Original graphics modifications:

Fl4sh9174 — FPS and graphics patches:

"https://github.com/Fl4sh9174" (https://github.com/Fl4sh9174)

"https://github.com/Fl4sh9174/Switch-Emulator-Ultrawide-FPS-Mods" (https://github.com/Fl4sh9174/Switch-Emulator-Ultrawide-FPS-Mods)

StevensND — credited in the Disable DOF patch:

"https://github.com/StevensND/switch-port-mods" (https://github.com/StevensND/switch-port-mods)

GPU driver development:

MrPurple666 — Custom Turnip drivers:

"https://github.com/MrPurple666/purple-turnip" (https://github.com/MrPurple666/purple-turnip)

Emulator:

Eden development team:

"https://eden-emu.dev/" (https://eden-emu.dev/)

All credit for the original patches, drivers, and emulator software belongs to their respective developers.

My contribution is the selection, combination, configuration, testing, and documentation of this Android optimization setup.

Disclaimer

This is an unofficial community optimization project.

It is not affiliated with or endorsed by Nintendo, The Pokémon Company, Game Freak, or the Eden development team.

No game files, encryption keys, firmware, or copyrighted game assets are distributed.

Third-party modifications remain the intellectual property of their respective creators. Redistribution is subject to the original authors' permissions and licensing terms.

Your results may vary depending on your hardware, GPU driver, game version, and emulator build.
