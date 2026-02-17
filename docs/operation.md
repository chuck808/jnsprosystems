# Basic Operation

Master all the features and modes of your AppGatePro system.

## Main Menu Overview

```
╔══════════════════════════════════╗
║      APPGATEPRO v2.4.1           ║
║                                  ║
║   [1] Start Gate Timing          ║
║   [2] Sprint Training            ║
║   [3] Cadence Analysis           ║
║   [4] Interval Timer             ║
║   [5] View Sessions              ║
║   [6] Settings                   ║
║   [7] Web Dashboard              ║
╚══════════════════════════════════╝
```

## Mode 1: Gate Timing

UCI-compliant timing for gate start practice.

### Random Start Mode (Recommended)

Follows UCI regulations with random delays:

1. Select **[1] Start Gate Timing**
2. Choose **Random Delay**
3. Press **OK** to arm
4. Screen shows: `ARMED - Ready for trigger`
5. When ready, trigger with remote
6. Random delay: 0.1-2.5 seconds before beep
7. Data recording: 8 seconds from beep

**What's Being Measured:**

- Reaction time (beep to first movement)
- Gate exit speed (0-10m average)
- Peak power output
- Pedal cadence
- Pitch angle through start
- Wheelie detection and timing

### Fixed Delay Mode

For specific training scenarios:

1. Select **Fixed Delay**
2. Set delay duration (0.5-3.0 seconds)
3. Arm and trigger as normal
4. Beep occurs exactly at set delay

**Use Cases:**

- Practicing specific timing
- Mental preparation drills
- Rhythm training
- Comparing identical conditions

### Understanding Results Screen

```
╔══════════════════════════════════╗
║     RUN #143 - 14:23:45          ║
╠══════════════════════════════════╣
║  REACTION:     142 ms    ⚡ PR!  ║
║  GATE SPEED:   31.2 km/h         ║
║  PEAK POWER:   847 W             ║
║  AVG CADENCE:  163 RPM           ║
║  MAX PITCH:    12.3°             ║
║  WHEELIE:      0.42s @ 4.2m      ║
╠══════════════════════════════════╣
║  [SAVE]  [DISCARD]  [REPLAY]     ║
╚══════════════════════════════════╝
```

!!! success "PR Indicator"
    The ⚡ symbol appears when you've beaten your personal record in any metric!

## Mode 2: Sprint Training

Timed sprints with automatic distance detection.

### Setup

1. Select **[2] Sprint Training**
2. Choose distance: 10m / 20m / 50m / 100m
3. Optional: Set target time
4. Position at start line

### Starting Sprint

1. Press **OK** to start countdown
2. "3... 2... 1... GO!" with beeps
3. Sprint to finish
4. System auto-detects when you stop

**Metrics Captured:**

- Total sprint time
- Average speed
- Peak speed and where it occurred
- Acceleration curve
- Power output throughout sprint
- Cadence analysis

### Training with Targets

Set target times for specific training:

```
Target: 2.8 seconds for 20m sprint
Actual: 2.91 seconds
Result: -0.11s (work on acceleration!)
```

## Mode 3: Cadence Analysis

Study your pedaling efficiency.

### Operation

1. Select **[3] Cadence Analysis**
2. Choose duration: 30s / 60s / 120s / Continuous
3. Start pedaling when prompted
4. System tracks every pedal stroke

### Results

```
╔══════════════════════════════════╗
║    CADENCE ANALYSIS - 60s        ║
╠══════════════════════════════════╣
║  AVERAGE:      157 RPM           ║
║  PEAK:         184 RPM           ║
║  CONSISTENCY:  92%   ✓ Good      ║
║                                  ║
║  POWER PHASES DETECTED:          ║
║    Stroke 1-8:   165 RPM avg     ║
║    Stroke 9-15:  152 RPM avg ⚠  ║
║    Stroke 16+:   159 RPM avg     ║
╚══════════════════════════════════╝
```

!!! tip "Consistency Score"
    >90% = Excellent smooth pedaling  
    80-90% = Good, minor variations  
    <80% = Uneven cadence, work on rhythm

## Mode 4: Interval Timer

Custom interval training sessions.

### Creating Interval Workout

1. Select **[4] Interval Timer**
2. Press **New Workout**
3. Set parameters:
   - Work duration (e.g., 30 seconds)
   - Rest duration (e.g., 90 seconds)
   - Number of intervals (e.g., 8 rounds)
