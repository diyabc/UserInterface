# DIYABC-RF GUI standalone build pipeline

This folder and its contents are only usefull for the standalone app developpers.

If you are a DIYABC-RF GUI user, please refer to README file at project root for installation and use instructions.

## Build preparation (for any platform)

1. Update `DESCRIPTION` file with version number and date: `Rscript prebuild.R`

2. Generate local `.Renviron` file: `Rscript generate_Renviron.R`

3. Install (or update) dependencies: `Rscript prepare_build.R`

## Windows standalone

Please read dedicated [README file](DIYABC-RF_GUI_windows/README.md) to setup environment.

### Build

> To be run on Windows OS.

1. Init and/or update `DesktopDeployrR` submodule
```bash
git submodule init
git submodule update
```

2. Build `diyabcGUI` packages zip sources for Windows
```bash
Rscript.exe build_windows_package.R
```

3. Build `DIYABC-RF_GUI` standalone app for Windows
```bash
Rscript.exe build_windows_standalone.R
```

> Release `dist/DIYABC-RF_GUI_<latest_version>.zip`

### Usage

1. Unzip `DIYABC-RF_GUI_<latest_version>.zip` 

2. Run `DIYABC-RF_GUI` (or `DIYABC-RF_GUI.bat`) in the previously extracted directory (either by double-clicking it or in a terminal).

> A log file for DIYABC-RF GUI is available in your user-specific directory for temporary files, generally `C:\Users\<username>\AppData\Local\Temp\DIYABC-RF_GUI_<timestamp>_<random_number>/`.

### Debugging

If you encounter any issue, you can try to use the application as a local shiny app (it should give you additional verbosity). To do this you can run `cmd.exe /c run_local_app_debug.bat` from the previously extracted directory in a terminal.
