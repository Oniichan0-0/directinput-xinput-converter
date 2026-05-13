# DirectInput to XInput Converter

A Windows utility for configuring DirectInput controllers to work with games and applications that expect XInput-style controller input.

This project lets you add programs, assign controller profiles, and map DirectInput or keyboard inputs to XInput controls.

## Screenshot

<img width="967" height="627" alt="Screenshot 2026-05-14 001341" src="https://github.com/user-attachments/assets/2792db26-d44f-4993-b2e1-3734f6eaf6b4" />


## Features

- Add games or applications to a managed program list
- Assign controller profiles per program
- Map DirectInput controller buttons and axes to XInput controls
- Keyboard input mapping support
- Multiple controller profile support
- XInput DLL version detection for selected programs
- Automatic configuration application for added programs
- Windows Forms desktop interface

## What is DirectInput to XInput?

Many older or generic controllers use **DirectInput**, while many modern PC games are designed around **XInput**, the input system commonly used by Xbox controllers.

This tool helps bridge that gap by allowing DirectInput controller inputs to be mapped to XInput-style controls.

## Download

Download the latest release from the **Releases** section of this repository.

After downloading:

1. Download the release ZIP file.
2. Extract the ZIP.
3. Run:

```text
di2xinput
```

Keep all included files in the same folder.

## How to Use

1. Open the application.
2. Add the game or application you want to configure.
3. Select or create a controller profile.
4. Choose the input device you want to use.
5. Map DirectInput controller inputs or keyboard inputs to XInput controls.
6. Save the profile.
7. Launch the configured game or application.

## Building from Source

### Requirements

Install **Visual Studio** with:

- `.NET desktop development`
- `Desktop development with C++`

Recommended components:

- `.NET Framework 4.8 targeting pack`
- Windows 10 SDK or Windows 11 SDK
- MSVC C++ build tools
- MSVC v141 build tools for older Visual Studio 2017 project compatibility

### Build Steps

1. Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
```

2. Open the solution file in Visual Studio:

```text
di2xinput.sln
```

3. If Visual Studio asks to retarget projects, choose the recommended option.

4. Set the startup project to:

```text
di2xinput
```

5. Select a build configuration:

```text
Release | x64
```

or, in Visual Studio:

```text
Debug | x64
```

6. Build the solution:

```text
Ctrl + Shift + B
```

7. Run the application:

```text
F5
```

## Project Structure

```text
di2xinput/
├── MainForm.cs              # Main application logic
├── MainForm.Designer.cs     # Windows Forms designer layout
├── InputDialog.cs           # Input mapping dialog
├── DIManager.cs             # DirectInput controller handling
├── XIManager.cs             # XInput control definitions
├── Mapping.cs               # Input mapping logic
├── ProfileManager.cs        # Profile loading and saving
├── ProgramManager.cs        # Program list and configuration handling
├── Resources/               # Images and application resources
└── Properties/              # Project settings

HookDLL/
├── HookDLL.vcxproj          # C++ hook DLL project
├── Controller.cpp           # Controller hook logic
├── DirectInput.cpp          # DirectInput handling
└── Supporting C++ source files
```

## Notes

- This application is intended for Windows.
- Some games or installation folders may require administrator permissions.
- If configuration files are not being written correctly, run the application as administrator.
- Keep the executable and included DLL/configuration files together.
- Compatibility may vary depending on the game, controller, and how the game handles input.

## Troubleshooting

### The app does not save configuration

Run the application as administrator, especially if the game is installed in a protected folder such as:

```text
Program Files
Program Files (x86)
```

### My controller does not appear

Make sure the controller is connected before launching the application.

You can also try reconnecting the controller and reopening the device dropdown.

### The game does not detect the controller

Check that the correct program was added, the correct profile is assigned, and the mapping has been saved.

Some games may require restarting after configuration changes.

## Disclaimer

Use this tool only with games and applications where input remapping or controller compatibility tools are allowed.