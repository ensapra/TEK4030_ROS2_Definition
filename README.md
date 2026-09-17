# TEK4030_ROS2_Definition

This repository contains a `.def` file to be used with Apptainer.

## Intended use

It is recommended to use Apptainer on UiO computers through the Omnissa Client. Accessing an IFI workstation or the UiO Linux Desktop will provide you with your user Linux environment.

Apptainer allows you to create custom environments without having to install dependencies in the global environment. It is also the only way to install libraries on UiO computers.

Once there, opening a terminal will give you access to Apptainer.

## How to use

1. Download `ros-jazzy.def`.

2. Place the file inside a folder in your Documents folder. Any folder will work, but I recommend having a single location where it is easy to launch Apptainer and access your files.

3. Open a terminal in that folder (via right-click → **Open Terminal**, or by navigating to the folder using `cd path/to/file`).

4. Run:

   ```bash
   apptainer build ros-jazzy.sif ros-jazzy.def
   ```

   This will build the environment and download all the necessary components for ROS 2 to work.

5. Run:

   ```bash
   apptainer shell ros-jazzy.sif
   ```

   Every time you want to access your environment from a new terminal, you will have to run this command.

   You should see something similar to:

   ```text
   APPT your/current/path $
   ```

   This means you are inside your Apptainer environment.

6. Running `ros2` in the terminal should now display the help message, confirming that ROS 2 is installed correctly.

## Known issues

Currently, IntelliSense does not work with the `.sif` environment.
