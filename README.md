# Blender Datasmith Export Plugin

This is a fork of the original [Blender Datasmith Export Plugin](https://github.com/0xafbf/blender-datasmith-export) by Andrés Botero. The plugin has been ported to work with Blender 4.5 and has been tested with Unreal Engine 5.6.

## Updates Made

1. **Compatibility with Blender 4.5**: The plugin has been updated to work with Blender 4.5, ensuring that it can be used with the latest version of Blender.
2. **Compatibility with Unreal Engine 5.6**: The plugin has been tested with Unreal Engine 5.6 to ensure that it works seamlessly with the latest version of Unreal Engine.
3. **Bug Fixes and Improvements**: Various bug fixes and improvements have been made to ensure that the plugin works correctly and efficiently.

## Installation

1. Download the latest release of the plugin from the [releases page](https://github.com/tankshield/Datasmith2Blender/releases).
2. Open Blender and go to `Edit > Preferences > Add-ons > Install`.
3. Select the downloaded zip file and click `Install Add-on`.
4. Enable the addon by checking the box next to `Unreal Datasmith format`.

## Usage

1. Open Blender and create or import a scene that you want to export to Unreal Engine.
2. Go to `File > Export > Datasmith (.udatasmith)`.
3. Choose the location and name for the exported file and click `Export Datasmith`.

## Testing

This plugin has been tested with Blender 4.5 and Unreal Engine 5.6. If you encounter any issues, please report them on the [issues page](https://github.com/tankshield/Datasmith2Blender/issues).

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Features

* **Meshes** with normals, vertex colors, and up to 8 UV channels.
* **Hierarchy** is exported, keeping mesh references, transforms, parents, and per-instance material overrides from Blender.
* **Textures and materials** are exported using data from the shader graphs. Materials are closely approximated, and a good amount of nodes are supported (math, mix, fresnel, vertex color, and others).
* **Cameras** are exported, trying to match Blender data, keeping focus distance, focal length, and aperture.
* **Lights** are exported, keeping their type, power, color, and size data.
* **Reflection probes** including Planar, Sphere, and Box captures.

## Sample

You can click the images to open a large preview.

**Blender Eevee:**

<img alt="Blender Eevee render" src="docs/blender.jpg" width="300">

**UE4 using Datasmith:**

<img alt="UE4 render" src="docs/unreal.jpg" width="300">

This result relies on the **DatasmithBlenderContent**, which is a UE4 Plugin that improves material import compatibility. Consider supporting the project by purchasing it from [here][gumroad] (Epic Games store support will be added later).

[gumroad]: https://gum.co/DQvTL

This result is in a custom UE4 build, which fixes some issues of the UE4 importer. If you are technical to compile the engine, you can check the fork [here][ue4 fork]. Hopefully, we can get to integrate our fixes into the main branch.

[ue4 fork]: https://github.com/0xafbf/UnrealEngine/tree/master

## Frequently Asked Questions

**Q: Does this support weighted normals/smoothing groups?**

A: Yes, but the plugin is unable to triangulate correctly. For the time being, you can add a `Triangulate` modifier with the `Keep Normals` option to work around this.

**Q: Why are some material nodes not exported?**

A: Most of the nodes are exported, but not all of them are imported from the UE4 side. The Datasmith Blender Additions (mentioned above) improves this by adding implementations for some of these nodes. There is a [list of nodes in the wiki] with more information on which nodes are supported, and which require the UE4 plugin to work.

[list of nodes in the wiki]: https://github.com/0xafbf/blender-datasmith-export/wiki/Supported-Material-Nodes

**Q: What is this "custom build" you talked about earlier?**

A: I modified some of the UE4 build to fix a couple of errors when importing the scenes generated from Blender. These are related to normal maps import and very specific import issues with lights. If you're interested, you can check this [custom build discussion].

[custom build discussion]: https://github.com/0xafbf/blender-datasmith-export/issues/25

If you want to support the project, consider supporting via [Patreon].

[patreon]: https://www.patreon.com/0xafbf

Please, [join the project Discord][join_discord] and share your results! I want to see what you make and I am open to any feedback you have.

[join_discord]: https://discord.gg/NJt5ADJ
