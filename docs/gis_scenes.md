# GIS Scenes
If you are looking to use one of our geo-specific scenes, provided that you have the needed glb/glTF tiles, you only have to make two changes.

In the **[Scene Configuration](config_scene.md)**, you will need to set the "scene-type" and "tiles-dir" parameters:
1. For GIS environments, **scene-type** should be set to **CustomGIS**.

## Cesium for Unreal

A local [3D Tiles](https://github.com/CesiumGS/3d-tiles) tileset can be loaded with the [Cesium for Unreal](https://cesium.com/platform/cesium-for-unreal/) plugin. It is **disabled by default**; to enable it, install the plugin, add `PublicDefinitions.Add("ENABLE_CESIUM=1");` and `"CesiumRuntime"` (in `PrivateDependencyModuleNames`) to `ProjectAirSim.Build.cs`, add `{ "Name": "CesiumForUnreal", "Enabled": true }` to `ProjectAirSim.uplugin`, and rebuild.

Set **scene-type** to **CesiumGIS** and **tiles-dir** to the directory containing `tileset.json` (or the root tileset json file).

The `CesiumGeoreference` origin is set to **home-geo-point** and rotated 90 degrees in yaw so that Unreal +X points North (NED).
