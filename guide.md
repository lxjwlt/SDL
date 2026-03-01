# build window bundle

help me build this library into window 64 bundle

## ✓ Completed

Successfully built SDL3 for Windows 64-bit using MinGW cross-compilation.

### Build Output
- **Location**: `build/SDL3-win64/`
- **Archive**: `build/SDL3-win64.zip` (4.7 MB)
- **Total Size**: 16 MB (uncompressed)

### Libraries Included
- `bin/SDL3.dll` - 5.5 MB (shared library)
- `lib/libSDL3.dll.a` - 826 KB (import library for DLL)
- `lib/libSDL3.a` - 6.1 MB (static library)
- `lib/libSDL3_test.a` - 127 KB (test library)

### Headers
All SDL3 headers are in `include/SDL3/`

### Usage
See `build/SDL3-win64/README.txt` for integration instructions.

## rebuild steps

After modifying source files (e.g. `src/joystick/usb_ids.h`), no need to re-run CMake configure. Just rebuild and reinstall:

```sh
# 1. Rebuild (uses all CPU cores)
cmake --build build --config Release -j$(sysctl -n hw.ncpu)

# 2. Overwrite the previous install bundle
cmake --install build --config Release --prefix build/SDL3-win64

# 3. Re-package as zip (optional)
cd build && zip -r SDL3-win64.zip SDL3-win64/ -q && cd ..
```

## force clean rebuild steps

If incremental rebuild is not picking up changes, wipe the build dir and start fresh:

```sh
# 1. Delete all build artifacts and cached CMake state
rm -rf build

# 2. Reconfigure from scratch
cmake -S . -B build \
  -DCMAKE_TOOLCHAIN_FILE=toolchain-mingw64.cmake \
  -DCMAKE_BUILD_TYPE=Release \
  -DSDL_SHARED=ON \
  -DSDL_STATIC=ON \
  -DCMAKE_INSTALL_PREFIX=build/SDL3-win64

# 3. Full build
cmake --build build --config Release -j$(sysctl -n hw.ncpu)

# 4. Install bundle
cmake --install build --config Release --prefix build/SDL3-win64

# 5. Re-package as zip (optional)
cd build && zip -r SDL3-win64.zip SDL3-win64/ -q && cd ..
```