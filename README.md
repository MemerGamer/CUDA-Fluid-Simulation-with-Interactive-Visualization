# CUDA Fluid Simulation with Interactive Visualization

A real-time fluid dynamics simulation implemented in Python using CUDA for GPU acceleration, featuring interactive ASCII visualization and automated movement patterns.

## ✨ Features

### 🚀 High-Performance Computing
- **CUDA GPU Acceleration**: Leverages GPU parallel processing for real-time fluid simulation
- **80x80 Grid Resolution**: High-resolution simulation with 6,400 fluid cells
- **Real-time Physics**: Implements a stable, semi-Lagrangian approximation of the Navier-Stokes equations for incompressible fluids

### 🎮 Interactive Controls
- **Manual Control**: Arrow keys and buttons for cursor movement
- **Force Application**: Add directional forces and density sources
- **Multiple Input Methods**: Button interface + keyboard shortcuts
- **Real-time Interaction**: Immediate response to user input

### 🎨 Advanced Visualization
- **Three Display Modes**:
  - **Density Mode**: Blue gradient showing fluid concentration
  - **Velocity Mode**: Rainbow arrows showing flow direction and speed
  - **Combined Mode**: Dynamic switching between density and velocity visualization
- **Enhanced Color Schemes**: 10+ color gradients for better visual clarity
- **ASCII Art Rendering**: Monospace character-based fluid representation

### 🎬 Automated Animations
- **6 Movement Patterns**:
  - 🎲 **Random Walk**: Chaotic Brownian motion with random forces
  - 🌀 **Spiral**: Expanding spiral with tangential forces
  - ∞ **Figure-8**: Smooth parametric figure-eight pattern
  - ⚽ **Bouncing Ball**: Physics-based collision simulation
  - 🌪️ **Vortex Dance**: Multiple moving vortices interaction
  - 🎯 **Random Pattern**: Randomly selected pattern
- **100 Frame Sequences**: Extended animations for pattern analysis

## 🔧 Technical Implementation

### Physics Engine
```
Navier-Stokes Equations Implementation:
- Velocity diffusion with viscosity
- Density advection and diffusion  
- Pressure projection for incompressibility
- Boundary condition enforcement
```

### CUDA Kernels
- `add_source`: Density injection
- `diffuse`: Heat equation solver
- `advect`: Semi-Lagrangian advection
- `project`: Pressure Poisson solver
- `apply_force`: Force field application
- `clear_fields`: Memory reset

### Memory Management
- GPU memory allocation for all field variables
- Efficient device-to-host transfers
- Automatic cleanup on exit

## 🎮 Controls Reference

### Keyboard Shortcuts
| Key | Action |
|-----|--------|
| `↑↓←→` | Move cursor & add directional force |
| `Space` | Add density at cursor position |
| `S` | Single simulation step |
| `A` | Toggle auto-update mode |
| `C` | Clear simulation (reset all fields) |
| `M` | Cycle through display modes |

### Button Interface
- **Navigation**: Arrow buttons for precise movement
- **Simulation Control**: Step, Auto, Clear, Mode, Quit
- **Force Control**: Directional forces and density injection
- **Animation Control**: 6 automated movement patterns

## 📊 Display Modes

### 1. Density Mode 💧
- **Purpose**: Visualize fluid concentration and distribution
- **Colors**: Blue gradient (dark blue → light blue → yellow → orange → red)
- **Characters**: ` .·:;!|▪▫▪■` (increasing density)

### 2. Velocity Mode 🌊  
- **Purpose**: Show flow direction and speed
- **Colors**: Rainbow gradient (green → yellow → orange → red)
- **Characters**: Directional arrows `→↘↓↙←↖↑↗`

### 3. Combined Mode 🌀
- **Purpose**: Dynamic visualization switching
- **Logic**: Shows velocity arrows when flow > threshold, otherwise density
- **Benefit**: Comprehensive fluid state visualization

## 🎬 Animation Patterns

### Random Walk 🎲
- **Behavior**: Chaotic movement with random directional forces
- **Physics**: Brownian motion simulation
- **Parameters**: Random force magnitude (1.0-3.0), density (20-60)

### Spiral 🌀
- **Behavior**: Expanding spiral with tangential forces
- **Mathematics**: $r \space = \space frame \cdot 0.1$, $\spaceθ = frame \cdot 0.3$
- **Forces**: Perpendicular to radius for circulation

### Figure-8 ∞
- **Behavior**: Smooth parametric motion
- **Mathematics**: $x \space = \space scale \cdot \sin(t)$, $\space y \space = \space scale \cdot \sin(t) \cdot \cos(t)$
- **Pattern**: Classical Lissajous curve

### Bouncing Ball ⚽
- **Behavior**: Physics-based collision with walls
- **Features**: Velocity damping, realistic bouncing
- **Physics**: Elastic collision with energy loss

### Vortex Dance 🌪️
- **Behavior**: Three moving vortices creating complex flow
- **Pattern**: Orbital motion with phase shifts
- **Interaction**: Multiple vortex interference patterns

## 🔬 Scientific Applications

### Fluid Dynamics Research
- **Educational Tool**: Visualize Navier-Stokes equation solutions
- **Pattern Analysis**: Study vortex formation and decay
- **Boundary Effects**: Observe wall interaction effects

### Computational Methods
- **GPU Programming**: CUDA kernel optimization examples
- **Numerical Methods**: Finite difference schemes
- **Real-time Simulation**: Interactive parameter exploration

## 🚀 Performance Specifications

### System Requirements
- **GPU**: CUDA-compatible graphics card
- **Memory**: 2GB+ GPU memory recommended
- **Software**: Python 3.7+, PyCUDA, Jupyter/Colab

### Performance Metrics
- **Grid Size**: 80×80 = 6,400 cells
- **Update Rate**: ~5-10 FPS (depending on hardware)
- **Memory Usage**: ~50MB GPU memory
- **Precision**: 32-bit floating point

## 🔮 Future Enhancements

### Potential Improvements
- [ ] 3D visualization support
- [ ] Variable viscosity and diffusion
- [ ] Particle tracking overlay
- [ ] Video export functionality
- [ ] Real-time parameter adjustment
- [ ] Multiple fluid interaction
- [ ] Texture rendering options

### Advanced Features
- [ ] Lattice Boltzmann method
- [ ] Free surface tracking
- [ ] Heat transfer simulation
- [ ] Magnetic field effects

## 📚 References

### Scientific Background
- **Navier-Stokes Equations**: Foundation of fluid dynamics
- **Jos Stam's Method**: "Real-Time Fluid Dynamics for Games" (1999)
- **Semi-Lagrangian Advection**: Stable numerical scheme
- **Pressure Projection**: Helmholtz-Hodge decomposition

### Implementation Resources
- **CUDA Programming**: NVIDIA CUDA Toolkit Documentation
- **Numerical Methods**: "Numerical Recipes" computational techniques
- **Interactive Visualization**: Jupyter widgets and HTML5
