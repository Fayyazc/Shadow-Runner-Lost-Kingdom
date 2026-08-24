# 🌟 SHADOW RUNNER: LOST KINGDOM

An original, fast-paced 3D mission-based endless runner game built for **Android** in **Unity (C#)**.

Explore the mysterious ancient Lost Kingdom, dodge treacherous traps, harvest luminous energy crystals, power up ancient relics, and conquer the colossal **Guardian of the Lost Kingdom**!

---

## 🎮 Core Features

* **🏃 Smooth 3-Lane Movement**: Highly responsive interpolated lane switching with zero abrupt snapping.
* **🤸 Athletic Trajectory & Slide**: Physics-tuned jump arc with fast-fall mechanics and dynamic hitbox reduction sliding.
* **🎥 Cinematic Camera System**: Dynamic 3rd-person spring camera with speed-boost FOV expansion, look-ahead framing, and impact screen shake.
* **🌴 World 1: The Lost Jungle**: Procedural modular chunk generator with ancient cobblestone roads, stone obelisks, temple archways, and crystal caverns.
* **⚠️ Original Hazards & Traps**: Low obstacles (fallen logs, spike traps), high obstacles (low temple overhangs, hanging torches), lane blockers (ancient boulders, statues), dynamic hazards (rolling stones, swinging blades), and chasm gaps.
* **💎 Collectibles & Economy**: Gold Coins, Energy Crystals, and Ancient Keys with dynamic magnet attraction physics.
* **⚡ 6 Powerful Relic Power-Ups**:
  1. **Magnet**: Attracts nearby coins and crystals.
  2. **Shield**: Absorbs one fatal collision with shatter feedback.
  3. **Speed Boost**: High-velocity invulnerable dash with warp FOV lines.
  4. **Coin Multiplier (2x/3x)**: Doubles gold acquisition.
  5. **Crystal Boost**: Multiplies rare crystal yield.
  6. **Slow Motion**: Dilates obstacle speed for precision dodges.
* **⚔️ Guardian Boss Encounter**: Cinematic chase sequence with ground shockwaves, laser sweeps, and a 5-crystal relic overload victory mechanic!
* **🏆 10 Campaign Missions & Rank Progression**: Progressive objectives with XP leveling from *Explorer* to *Lost Champion*.
* **🛠️ Upgrades & Customization**: Stat upgrades for Speed, Jump, Shield, Magnet, Multiplier, and Power-Up Duration + unlockable explorer outfits.
* **🔊 Built-In Procedural Audio Synthesizer**: Complete sound architecture (SFX + Music) generated with zero missing audio dependencies.
* **📱 Android-First Architecture**: 60 FPS target, Portrait lock, native haptic feedback, hardware back-button navigation, and 1-click APK/AAB build pipeline.

---

## 🕹️ Controls

| Action | Touch Gesture (Mobile) | Keyboard (PC / Editor) |
| :--- | :--- | :--- |
| **Move Left** | Swipe Left | `A` or `Left Arrow` |
| **Move Right** | Swipe Right | `D` or `Right Arrow` |
| **Jump** | Swipe Up | `W`, `Up Arrow`, or `Space` |
| **Slide** | Swipe Down | `S` or `Down Arrow` |
| **Special Relic Blast** | Screen Tap / Button | `E` or `Ability Button` |
| **Pause** | Pause Button | `Escape` |

---

## 🚀 Quick Start (Unity Editor)

1. Open **Unity Hub** and click **Add** > select this project folder (`Shadow Runner Lost Kingdom`).
2. Open with **Unity 2021.3 LTS, 2022.3 LTS, or Unity 6**.
3. In Unity's top menu bar, click:
   ```
   Lost Kingdom -> Build Game Scenes & Prefabs
   ```
4. Open the generated scene at `Assets/Scenes/Gameplay.unity`.
5. Press **Play ▶** in the Unity Editor to play immediately!

---

## 📱 Building Android APK / AAB

1. Ensure the **Android Build Support** module (including OpenJDK and Android SDK/NDK) is installed in Unity Hub.
2. In Unity's top menu bar, click:
   - To build an APK for direct device testing:
     ```
     Lost Kingdom -> Android Build -> Build APK
     ```
   - To build an AAB App Bundle for Google Play Store:
     ```
     Lost Kingdom -> Android Build -> Build AAB (Google Play)
     ```
3. Output binaries are saved to `Builds/Android/`.

---

## 📂 Project Architecture

```
Assets/
├── Plugins/Android/
│   └── AndroidManifest.xml          # Portrait lock, haptics, game flags
├── Scenes/
│   └── Gameplay.unity               # Master scene
├── Scripts/
│   ├── Android/
│   │   └── AndroidManager.cs        # Haptic vibration & back-button handler
│   ├── Audio/
│   │   ├── AudioManager.cs          # Audio mixer & channels
│   │   └── ProceduralAudioSynthesizer.cs # Dynamic sound & music generator
│   ├── Boss/
│   │   └── GuardianBossController.cs # Guardian chase, stomp & relic overload
│   ├── Camera/
│   │   └── CameraController.cs      # Smooth 3rd person follow & shake
│   ├── Collectibles/
│   │   ├── CollectibleItem.cs       # Coins, Crystals, Keys
│   │   └── CollectibleType.cs
│   ├── Core/
│   │   ├── Bootstrapper.cs          # Initialization & singleton instantiator
│   │   ├── GameConstants.cs         # Gameplay balance & tuning variables
│   │   ├── GameManager.cs           # State machine & active run stats
│   │   └── GameState.cs
│   ├── Customization/
│   │   ├── CharacterCustomizationManager.cs # Outfits catalog & unlocker
│   │   └── UpgradeManager.cs        # Tiered stat upgrades
│   ├── Economy/
│   │   └── CurrencyManager.cs       # Coins, Crystals, Keys persistence
│   ├── Editor/
│   │   ├── AndroidBuildPipeline.cs  # 1-click APK & AAB production builder
│   │   └── LostKingdomSceneBuilder.cs # 1-click scene & prefab generator
│   ├── Level/
│   │   ├── ChunkManager.cs          # Dynamic chunk recycling & difficulty
│   │   ├── EnvironmentTheme.cs      # Color palettes & world themes
│   │   ├── LevelChunk.cs            # Modular 30m chunk container
│   │   └── ProceduralMeshBuilder.cs # 3D roads, pillars, arches, materials
│   ├── Obstacles/
│   │   ├── Obstacle.cs              # Dynamic hazards, logs, spikes, boulders
│   │   └── ObstacleType.cs
│   ├── Player/
│   │   ├── PlayerAnimationHelper.cs # Procedural leaning, bobbing, squash/stretch
│   │   ├── PlayerController.cs      # 3-lane motion, jump, slide, collisions
│   │   └── PlayerStats.cs           # Dynamic stats with upgrade modifiers
│   ├── PowerUps/
│   │   ├── PowerUpEffect.cs         # 3D pickup entity
│   │   ├── PowerUpManager.cs        # Active timers & status management
│   │   └── PowerUpType.cs
│   ├── Progression/
│   │   ├── AchievementManager.cs    # Trophies & rewards
│   │   ├── MissionData.cs           # Mission schemas
│   │   ├── MissionManager.cs        # Campaign objectives evaluator
│   │   ├── ProgressionManager.cs    # XP & rank promotion curve
│   │   └── RewardManager.cs         # Daily logins & level bonuses
│   ├── Save/
│   │   ├── SaveData.cs              # JSON persistence schema
│   │   └── SaveManager.cs           # File I/O with auto-save & reset
│   └── UI/
│       ├── DailyRewardUI.cs         # 7-day login calendar
│       ├── GameOverUI.cs            # Post-run summary & 2x coins
│       ├── GameplayHUD.cs           # Real-time HUD & powerup timers
│       ├── MainMenuUI.cs            # Main hub & rank card
│       ├── MissionsUI.cs            # Mission tracker & claim buttons
│       ├── ProfileUI.cs             # Career statistics
│       ├── SettingsUI.cs            # Volume, vibration & graphics sliders
│       ├── ShopUI.cs                # Outfits showcase & currency packs
│       ├── TutorialUI.cs            # Controls onboarding
│       ├── UIManager.cs             # Screen switcher & toasts
│       └── UpgradesUI.cs            # Interactive stat upgrade cards
└── README.md
```
