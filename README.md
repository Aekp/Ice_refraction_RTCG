# Ice Refractions

This project demonstrates the creation of a shader in Unity that simulates light refraction through ice, using Shader Graph and the Universal Render Pipeline (URP). The shader provides a visually appealing approximation of light bending as it passes through an ice surface.

## Getting Started

To use this shader, ensure you are using the Universal Render Pipeline and have Shader Graph installed through the Unity Package Manager. Start with the URP default scene and place the provided ice meshes over the landscape.

### Prerequisites

- Unity Editor with URP and Shader Graph installed
- Ice mesh (included in the GitHub repository)

### Installation

1. Clone the repository or download the provided assets.
2. Open the project in Unity.
3. Navigate to `Project Settings > Graphics` and ensure that `Opaque Texture` and `Depth Texture` are enabled.

## Shader Creation

Create a new PBR Graph by right-clicking in the Project view and selecting `Create > Shader > PBR Graph`. Name it `Ice`.

### Texture and Normals

- Add a `Texture2D` property called `Ice Normals` and set the mode to `Bump`.
- Use a `Vector2` property called `Ice Tiling` to control the texture tiling across the mesh.

### Refraction Effect

- Add a `Vector1` property called `Refract Strength` as a slider to control the refraction intensity.
- Use the `Scene Color` node to fetch what's already been rendered behind the ice.
- Multiply the normals by `Refract Strength` and add them to the screen position to distort the scene texture.

### Visual Enhancements

- Add a `Color` property named `Ice Color` and set it to HDR mode for a blue tint.
- Introduce `Fresnel` to the shader with a `Vector1` property called `Fresnel Strength` to simulate reflectivity at shallow angles.

### Final Touches

- Connect the normal texture to the `Normal` pin on the PBR Master node.
- Change the material's rendering mode to `Transparent` to ensure proper rendering of the refraction effect.

## Usage

Select the ice material in the editor and change its shader to the `Ice` shader created with Shader Graph. Adjust the `Refract Strength` to see the refraction effect in action.


Enjoy creating your icy scenes!
