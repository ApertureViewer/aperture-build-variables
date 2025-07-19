# Aperture Viewer - Build Variables

## Overview

This repository contains the master `variables` file for the Aperture Viewer build system. Its purpose is to define the specific compiler flags and settings required for a successful build on supported platforms.

This is a mandatory dependency for compiling Aperture Viewer from source.

## Origin and Lineage

The scripts and variable definitions in this repository, while adapted and de-branded for Aperture Viewer, are based on the original open-source work from both the **Linden Lab** and **Firestorm Viewer** projects. We gratefully acknowledge their foundational contributions.

## Usage

The Aperture Viewer build system automatically consumes the `variables` file from this repository. To use it, you must:

1.  **Clone this repository** to a location on your machine. For example:
    ```
    git clone https://github.com/ApertureViewer/aperture-build-variables.git
    ```

2.  **Set the `AUTOBUILD_VARIABLES_FILE` environment variable** to point directly to the `variables` file inside your cloned repository.

    **Example (Windows Command Prompt):**
    ```cmd
    set AUTOBUILD_VARIABLES_FILE=C:\path\to\your\clone\aperture-build-variables\variables
    ```
    It is recommended to set this as a permanent system environment variable.

Once this environment variable is set, the `autobuild` tool used by the Aperture Viewer build process will automatically load the correct compiler flags.

## Structure

*   **`variables`**: The main file containing all compiler flags, organized by platform (`WINDOWS`, `LINUX`) and build type (`RELEASE`, `RELWITHDEBINFO`). All Aperture-specific configurations (`RELEASEAP_*`) are defined here.
*   **`functions` & `convenience`**: These are helper scripts inherited from the upstream build system, used to provide shell functions and aliases. They are not typically used during a standard developer build but are preserved for compatibility.