# Catenary Cable Calculator

A web-based calculator for analyzing suspended cable behavior using catenary physics. This tool helps engineers and technicians calculate cable sag, droop, tension, and length for overhead cable installations.

## What is a Catenary?

A catenary is the curve that a flexible cable or chain assumes when supported at its ends and acted upon by gravity. Unlike a parabola, the catenary curve is described by the hyperbolic cosine function and accurately models real-world cable behavior.

## Features

- **Real-time Calculations**: Interactive inputs with instant results
- **Visual Profile**: Dynamic chart showing the cable curve, line of sight, and measurement point
- **Comprehensive Results**:
  - Cable height at any measurement point
  - Droop below line of sight
  - Tension at both endpoints
  - Total cable length
  - Maximum droop point
- **Responsive Design**: Works on desktop and mobile devices

## Usage

Simply open `index.html` in a web browser. No installation or build process required.

### Input Parameters

1. **Total Horizontal Distance** (ft): The horizontal span between support points A and B
2. **Elevation Gain** (ft): The vertical height difference (positive if endpoint B is higher than A)
3. **Cable Weight** (lb/1000ft): The linear weight density of the cable
4. **Horizontal Tension** (lbf): The constant horizontal component of cable tension
5. **Measurement Distance from A** (ft): Where along the span to calculate droop

### Outputs

- **Cable Height**: Absolute vertical position of the cable at the measurement point
- **Line of Sight Height**: Height of the straight line between endpoints at the measurement point
- **Droop**: How far the cable sags below the line of sight (key metric)
- **Tension @ A/B**: Total tension force at each endpoint
- **Cable Length**: Actual length of the cable (always greater than horizontal span)
- **Max Droop**: The maximum sag anywhere along the span

## Physics

The calculator solves the catenary equation:

```
y = a × cosh((x - x₀)/a) + c
```

Where:
- `a = H/w` is the catenary parameter (H = horizontal tension, w = weight per unit length)
- `x₀` is the horizontal offset (solved using Newton-Raphson iteration)
- `c` is the vertical offset (calculated from boundary conditions)

The solver uses numerical methods to find the catenary curve that passes through both support points given the cable weight and tension.

## Use Cases

- Power line installation planning
- Communication cable design
- Bridge cable analysis
- Overhead wire systems (railways, trolleys)
- Guy wire calculations
- Zip line design

## Technical Details

- Pure HTML/CSS/JavaScript - no dependencies except Chart.js
- Uses Chart.js 4.4.1 for visualization
- Newton-Raphson iteration for solving the catenary equation
- Responsive grid layout with CSS Grid

## Example Scenarios

**Default Example**: A 1000 ft span with 200 ft elevation gain, using 29 lb/1000ft cable at 340 lbf tension. At 190 ft from point A, the calculator shows the droop and cable position.

**Flat Span**: Set elevation gain to 0 to analyze a level cable run.

**Steep Grade**: Increase elevation gain to see how slope affects droop and tension distribution.

## License

This is a standalone calculator tool with no external dependencies beyond Chart.js (MIT licensed).
