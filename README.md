# Godot Video Decoder

GDNative Video Decoder library for [Godot Engine](https://godotengine.org),
using the [FFmpeg](https://ffmpeg.org) library for codecs.

**A GSoC 2018 Project**

## Instructions to use the test project

1. Clone the repository and initialize submodules

```
git clone https://github.com/KidRigger/godot-videodecoder.git godot-videodecoder
cd godot-videodecoder
git submodule update --init --recursive
```

2. Clone FFmpeg in another folder.

```
git clone git://source.ffmpeg.org/ffmpeg.git ffmpeg
```

3. Switch ffmpeg to branch `release/4.1`
   (Tested with both `release/4.0` and `release/4.1`.)

4. Configure FFmpeg using the `configure` tool in the ffmpeg repository.
   Use the following flags. (Or as per requirement) [Needs OpenCL].
   **Make sure to replace the path to godot-videodecoder folder!**

   
   - OSX:

      ./configure --enable-shared --enable-version3 --disable-programs \
      --enable-libmp3lame --enable-libtheora \
      --enable-libvorbis --enable-libvpx --enable-libwebp \
      --enable-opencl --enable-opengl --disable-debug \
      --prefix=<path-to-videodecoder-folder>/godot-videodecoder/thirdparty


   - Linux:

      ./configure --enable-shared --enable-version3 --disable-programs \
      --enable-libmp3lame --enable-libtheora \
      --enable-libvorbis --enable-libvpx --enable-libwebp \
      --enable-opencl --enable-opengl --disable-debug \
      --prefix=<path-to-videodecoder-folder>/godot-videodecoder/thirdparty

   - Windows:

      configure --enable-shared --enable-version3 --disable-programs \
      --enable-libmp3lame --enable-libtheora \
      --enable-libvorbis --enable-libvpx --enable-libwebp \
      --enable-opencl --enable-opengl --disable-debug \
      --prefix=<path-to-videodecoder-folder>/godot-videodecoder/thirdparty


5. Run `make` and then `make install`.

6. Go to the Godot videodecoder folder, and clone the samples:
   `git submodule update --init`
   
7. Now, use `scons` to build the project.
   - OSX: `scons platform=osx`
   - Linux: `scons platform=x11`
   - Windows: `scons platform=win64`
   
8. Now you can simply use the test project.
9. For your own custom project:
   1. You can copy and paste the `addons` folder from inside the `test` project. (Or you could write your own `.gdnlib` file.)
   2. Add the plugin to the project in Godot.
   3. ???
   4. Enjoy
