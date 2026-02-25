# Driving Simulator — iOS Game

## Game Overview
A 3D open-world driving simulator for iOS. Each character has their own set of vehicles to choose from. Built in Unity, targeting iOS.

### Gameplay
- **Free Roam** — drive anywhere, do stunts, explore
- **Racing** — checkpoint-based races on predefined routes, AI opponents
- **Obstacle Courses** — timed courses with jumps, turns, hazards

### Camera
- Switchable camera angles like GTA (third-person chase, first-person cockpit, cinematic)
- Tap button to cycle views
- Smooth transitions

### Setting
- Open world with roads, off-road areas, water, snow zones
- Rural countryside / small-town vibe

---

## Characters & Vehicles

### Omar
- Lamborghini Gallardo (red)
- Stark dirt bike (Cheeto wrap)
- Ford Raptor R (red)
- El Camino (red, gold wheels)

### Chris
- Nissan GTR (white)
- Ford Raptor R (black)
- Quads
- Snowmobiles

### Theodore
- *Awaiting info*

### Joseph
- *Awaiting info*

### Matthew
- *Awaiting info*

### Adin
- *Awaiting info*

### Liam
- *Awaiting info*

---

## Technical Plan

### Project Setup
- **Engine**: Unity 3D (URP template)
- **Unity Version**: 2022.3 LTS or newer
- **Platform**: iOS
- **Repo**: `/Users/isaacwuest/Git/iosGame`
- **Current state**: Repo has only a `.gitignore` — Unity project needs to be created

#### User must do in Unity Hub:
1. Open Unity Hub → New Project → select "3D (URP)" template
2. Set project location to `/Users/isaacwuest/Git/iosGame`
3. Unity version: 2022.3 LTS or newer
4. Switch build target to iOS (File → Build Settings → iOS → Switch Platform)

#### Folder Structure
```
Assets/
  Scripts/
  Scenes/
  Prefabs/
  Materials/
  Models/
  UI/
```

#### Required Packages
- New Input System (touch controls)
- Cinemachine (camera system)

### Core Scripts
| Script | Purpose |
|--------|---------|
| `VehicleController.cs` | Physics-based driving (acceleration, braking, steering) using WheelColliders |
| `VehicleData.cs` | ScriptableObject for vehicle stats (speed, handling, weight, type) |
| `CameraController.cs` | Cinemachine switchable virtual cameras |
| `CharacterData.cs` | ScriptableObject per character (name, avatar, vehicle list) |
| `CharacterSelectUI.cs` | Character selection screen |
| `VehicleSelectUI.cs` | Vehicle selection (filtered by chosen character) |

### Vehicle Types
- Cars (sports cars, muscle cars)
- Trucks (Raptors, etc.)
- Dirt bikes
- Quads / ATVs
- Snowmobiles
- Touch controls: left side = steering, right side = gas/brake

### UI Flow
Main Menu → Character Select → Vehicle Select → Game Mode Select → Play

### In-Game HUD
- Speedometer
- Minimap
- Timer (for races/courses)
- Pause menu

### iOS Build
- Configure bundle ID & signing
- Optimize for mobile (LOD, draw call batching)
- Touch input tuning
- Sound effects & music

---

## Build Order
1. User creates Unity project in Unity Hub (manual step)
2. Scaffold folder structure + install packages
3. Build vehicle controller + placeholder car
4. Build camera system
5. Build character/vehicle selection
6. Build a test map
7. Add game modes
8. Polish & iOS build

## Verification
- Test vehicle driving on a flat plane first
- Test camera switching
- Test character → vehicle selection flow
- Test on iOS Simulator, then real device
- Profile performance on device
