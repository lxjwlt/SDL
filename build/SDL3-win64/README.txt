SDL3 Windows 64-bit Bundle
===========================

This is a cross-compiled Windows 64-bit build of SDL3 (Simple DirectMedia Layer).

Build Information:
- Platform: Windows x86_64
- Build Type: Release
- Compiler: MinGW-w64 GCC 15.2.0
- SDL Version: 3.5.0

Directory Structure:
-------------------
bin/           - Runtime libraries (SDL3.dll)
lib/           - Link libraries (libSDL3.dll.a, libSDL3.a, libSDL3_test.a)
include/SDL3/  - Header files
lib/cmake/     - CMake configuration files
lib/pkgconfig/ - pkg-config files

Usage:
------
1. For dynamic linking:
   - Copy SDL3.dll from bin/ to your application directory
   - Link against lib/libSDL3.dll.a
   - Include headers from include/SDL3/

2. For static linking:
   - Link against lib/libSDL3.a
   - Include headers from include/SDL3/
   - You may need to link additional system libraries

Enabled Features:
----------------
- Video drivers: Windows, Dummy, Offscreen
- Render drivers: Direct3D 9/11/12, GPU, OpenGL, OpenGL ES2, Vulkan
- GPU drivers: Direct3D 12, OpenXR, Vulkan
- Audio drivers: DirectSound, WASAPI, Disk, Dummy
- Joystick drivers: DirectInput, HIDAPI, RawInput, Virtual, WGI, XInput
- Camera drivers: MediaFoundation, Dummy

For more information, visit: https://libsdl.org/
