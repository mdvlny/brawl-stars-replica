# Holographic UI Design Guide

## Anime Cyberpunk UI Framework

### Design Principles
1. **Translucent Elements**: Semi-transparent backgrounds with subtle glow
2. **Neon Borders**: Bright cyan/pink outlines with soft edges  
3. **Anime Typography**: Clean, futuristic fonts with slight glow
4. **Holographic Effects**: Scanlines, noise, and interference patterns
5. **Interactive Feedback**: Glow intensity changes on hover/press

### Color Scheme
```css
Primary: #00FFFF (Cyan)
Secondary: #FF0080 (Hot Pink) 
Accent: #FF1493 (Deep Pink)
Background: #0D1B2A (Dark Blue)
Text: #FFFFFF (White) with glow
Disabled: #4A5568 (Gray)
```

### UI Components

#### 1. Main Menu Buttons
- **Background**: Translucent dark blue (Alpha: 0.7)
- **Border**: 2px neon cyan glow
- **Text**: White with cyan drop shadow
- **Hover Effect**: Increased glow + scale 1.05x
- **Press Effect**: Pulse animation + brief color shift

#### 2. Character Selection Cards
- **Layout**: Vertical card with character portrait
- **Background**: Gradient from transparent to dark
- **Border**: Animated neon border (cycling colors)
- **Character Portrait**: Anime-style with glow effects
- **Selection State**: Bright pink border + increased scale

#### 3. HUD Elements
- **Health Bar**: Neon green with red damage overlay
- **Mana/Energy**: Electric blue with pulse effect
- **Mini-map**: Circular with scanning line animation
- **Score Display**: Large holographic numbers

#### 4. In-Game UI
- **Attack Button**: Circular with weapon icon, red glow
- **Ultimate Button**: Hexagonal with charging animation
- **Joystick**: Translucent with neon trail
- **Menu Button**: Three-line icon with cyan glow

### Animation Patterns

#### Glow Pulse Animation
```
Duration: 2 seconds
Keyframes:
  0%: opacity 0.5, scale 1.0
  50%: opacity 1.0, scale 1.02  
  100%: opacity 0.5, scale 1.0
```

#### Scanning Line Effect
```
Duration: 3 seconds (loop)
Movement: Top to bottom sweep
Color: Bright cyan (Alpha: 0.8)
Blur: 5px gaussian
```

#### Button Press Feedback
```
Duration: 0.2 seconds
Scale: 0.95x → 1.05x → 1.0x
Glow: +50% intensity
Color: Brief shift to pink
```

### Mobile Optimization

#### Performance Considerations
- Use UI materials instead of post-process effects
- Limit simultaneous glow effects to 5-8 elements
- Implement simple fallbacks for older devices
- Use texture atlases for UI icons

#### Touch-Friendly Design
- Minimum button size: 44x44 points
- Clear visual feedback for all interactions
- Larger target areas than visual elements
- Appropriate spacing between interactive elements

### Implementation Notes

#### UMG Widget Setup
1. Create base widget class for holographic styling
2. Use material parameters for dynamic color changes
3. Implement consistent animation blueprints
4. Create reusable components for common elements

#### Material Setup
- Base UI material with glow parameters
- Separate materials for different glow colors
- Simple fallback materials for low-end devices
- Masked materials for complex shapes

### Accessibility Features
- High contrast mode option
- Reduced motion settings
- Colorblind-friendly alternatives
- Scalable UI elements

### File Structure
```
/Content/UI/CyberpunkTheme/
  ├── Materials/
  │   ├── M_UI_Holographic_Base
  │   ├── M_UI_Neon_Glow
  │   └── M_UI_Button_Variants
  ├── Widgets/
  │   ├── W_MainMenu
  │   ├── W_CharacterSelect
  │   ├── W_GameHUD
  │   └── W_Settings
  ├── Animations/
  │   ├── A_GlowPulse
  │   ├── A_ScanningLine
  │   └── A_ButtonPress
  └── Textures/
      ├── T_Noise_Pattern
      ├── T_Scanlines
      └── T_UI_Icons_Atlas
```