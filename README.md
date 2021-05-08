# GDGD - godot gui desktop drawer

## the plan
![image](https://user-images.githubusercontent.com/2749942/117519655-c6d0c480-afa4-11eb-9e75-eb0f2c26c1c9.png)




# Building
-  copy `custom/customize.py` to the root path of the project. 
-  There is a bunch of stuff disabled to try and minimize output. But its not enough, for example 3d view in editor is not needed for this project but cannot be disabled from build configs due to dependencies in the tool (editor).
-  Status now for ubuntu is atleast it builds fine with a tool binary size of about 140mb after stripping debug binaries.

## Vulcan
-  Platform setup at: https://linuxconfig.org/install-and-test-vulkan-on-linux

## Ubuntu
- Setup vulcan: `apt install libvulkan1 mesa-vulkan-drivers vulkan-utils`
- Install all deps `sudo apt-get install build-essential scons pkg-config libx11-dev libxcursor-dev libxinerama-dev libgl1-mesa-dev libglu-dev libasound2-dev libpulse-dev libudev-dev libxi-dev libxrandr-dev yasm` 

### Building from VSCode
- Added run and build tasks so either F5 for debug-run och ctrl-f5 for run without debug
- These are tasks.json and launch.json

### Building from Terminal 
- Docs at https://docs.godotengine.org/en/latest/development/compiling/index.html
- j8 should be equal to your cores `scons -j8 platform=linuxbsd`

## Post build
- Stripping binary from debug symbols will reduce size with about 400mb `strip bin/godot.linuxbsd.tools.64`
