# Tech Stack

## Engine
- **Unity 3D** (URP — Universal Render Pipeline)
- **Unity Version**: 2022.3 LTS or newer
- **Language**: C#

## Target Platform
- **iOS** (iPhone & iPad)
- Xcode required for building & deploying

## Required Unity Packages
| Package | Purpose |
|---------|---------|
| Universal RP | Optimized rendering for mobile |
| New Input System | Touch controls (steering, gas, brake) |
| Cinemachine | Switchable camera system |
| TextMeshPro | UI text rendering |

## Physics
- **WheelColliders** for car/truck physics
- **Rigidbody** for vehicle mass, drag, and collisions
- Custom physics for different vehicle types (dirt bikes, snowmobiles, quads)

## Architecture
| Script | Role |
|--------|------|
| `VehicleController.cs` | Core driving mechanics (acceleration, braking, steering) |
| `VehicleData.cs` | ScriptableObject — vehicle stats (speed, handling, weight) |
| `CameraController.cs` | Cinemachine virtual camera switching |
| `CharacterData.cs` | ScriptableObject — character info & vehicle list |
| `CharacterSelectUI.cs` | Character selection screen logic |
| `VehicleSelectUI.cs` | Vehicle selection screen logic |
| `GameManager.cs` | Game state, mode selection, scene management |
| `RaceManager.cs` | Race logic (checkpoints, timers, AI opponents) |
| `ObstacleCourseManager.cs` | Obstacle course logic (timed runs, hazards) |

## 3D Assets
- Starting from scratch — no existing models
- Options: Unity Asset Store, free assets, or custom models
- Vehicle models needed: cars, trucks, dirt bikes, quads, snowmobiles

## Version Control
- **Git** + **GitHub**
- Repo: `/Users/isaacwuest/Git/iosGame`
- Unity `.gitignore` already configured

## iOS Build Requirements
- Apple Developer Account
- Xcode (latest stable)
- Signing certificates & provisioning profiles
- Bundle ID configuration
- Performance targets: 30+ FPS on iPhone 12 and newer

## Performance Optimization
- LOD (Level of Detail) for distant objects
- Draw call batching
- Texture compression (ASTC for iOS)
- Object pooling for repeated elements
- Occlusion culling for open world
