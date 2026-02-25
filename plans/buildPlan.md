# Driving Simulator — Build Plan

## Step 1: Create the Unity Project
**Who**: You (manual step in Unity Hub)

- Open Unity Hub → New Project → select **3D (URP)** template
- Set project location to `/Users/isaacwuest/Git/iosGame`
- Use Unity **2022.3 LTS** or newer
- Once created, go to File → Build Settings → select **iOS** → click **Switch Platform**
- Commit the initial Unity project files to the repo

**Done when**: You see the default Unity scene and the Assets folder exists in the repo.

---

## Step 2: Project Scaffolding
**Who**: Claude (I write this)

- Create folder structure inside Assets:
  - `Scripts/`, `Scenes/`, `Prefabs/`, `Materials/`, `Models/`, `UI/`
- Install required packages via Unity Package Manager:
  - **New Input System** — for touch controls
  - **Cinemachine** — for camera system
  - **TextMeshPro** — for UI text
- Write initial C# scripts and project configuration

**Done when**: Folders exist, packages are installed, project compiles with no errors.

---

## Step 3: Get a Car Moving (Core Milestone)
**Who**: Claude writes scripts, you test in Unity

This is the **most important step** — everything else builds on this.

- Create a placeholder vehicle (cube/box with 4 wheel colliders)
- Write `VehicleController.cs`:
  - Acceleration & braking
  - Steering with smooth turning
  - Physics-based movement using WheelColliders & Rigidbody
- Write `VehicleData.cs` (ScriptableObject):
  - Stats: max speed, acceleration, handling, weight
- Add touch controls:
  - Left side of screen = steering (tilt or virtual joystick)
  - Right side of screen = gas (bottom) & brake (top)
- Create a flat test plane to drive on

**Done when**: You can drive a placeholder car around a flat plane using touch controls and it feels responsive.

---

## Step 4: Camera System
**Who**: Claude writes scripts, you test in Unity

- Install & configure Cinemachine
- Write `CameraController.cs`:
  - **Third-person chase cam** — behind the vehicle, follows movement
  - **First-person cockpit cam** — driver's seat view
  - **Cinematic cam** — wider angle, dramatic view
- Add a UI button to cycle between camera views
- Smooth transitions between cameras

**Done when**: You can tap a button to switch between 3 camera angles while driving.

---

## Step 5: Menus & Character/Vehicle Selection
**Who**: Claude writes scripts & UI, you test

- **Main Menu Scene**:
  - Game title / logo
  - "Play" button
  - "Settings" button
- **Character Select Screen**:
  - Grid of 7 characters (Omar, Chris, Theodore, Joseph, Matthew, Adin, Liam)
  - Tap to select, highlight chosen character
  - "Next" button
- **Vehicle Select Screen**:
  - Shows only vehicles for the selected character
  - Carousel with vehicle preview & stats
  - "Select" button
- **Game Mode Select**:
  - Free Roam / Race / Obstacle Course
  - "Go" button to load gameplay scene
- Write `CharacterData.cs` (ScriptableObject) — name, avatar, vehicle list
- Write `CharacterSelectUI.cs` & `VehicleSelectUI.cs`
- Write `GameManager.cs` — manages game state & scene transitions

**Done when**: You can go from main menu → pick a character → pick a vehicle → select a mode → start playing.

---

## Step 6: Build the Map
**Who**: Collaborative (Claude sets up terrain scripts, you design in Unity editor)

- Create open world using **Unity Terrain**:
  - Roads & highways
  - Dirt paths & off-road areas
  - Water zones (lakes)
  - Snow zones
- Place environment objects:
  - Trees, rocks, fences
  - Buildings, barns, houses
  - Ramps, jumps, obstacles
- Add spawn points for different vehicle types
- Source assets from:
  - Unity Asset Store (free & paid)
  - Sketchfab
  - Or create simple low-poly assets

**Done when**: You have a driveable open world map with varied terrain and landmarks.

---

## Step 7: Game Modes
**Who**: Claude writes scripts, you test

### Free Roam
- No objectives, just drive & explore
- Stunt detection (air time, flips, speed)

### Racing
- Write `RaceManager.cs`:
  - Predefined race routes with checkpoint triggers
  - Countdown start (3, 2, 1, GO!)
  - Lap timer
  - AI opponents that follow race path
  - Finish line → results screen (position, time)

### Obstacle Courses
- Write `ObstacleCourseManager.cs`:
  - Timed runs through marked courses
  - Hazards (barriers, moving obstacles, tight turns)
  - Penalty time for hitting obstacles
  - Best time tracking

**Done when**: All 3 game modes are playable and functional.

---

## Step 8: Real Vehicle Models
**Who**: You source models, Claude integrates them

- Replace placeholder cubes with actual 3D vehicle models
- For each vehicle:
  - Import model into Unity
  - Set up wheel colliders to match wheel positions
  - Apply correct materials/colors (e.g., Omar's red Gallardo)
  - Create a VehicleData ScriptableObject with stats
  - Create a prefab
- Sources for models:
  - **Unity Asset Store** — search for car/truck packs
  - **Sketchfab** — free & paid models
  - **TurboSquid** — professional models
  - **Custom** — hire a 3D artist on Fiverr/Upwork

**Done when**: Each character has real-looking vehicles instead of placeholder boxes.

---

## Step 9: Polish & Effects
**Who**: Claude writes scripts, you tune in Unity

- **Sound effects**: engine revs, tire skids, collisions, UI clicks
- **Particle effects**: dust clouds, snow spray, exhaust, sparks
- **Vehicle effects**: headlights, tail lights, brake lights
- **HUD polish**: animated speedometer, smooth minimap
- **Screen shake** on big impacts
- **Music**: background tracks for menus & gameplay

**Done when**: The game feels and sounds like a polished product.

---

## Step 10: iOS Build & Release
**Who**: Collaborative

- Configure iOS build settings:
  - Set Bundle Identifier (e.g., `com.yourname.drivingsimulator`)
  - Configure signing with Apple Developer account
  - Set app icons & splash screen
- **Optimize for mobile**:
  - LOD (Level of Detail) on distant objects
  - Draw call batching
  - ASTC texture compression
  - Target 30+ FPS on iPhone 12+
- **Test on device**:
  - Build to Xcode → deploy to real iPhone
  - Test all game modes, vehicles, UI
  - Profile performance & fix bottlenecks
- **App Store submission**:
  - Screenshots & preview video
  - App description & metadata
  - Submit for review

**Done when**: The game is live on the App Store!

---

## Summary Timeline
| Step | What | Priority |
|------|------|----------|
| 1 | Create Unity project | **Start here** |
| 2 | Scaffold folders & packages | Immediate |
| 3 | Get a car driving | **Critical** |
| 4 | Camera system | High |
| 5 | Menus & selection | High |
| 6 | Build the map | Medium |
| 7 | Game modes | Medium |
| 8 | Real vehicle models | Medium |
| 9 | Polish & effects | Low |
| 10 | iOS build & release | Final |
