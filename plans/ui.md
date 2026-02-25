# UI Design

## Screen Flow
```
Splash Screen
    ↓
Main Menu
    ↓
Character Select → Vehicle Select → Game Mode Select
    ↓
Gameplay (with HUD)
    ↓
Results / Back to Menu
```

## Screens

### Splash Screen
- CboysTv logo / game title
- "Tap to Start"

### Main Menu
- Play button
- Settings button
- Credits button

### Character Select
- Grid or horizontal scroll of all 7 CboysTv members
- Each character shown with name and avatar/image
- Highlight selected character
- "Next" button to proceed to vehicle select

### Vehicle Select
- Shows only vehicles available for the selected character
- Horizontal carousel of vehicles
- Each vehicle shows:
  - 3D preview or image
  - Vehicle name
  - Stats (speed, handling, weight)
- "Select" button to confirm

### Game Mode Select
- Free Roam
- Race
- Obstacle Course
- Brief description under each mode
- "Go" button to start

### In-Game HUD
- **Speedometer** — bottom right, circular gauge
- **Minimap** — top right corner
- **Timer** — top center (races & obstacle courses only)
- **Position** — top center (races only, e.g., "2nd / 4")
- **Pause button** — top left
- **Camera switch button** — bottom left or top right

### Pause Menu
- Resume
- Restart
- Settings
- Quit to Menu

### Race Results
- Final position / time
- "Retry" button
- "Back to Menu" button

## Touch Controls (In-Game)
```
┌─────────────────────────────────┐
│ [Pause]     Timer      [Camera] │
│                        Minimap  │
│                                 │
│                                 │
│                                 │
│                                 │
│  ← STEER →          [BRAKE]    │
│  (left side)         [GAS]     │
│                   (right side)  │
└─────────────────────────────────┘
```
- **Left side of screen**: tilt or virtual joystick for steering
- **Right side of screen**: gas pedal (bottom) and brake (above it)
- Tap anywhere to toggle camera (or dedicated button)

## Notifications / Popups
- Countdown before race start (3, 2, 1, GO!)
- Checkpoint passed
- Lap completed
- New best time
