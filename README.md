# Python-Raytracer-V2.0
To use the raytracer, just run the pyton script "Raytracer.py". It will render the picture, ask you how you want to name it, and save it in the "Results" directory.

To change the settings and the scene, you have to modify the python script "Raytracer.py":

Resolution:
modify the variables "Width" and "Height" at line 85. These values represent the width and the height of the picture in number of pixels.

Objects:
add or remove elements to the array named "Objects" at line 91. You need to add objects from the class that are defined in the script "objects_class.py": Sphere, Plane, and Triangle (ImportedOBJ is not finished)

Camera:
to modify the camera position and rotation (rotation is glitched and gives strange results), you have to modify the dict named "Camera" at the line 88. the value "position" and "rotation" have to be Vectors.

Parameters:
the dict "Parameters" at line 83 contains the other parameters:
"maxReflection" is the maximum number of reflection rays. Higer values will result in higer render time.
"indirectLightingMaxBounces" is the maximum number of bounces when calculating the indirect lighting. High values can more precise, but not so visible and will really increase the render time.
"indirectLightingSamples" is the number of samples to compute indirect lighting. Higher values will reduce noise, but also increase render time.
"Lighting" is the type of lighting:
	"Direct" will only render the direct lighting (with shadows).
	"Indirect" willl only render the indirect lighting.
	"All" will render all the lighting.
	"Ambient" and "Diffuse" will only render the ambient or diffuse color (diffuse become darker in function of the angle between the 		normal and the light).
	"Specular" will only render the specular.

The maximum number of rays traced for one pixel is equal to: maxReflection * (indirectLightingSamples ^ maxIndirectLightingBounces)

