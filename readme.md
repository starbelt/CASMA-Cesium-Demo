# CASMA-Cesium-Demo

This folder contains demos using [CesiumJS](https://cesium.com/platform/cesiumjs/) for use in AOE 4414 - Computer Aided Space Mission Planning. Below is an overview of the main files:

### `twosat.html`

- **Purpose:**  
  Visualizes two satellites in orbit above a ground station (Blacksburg, VA) using CesiumJS and [satellite.js](https://github.com/shashwatak/satellite-js).
- **Features:**  
  - Loads two example satellites from TLE (Two-Line Element) data.
  - Propagates their orbits for 2 hours and animates their positions.
  - Animates satellite paths and labels.
  - Camera looks at sky from a ground station in Blacksburg.

### `ecef_eci.html`

- **Purpose:**  
  Demonstrates the difference between ECEF (Earth-Centered, Earth-Fixed) and ECI (Earth-Centered Inertial) coordinate frames.
- **Features:**  
  - Draws ECEF axes and ECI axes.
  - Animates the ECI axes and the direction to first point of Aries.
  - Has camera rotate to make it seem if ECI is fixed, so that the globe rotates and stars are fixed.
  - Camera starts in a position to view both sets of axes.

### Authors:
- Tejas Vinod