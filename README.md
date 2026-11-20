# Five-Scene 3D Gaussian Splatting Walkability Dataset

This dataset contains five synthetic indoor scenes and their associated Gaussian reconstructions, reconstructed geometry, and reference and predicted walkable surfaces. The original scene geometry provides an independent reference for evaluating walkability recovered from reconstructed scenes.

## Downloads

The complete supplementary dataset is provided through the `dataset-v1` GitHub release. The dataset is divided into five scene archives (`Scene01.zip` to `Scene05.zip`) for convenient downloading.

The release also includes `FiveScenes_Quest.apk`, a standalone Meta Quest build for demonstrating the reconstructed scenes and walkable navigation.

## Dataset contents

| Component | Included | Location |
|---|:---:|---|
| Original Three.js scene | ✓ | `Threejs file/` |
| CoR-GS reconstruction and associated assets | ✓ | `CoR-GS/` |
| SparseSurf reconstruction, depth, alpha, RGB and camera metadata | ✓ | `SparseSurf/` |
| TSDF surface, collision and floor geometry | ✓ | `TSDF output/` |
| Reference walkable surface (original scene geometry) | ✓ | `Reference walkable obj/` |
| Predicted walkable surface (reconstructed geometry) | ✓ | `Predicted walkable obj/` |

## Directory structure

The following is the directory structure shown for **Scene01**. The other scenes use their corresponding scene identifiers.

```text
Scene01/
├── CoR-GS/
│   ├── images/
│   ├── iteration_30000/
│   ├── MVS/
│   ├── sparse/
│   └── transforms_train.json
├── Predicted walkable obj/
│   └── scene01_walkable_surface.obj
├── Reference walkable obj/
│   └── scene01_reference_walkable.obj
├── SparseSurf/
│   ├── alpha/
│   ├── depth/
│   ├── rgb/
│   ├── manifest.json
│   ├── scene01_baseline_r1_7000.ply
│   └── training_cameras.json
├── Threejs file/
│   └── Scene01_reference.html
└── TSDF output/
    ├── floor_report.json
    ├── scene01_floor_collision.obj
    ├── scene01_tsdf_collision.obj
    ├── scene01_tsdf_surface.ply
    ├── scene01_walkable_surface.obj
    ├── tsdf_report.json
    └── walkable_report.json
```

## Reference and predicted walkability

- **Reference walkable surface:** `Reference walkable obj/` contains the walkable geometry derived from the original Three.js scene, independently of the reconstruction.
- **Predicted walkable surface:** `Predicted walkable obj/` contains the walkable geometry obtained from the SparseSurf depth-based reconstruction and TSDF processing.

The two OBJ surfaces are provided in the scene's coordinate frame for direct geometric comparison. The predicted surface also appears in `TSDF output/` as part of the geometry-processing outputs.