4. Save and start

### During Workout

Screen displays:

```
╔══════════════════════════════════╗
║    INTERVAL 3 of 8               ║
╠══════════════════════════════════╣
║         WORK PHASE               ║
║                                  ║
║           00:17                  ║
║    [████████░░░░░░░░░]           ║
║                                  ║
║  Current Power: 723W             ║
║  Avg This Set:  698W             ║
╚══════════════════════════════════╝
```

Audio cues:

- 3-beep countdown before work phase
- 1-beep countdown before rest
- 2-beep for final interval

## Mode 5: View Sessions

Review past training data.

### Session List

```
╔══════════════════════════════════╗
║       SESSION HISTORY            ║
╠══════════════════════════════════╣
║  Feb 16 - Morning (15 runs)      ║
║  Feb 15 - Evening (23 runs)      ║
║  Feb 14 - Track Day (47 runs)    ║
║  Feb 13 - Morning (12 runs)      ║
╚══════════════════════════════════╝
```

### Session Details

Select any session to see:

- All runs in chronological order
- Best runs highlighted
- Graphs showing improvement
- Export options (USB or cloud)

### Comparing Runs

1. Select a session
2. Press **Compare**
3. Choose 2-4 runs
4. View side-by-side metrics

!!! info "Cloud Backup"
    Sessions automatically upload when connected to WiFi. View enhanced analytics at dashboard.appgatepro.com

## Settings Menu

### Essential Settings

**Display Settings:**

- Brightness: Auto / Low / Medium / High
- Theme: Light / Dark / Auto
- Screen timeout: 1-5 minutes

**System Settings:**

- Language: English / Español / Français / Deutsch
- Units: Metric / Imperial
- Time zone: Auto from GPS / Manual

**Sensor Settings:**

- Calibrate IMU
- Tire diameter setup
- Sample rate (default 200Hz)

**WiFi Settings:**

- Configure network
- Auto-upload toggle
- Cloud sync status

**User Profile:**

- Rider name
- Weight (for power calculations)
- Age category
- Bike setup

## Data Management

### Local Storage

- Capacity: ~500 sessions (40,000+ runs)
- Auto-management: Oldest sessions deleted when full
- Manual delete: Settings → Data → Manage Storage

### Cloud Sync

When WiFi enabled:

- Auto-upload after each session
- Background sync of old data
- Cloud backup of settings/profiles
- Access from web dashboard

### Exporting Data

**USB Export:**

1. Connect Main Controller to computer via USB-C
2. Device shows: `USB Mode - Select Action`
3. Choose **Export Data**
4. Select sessions to export
5. Data saved as CSV files

**Cloud Export:**

- Login to dashboard.appgatepro.com
- Navigate to any session
- Click **Export** → Choose format (CSV/JSON/PDF)

## Battery & Performance

### Typical Battery Life

| Mode | Battery Life |
|------|--------------|
| Gate timing (WiFi off) | 5-6 hours |
| Gate timing (WiFi on) | 3-4 hours |
| Continuous recording | 4-5 hours |
| Standby | 30+ days |

### Performance Tips

!!! tip "Maximize Battery"
    - Disable WiFi during training sessions
    - Lower screen brightness
    - Enable auto-sleep
    - Close unused background features

!!! tip "Improve Accuracy"
    - Calibrate IMU monthly
    - Secure mounting (no movement)
    - Keep firmware updated
    - Verify tire diameter setting

## Firmware Updates

### Checking for Updates

1. Navigate: **Settings → System → Check Updates**
2. Requires WiFi connection
3. If available: **v2.4.1 → v2.5.0 [DOWNLOAD]**

### Installing Update

!!! warning "Do Not Interrupt"
    Keep device on charger during update. Do not power off.

1. Press **DOWNLOAD** to fetch update
2. When complete: **INSTALL NOW** or **INSTALL LATER**
3. Installation takes 2-3 minutes
4. Device reboots automatically
5. Verify: Settings → System → About

### Changelog

View what's new:

- Settings → System → Version History
- Or online: appgatepro.com/firmware

## Next Steps

- **[Web Dashboard](dashboard.md)** - Advanced analytics online
- **[Training Programs](training.md)** - Structured improvement plans
- **[Troubleshooting](troubleshooting.md)** - Fix common issues
