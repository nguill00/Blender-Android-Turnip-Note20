# Blender Android Turnip - Known Good Note20 Build

## Status

WORKING

## Tested

Samsung Galaxy Note20 Ultra SM-N986U / Adreno 650.

## Fix

Mesa Turnip is bundled and loaded using libadrenotools.

Old failure:

    /vendor/lib64/hw/vulkan.adreno.so
    Missing features are [timeline semaphores]
    No Vulkan device found
    SIGSEGV

Working path:

    blender-turnip: loaded libvulkan_turnip.so
    hook_impl: loading custom driver: .../libvulkan_turnip.so

Blender reaches the UI and renders the 3D viewport.

## APK

Blender-Note20-Turnip-KNOWN-GOOD.apk
