# DeepDrive

Unreal based simulator and Python interface for self-driving AI development


## Usage

DeepDrive is best used by [one of our agents](https://github.com/deepdrive/deepdrive-agents)

## Development

- [Associate your GitHub username with your Unreal account](https://www.unrealengine.com/en-US/ue4-on-github)

- Clone the Allegorithmic version of Unreal with the Substance plugin <kbd>4.14.0.17</kbd>:
```
    git clone git@github.com:Allegorithmic/UnrealEngine --branch 4.14.0.17
    # or if you are using https: 
    # git clone https://github.com/Allegorithmic/UnrealEngine --branch 4.14.0.17
```

### Windows

- Get Unreal v4.14 via the Epic Launcher -> Unreal Enngine tab -> Library
- Install the Substance Plugin through the Marketplace in Epic Launcher

Opening the project in Unreal will update the Substance textures to Windows-only versions. Once you see these files changed, you can run the following to avoid ever checking them in
```
cd Content/TuningCars/Materials/Hangar/material/Substance
git update-index --assume-unchanged $(git ls-files | tr '\n' ' ')
```

***Refresh / Create Visual Studio project***

***On Windows, Right click the DeepDrive project and set as Startup Project, debug...***

### Linux

The Unreal Editor in Linux works, but not nearly as well as in Windows. So if you develop, we recommend getting things working in Windows, then testing / bug fixing Linux specific issues in Linux.

Build Unreal

```
cd UnrealEngine
./Setup.sh
./GenerateProjectFiles.sh
make  # Takes about an hour
```

More details on building Unreal [here](https://wiki.unrealengine.com/Building_On_Linux) - though the above commands should be sufficient.

Run 
```
./Engine/Binaries/Linux/UE4Editor
```

Open deepdrive uproject file - choose other -> Skip Conversion

**Building the Python Extension**
```
cd Plugins/DeepDrivePlugin/Source/DeepDrivePython
python setup.py install
```

**How to change the field of view**
Content->Tuning Cars->Blueprint->AliceGT->

**How to change the shared memory names (mostly useful for debugging)**

**Development**

***Run game full speed when the window is not focused***
```Uncheck Edit->Editor Preferences->Use Less CPU when in Background```

