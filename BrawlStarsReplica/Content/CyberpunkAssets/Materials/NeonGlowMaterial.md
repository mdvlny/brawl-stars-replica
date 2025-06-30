# Neon Glow Material Configuration

## Material Setup for Anime Cyberpunk Aesthetic

### Base Material Properties
- **Material Domain**: Surface  
- **Blend Mode**: Translucent
- **Shading Model**: Unlit (for maximum glow effect)

### Key Parameters
1. **Neon Color** (Vector Parameter)
   - Default: RGB(0, 1, 1) - Cyan
   - Variants: Pink (1, 0, 0.5), Purple (0.5, 0, 1), Green (0, 1, 0.3)

2. **Glow Intensity** (Scalar Parameter)  
   - Range: 0.0 - 10.0
   - Default: 3.0
   - Mobile Optimized: 1.5-2.0

3. **Pulse Speed** (Scalar Parameter)
   - Range: 0.0 - 5.0  
   - Default: 1.0
   - Creates breathing/pulsing effect

4. **Fresnel Power** (Scalar Parameter)
   - Range: 0.5 - 5.0
   - Default: 2.0
   - Controls edge glow falloff

### Node Network (Simplified)
```
Time -> Sine -> Multiply(Pulse Speed) -> Add(1.0) -> Multiply(0.5)
  |
  v
Multiply(Glow Intensity) -> Multiply(Neon Color) -> Emissive Color

Fresnel(Power=Fresnel Power) -> Multiply(Glow Intensity) -> Opacity
```

### Mobile Optimization
- Use simplified node networks
- Reduce texture samples
- Use vertex colors for color variation
- Implement LOD system for distant objects

### Usage Examples
- Character weapon highlights
- UI button borders  
- Environmental accent lighting
- Projectile trails
- Character ability effects

### Performance Notes
- Translucent materials are expensive on mobile
- Use sparingly for key visual elements
- Consider using Additive blend mode for better performance
- Implement distance-based culling