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

## build steps

```
cmake --build build --config Release -j$(sysctl -n hw.ncpu)

cmake --install build --config Release --prefix build/SDL3-win64
```