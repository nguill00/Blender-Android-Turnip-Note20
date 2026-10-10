# Compatibility

This file tracks community testing for the Blender Android Mesa Turnip / AdrenoTools build.

## Confirmed devices

| Device | Model | SoC / GPU | Android | Launch | Viewport | Turnip | Notes |
|---|---|---|---|---|---|---|---|
| Samsung Galaxy Note20 Ultra | SM-N986U | Snapdragon 865+ / Adreno 650 | 12+ | ✅ | ✅ | ✅ | Known-good reference device |

## Candidate devices

This build is primarily intended for Qualcomm Snapdragon devices with Adreno GPUs.

Good candidates for testing include:

- Adreno 6xx devices
- Adreno 7xx devices

Turnip is not intended for Mali or PowerVR GPUs.

The current APK requires Android API 31 / Android 12 or newer and ARM64.

## How to test

1. Install the APK from the latest GitHub Release.
2. Launch Blender.
3. Confirm the main UI appears.
4. Open the 3D viewport and verify it renders.
5. Check logcat for Turnip loading.

Useful runtime lines:

    blender-turnip: loaded libvulkan_turnip.so
    hook_impl: loading custom driver: .../libvulkan_turnip.so

A failing stock-driver path may look like:

    /vendor/lib64/hw/vulkan.adreno.so
    Missing features are [timeline semaphores]
    No Vulkan device found

## Report a result

Open a **Compatibility Test** issue and include:

- Phone manufacturer and model
- Exact model number
- Android version
- SoC / chipset
- GPU
- Blender launches: YES / NO
- 3D viewport renders: YES / NO
- Turnip loaded: YES / NO
- Crash: YES / NO
- Relevant logcat output

Successful tests are just as useful as failures. Confirmed devices can be added to the table above.
