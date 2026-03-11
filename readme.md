# CASMA-Cesium-Demo

This folder contains demos using [CesiumJS](https://cesium.com/platform/cesiumjs/) for use in AOE 4414 - Computer Aided Space Mission Planning. Below is an overview of the main files:

## `blacksburg_horizon.html`

- **Purpose:**  
  Visualizes in satellites in orbit from the VT NSI telescope using CesiumJS and [satellite.js](https://github.com/shashwatak/satellite-js).
- **Features:**  
  - Loads two example satellites from TLE (Two-Line Element) data.
  - Propagates their orbits for 2 hours and animates their positions.
  - Animates satellite paths and labels.
  - Camera looks at sky from a ground station in Blacksburg.

## `czml_satellites.html`

- **Purpose:**  
  Visualizes satellites using a CZML (Cesium Language) data file in CesiumJS.

- **Features:**  
  - Initializes a CesiumJS viewer with animation enabled.
  - Loads satellite data from an external CZML file (`satellites.czml`).
  - Displays time-dynamic satellite positions and trajectories defined in the CZML file.
  - Uses Cesium’s `CzmlDataSource` to automatically parse and render satellite data.
  - Camera begins at the default Earth "home" view using `viewer.camera.flyHome()`.

- **Notes:**  
  - The CZML file (`satellites.czml`) should be located in the same directory as the HTML file.

## `ecef_eci.html`

- **Purpose:**  
  Demonstrates the difference between ECEF (Earth-Centered, Earth-Fixed) and ECI (Earth-Centered Inertial) coordinate frames.
- **Features:**  
  - Draws ECEF axes and ECI axes.
  - Animates the ECI axes and the direction to first point of Aries.
  - Has camera rotate to make it seem if ECI is fixed, so that the globe rotates and stars are fixed.
  - Camera starts in a position to view both sets of axes.

## `ground_station.html`

- **Purpose:**  
  Simulates satellite communication with ground stations by visualizing satellite orbits and dynamically selecting the best ground station link in CesiumJS.

- **Features:**  
  - Propagates satellite orbits from TLE data using [satellite.js](https://github.com/shashwatak/satellite-js) and renders time-dynamic trajectories for LEO, MEO, and GEO satellites.
  - Displays a global network of ground stations and dynamically connects each satellite to the closest station with elevation ≥ 10°.
  - Computes and displays maximum communication bitrate in real time using user-adjustable link parameters (TX power, antenna gains, frequency, bandwidth, and noise).
  - Includes UI controls to follow satellites, adjust communication parameters, and visualize active communication links.

## `kepler_second_law.html`

- **Purpose:**  
  Visualizes Kepler’s Second Law (Equal Areas in Equal Times) by showing a satellite sweeping equal-area sectors around the focus of an elliptical orbit.

- **Features:**  
  - Generates an elliptical orbit using orbital parameters and solves Kepler’s Equation to compute satellite positions over time.
  - Displays the satellite, orbital path, and focus of the ellipse, representing the gravitational center.
  - Divides the orbit into equal time intervals, drawing alternating colored polygons that illustrate equal swept areas.
  - Uses an accelerated simulation clock and a top-down camera view to clearly demonstrate the relationship between orbital speed and distance from the focus.

## `satellite_gsd_cnn.html`

- **Purpose:**
  Simulates satellite imaging and onboard image processing by visualizing ground sample distance (GSD), sensor footprints, and tile-based CNN processing of captured imagery.

- **Features:**  
  - Propagates a satellite orbit from TLE data using [satellite.js](https://github.com/shashwatak/satellite-js) and visualizes the satellite and its ground track in Cesium.
  - Computes ground sample distance and dynamically renders the satellite imaging footprint on Earth based on altitude, focal length, pixel size, and sensor resolution.
  - Captures simulated image frames along the ground track and subdivides each frame into tiles representing sections of the image.
  - Models onboard CNN processing by sequentially processing tiles based on configurable compute throughput (GOPS) and operation counts, updating tile colors to indicate processing progress.

## `satellite_gsd.html`

- **Purpose:**
  Visualizes satellite imaging geometry by computing and displaying ground sample distance (GSD) and the corresponding ground footprint of a satellite sensor in Cesium.

- **Features:**
  - Propagates a satellite orbit from TLE data using [satellite.js](https://github.com/shashwatak/satellite-js) and visualizes the satellite and its ground track in Cesium.
  - Computes ground sample distance in real time using satellite altitude, sensor pixel size, focal length, and image resolution.
  - Displays the sensor footprint on the Earth’s surface as a dynamic rectangle representing the current imaging area.
  - Provides interactive controls to adjust sensor parameters and observe how changes affect GSD and ground coverage.

## `satellite_sun_visibility.html`

- **Purpose:**
  Visualizes whether satellites are illuminated by the Sun or in Earth’s shadow by computing the fraction of the Sun visible from each satellite.

- **Features:**
  - Propagates multiple satellites from TLE data (LEO, SSO, MEO, GEO) using [satellite.js](https://github.com/shashwatak/satellite-js) and renders their orbits in Cesium.
  - Computes the Sun’s position in the Earth-centered inertial (ECI) frame and evaluates Earth–Sun–satellite geometry.
  - Calculates the fraction of the Sun visible to the satellite to determine full sunlight, penumbra, or eclipse conditions.
  - Displays the real-time percentage of Sun visibility in each satellite’s label and allows the user to follow satellites using a dropdown selector.

## `sun_vector.html`

- **Purpose:**
  Demonstrates the direction of the Sun relative to a satellite by visualizing the Sun vector originating from the satellite in orbit.

- **Features:**
  - Propagates a satellite orbit using classical Keplerian orbital elements and solves Kepler’s equation to determine the satellite’s ECI position over time.
  - Computes the Sun’s geocentric position using an analytical solar ephemeris model and converts it to the Earth-centered Earth-fixed (ECEF) frame.
  - Draws a dynamic vector from the satellite pointing toward the Sun, updating continuously as the satellite moves along its orbit.
  - Displays the full orbit path and animates the satellite motion using Cesium’s timeline and clock for time-based visualization.

## Authors

- Tejas Vinod
