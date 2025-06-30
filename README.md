# 🎮 Character Controller Setup Tool for Unity

This Unity Editor tool simplifies the process of setting up a fully functional third-person character controller with animations, camera, and movement logic.

## ✨ Features

- One-click setup of player controller
- Adds essential components: `CharacterController`, `Animator`, `AdvancedPlayerController`
- Auto-generates Animator Controller with Idle, Walk, Run, Jump, and Fall states
- Ground check system
- Third-person camera with customizable follow behavior
- Easy-to-extend controller script for crouch, climb, swim, etc.

## 🚀 Setup Instructions

### 1. Select Your Player Model
- Choose a **3D GameObject** in your Unity hierarchy.

### 2. Run the Setup Tool
- Go to `Tools > Character Setup > Setup Player Controller` in the Unity menu.
- The tool will:
  - Add a `CharacterController` (if not already present)
  - Attach the `AdvancedPlayerController` script
  - Add an `Animator` and auto-create an Animator Controller
  - Set up a ground check system
  - Attach a third-person follow camera

## ⚙️ Ground Check Configuration

1. Create an empty GameObject under your player model.
2. Name it `GroundCheckPoint`.
3. Assign it to the **GroundCheckPoint** field in `AdvancedPlayerController`.

## 🧱 Ground Layer Setup

1. Create a new Layer named `Ground`.
2. Assign all ground objects to this layer.
3. In `AdvancedPlayerController`, assign the **Ground Mask** field with the Ground layer.

## 📏 Character Controller Adjustment

Tweak the following values in the `CharacterController` to match your player:
- **Height**
- **Radius**
- **Center**

## 🎞️ Animator Setup

The tool auto-adds:
- `Idle`, `Walk`, `Run`, `Jump`, and `Fall` states

### Add or Edit Animation States

1. Open the Animator Controller.
2. Drag & drop new animation clips into the Animator window.
3. Right-click to create new **States**.
4. Use **Make Transition** to define flow between states.
5. Use the **Parameters** tab to set triggers/conditions.

## ➕ Extending Functionality

Add new features to `AdvancedPlayerController`, such as:

### Example: Add Crouch
```csharp
void HandleCrouch() {
    // Toggle crouch and adjust CharacterController height
}
```

## 🎥 Camera Configuration

The `ThirdPersonCamera` script provides adjustable properties:

| Property         | Description                             |
|------------------|-----------------------------------------|
| `Distance`       | Distance behind the player              |
| `Height`         | Height of camera above the player       |
| `Rotation Speed` | How fast the camera rotates             |
| `Vertical Clamp` | Limits up/down rotation angle           |

## 🧩 Requirements

- Unity 2020.3 or later
- Works in HDRP/URP/Built-in pipelines

## 📂 Folder Structure

```
Assets/
└── CharacterSetupTool/
    ├── Scripts/
    │   └── AdvancedPlayerController.cs
    ├── Editor/
    │   └── CharacterSetupMenu.cs
    └── Animator/
        └── PlayerAnimatorController.controller
```

## 🛠️ Future Plans

- Add 1st person toggle
- Multiplayer-ready support
- ScriptableObject-driven input mapping
