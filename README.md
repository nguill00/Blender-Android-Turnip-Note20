# Blender Android - Mesa Turnip / AdrenoTools Build

Experimental Blender 5.3 Alpha Android build tested on Samsung Galaxy Note20 Ultra SM-N986U with Snapdragon / Adreno 650.

## What this fixes

The stock Qualcomm Vulkan driver on the tested Note20 did not meet Blender Vulkan requirements because timeline semaphores were unavailable.

This build packages Mesa Turnip and loads it through libadrenotools.

## Confirmed working

- Blender launches
- 3D viewport renders
- Mesa Turnip loads
- AdrenoTools hooks load
- Startup Vulkan crash is avoided

Runtime verification:

    blender-turnip: loaded libvulkan_turnip.so
    hook_impl: loading custom driver: .../libvulkan_turnip.so

## Compatibility

Primarily intended for Qualcomm Snapdragon devices using Adreno GPUs.

- Adreno 6xx: candidate
- Adreno 7xx: candidate
- Mali / PowerVR: Turnip is not intended for these GPUs
- Android minimum: API 31 / Android 12

Confirmed so far:

| Device | Model | SoC / GPU | Android | Launch | Viewport | Turnip |
|---|---|---|---|---|---|---|
| Samsung Galaxy Note20 Ultra | SM-N986U | Snapdragon 865+ / Adreno 650 | 12+ | ✅ | ✅ | ✅ |

See [COMPATIBILITY.md](COMPATIBILITY.md) for the full test matrix and reporting instructions.

### Test another phone

If you try this build on another device, please open a **Compatibility Test** issue and include:

- Phone manufacturer and model
- Exact model number
- Android version
- SoC / chipset
- GPU
- Whether Blender launches
- Whether the 3D viewport renders
- Whether Turnip loads
- Whether it crashes
- Relevant logcat output if it fails

The repository includes an issue template so reports stay consistent and useful.

## Installing

Download the APK from GitHub Releases.

    adb install Blender-Note20-Turnip-KNOWN-GOOD.apk

For a clean install:

    adb uninstall org.blender.blender

## Build configuration

- ARM64 / arm64-v8a
- min API 31
- target API 34
- NDK 28.2.13676358
- Mesa Turnip
- libadrenotools
- Blender full feature configuration

See patches/NOTE20-TURNIP.patch, build-files/, and KNOWN-GOOD.txt.

## Important

Experimental Android port. Not an official Blender Foundation Android release.

## License

Blender is GPL licensed. Preserve all applicable Blender and third-party licenses when redistributing.
