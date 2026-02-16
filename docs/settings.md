# Settings Guide

Complete reference for configuring your AppGatePro system. This page explains every setting and how to use them effectively.

## Accessing Settings

From the main menu:
1. Navigate to **Settings** or **AppGateSettings**
2. The settings screen displays with all configuration options
3. Changes save automatically as you make them
4. Use the **Back (←)** or **Home (🏠)** buttons to exit

!!! tip "Settings Scroll"
    The settings screen scrolls vertically. Swipe up to see all options.

---

## External Devices

Control which wireless devices are active in your training setup. Each device can be toggled independently.

### Device Icons

Tap each icon to enable/disable the corresponding device:

```
┌──────┐  ┌──────┐  ┌──────┐  ┌──────┐
│LIGHTS│  │TIMER │  │ GATE │  │MAG/  │
│      │  │      │  │      │  │ RAM  │
└──────┘  └──────┘  └──────┘  └──────┘
```

**Visual indicators:**
- **Green glow** = Device enabled and active
- **Gray/no glow** = Device disabled
- **Status text** below icon shows connection state

### LIGHTS Toggle

**Controls:** JNS_Lights external start light system

**When ON (green glow):**
- Start lights will display UCI-compliant sequence
- Synchronized with CoreS3 audio beeps
- Latency automatically compensated

**When OFF:**
- Only CoreS3 screen shows visual sequence
- Audio beeps still play
- Useful for solo practice without lights

**Status messages:**
- "Connected" - Device paired and ready
- "Not Paired" - Need to pair device
- "Searching..." - Attempting connection

### TIMER Toggle

**Controls:** JNS_Timing external breakbeam timer

**When ON (green glow):**
- System waits for beam break to stop timing
- "Sprint Time" setting is ignored
- Speed calculated from distance and actual time
- 2-minute safety timeout if no beam break

**When OFF:**
- System uses internal countdown timer
- "Sprint Time" setting determines duration
- Speed = 0.00 (no beam measurement)
- Useful for technique practice without finish timing

### GATE Toggle

**Controls:** Physical gate hardware (if you have one)

!!! info "Beta Systems"
    Your beta system does not include a physical gate. Leave this setting OFF.

**When ON:**
- Enables communication with JNS_Gate hardware
- "MAG/RAM" selector becomes active
- Physical gate will rise and drop during sequence

**When OFF (typical for beta testers):**
- Gate drop is simulated on screen and audio
- "MAG/RAM" selector is grayed out and inactive
- System functions normally for timing practice

### MAG/RAM Mode Selector

**Only active when GATE is enabled.** Switches between two gate controller types:

**MAG Mode (cyan/blue glow):**
- Magnetic gate controller
- Gate is held up magnetically
- Release signal drops gate instantly
- Typical for electromagnetic gate systems

**RAM Mode (yellow/gold glow):**
- 12V RAM-style gate controller
- Motor-driven gate rise and drop
- Sends "RISE" command during reset
- Sends "DROP" command at start
- Typical for pneumatic/hydraulic gates

**When GATE is OFF:**
- Icon appears grayed out
- No glow effect
- Tapping has no effect
- Mode selection not relevant

---

## Performance Settings

Configure detection thresholds and timing parameters.

### G-Force Threshold

**Roller selector with 6 options:**

```
0.2G  →  0.5G  →  1G  →  2G  →  5G  →  10G
```

**What it controls:**
- Minimum acceleration required to trigger certain events
- Affects reaction time detection sensitivity
- Influences movement detection algorithms

**Choosing the right threshold:**

**0.2G - 0.5G (Very sensitive):**
- Low-intensity activities
- Cadence analysis
- Technique focus with minimal effort
- May detect vibrations and bumps

**1G - 2G (Moderate sensitivity) ← Recommended for most BMX:**
- Normal racing starts
- Training sessions
- Good balance of sensitivity and noise rejection
- Detects strong pedal strokes

**5G - 10G (Low sensitivity):**
- High-intensity racing
- Filters out all but maximum effort
- Professional competition use
- Avoids false triggers from bike handling

!!! tip "Start with 2G"
    For typical BMX gate starts, 2G provides excellent detection without false triggers. Adjust based on your experience.

### Sprint Time

**Roller selector: 1-10 seconds**

```
1 sec  →  2 sec  →  3 sec  →  ...  →  10 sec
```

**What it controls:**
- Duration of timing window when External Timer is OFF
- How long IMU records data
- When timer automatically stops

**Choosing sprint time:**

**1-3 seconds:**
- Reaction time focus
- Gate exit speed only
- Quick burst training

**4-6 seconds:**
- Standard sprint distance (10-20m)
- First straight practice
- Most common setting

**7-10 seconds:**
- Longer distance training (30m+)
- Full acceleration curve
- Extended IMU recording

!!! warning "Only Active When External Timer is OFF"
    If you have TIMER enabled (using breakbeam), this setting is ignored and timing runs until beam break.

---

## Session Configuration

Control multi-run tracking and batch data collection.

### Session Mode Toggle

**ON/OFF switch**

**When OFF (default):**
- Each run is independent
- Results shown after each run
- No automatic counting or batching
- Good for casual practice

**When ON:**
- System tracks multiple runs as a session
- Counter displays: "GATES: 5/5" (example)
- After final run: Save prompt appears
- Can save all runs together
- Perfect for structured training

**Use cases:**
- Multi-rider rotation (each rider = 1 gate)
- Individual training sets (e.g., 5 practice starts)
- Competition heats
- Comparative analysis across runs

### Gates per Session

**Roller selector: 1-20**

```
1  →  2  →  3  →  5  →  10  →  15  →  20
```

**Only active when Session Mode is ON.**

**What it controls:**
- How many runs before session completes
- Counter starts at this number and counts down
- When it reaches 0/X, save prompt appears

**Example session (Gates per Session = 5):**

1. **Run 1 completes** → Display: "GATES: 4/5"
2. **Run 2 completes** → Display: "GATES: 3/5"
3. **Run 3 completes** → Display: "GATES: 2/5"
4. **Run 4 completes** → Display: "GATES: 1/5"
5. **Run 5 completes** → Popup: "Session Complete - Save to SD? / Upload to Web? / Cancel"

**Choosing gate count:**

- **3-5 gates:** Individual training focus
- **5-8 gates:** Standard club practice
- **10+ gates:** Competition day with multiple heats

!!! tip "Auto-Advance Between Runs"
    After each run's finish screen, system automatically returns to ready after 25 seconds (if Auto-Transition is enabled). Perfect for continuous training.

---

## Distance Tracking

Enable distance-based measurements and speed calculations.

### Distance Toggle

**ON/OFF switch**

**When OFF:**
- Distance not recorded with runs
- Speed calculations not performed
- Focus purely on time and IMU analytics

**When ON:**
- Distance value stored with each run
- Enables speed calculation (if using External Timer)
- Distance shown on finish screen
- Useful for sprint distance training

### Distance per Run

**Roller selector: 5m, 10m, 15m, 20m, 25m, 30m**

**Only active when Distance toggle is ON.**

**What it controls:**
- The distance value associated with your runs
- Used in speed calculation: Speed = Distance ÷ Time

**Important:** This is the distance from the **start line to the breakbeam sensor**. Measure accurately for correct speed calculations.

**Speed calculation behavior:**

**With External Timer ON:**
```
Distance: 20 meters
Time: 5.234 seconds (from beam break)
Speed: 20 ÷ 5.234 = 3.82 m/s (13.75 km/h)
```

**With External Timer OFF:**
```
Distance: 20 meters
Time: 10.000 seconds (countdown expired)
Speed: 0.00 m/s (no beam break = no speed)
```

**Common distances:**

- **5m:** Gate exit speed focus
- **10m:** Short sprint, acceleration analysis
- **20m:** Standard sprint distance
- **30m:** Extended sprint, top speed measurement

!!! warning "Measure Accurately"
    Speed calculations are only as accurate as your distance measurement. Use a tape measure from gate position to breakbeam sensor.

---

## System Settings

General device behavior and display preferences.

### Auto-Transition (25s)

**ON/OFF toggle**

**When ON (recommended):**
- After finish screen displays, system waits 25 seconds
- If no button press, automatically returns to ready state
- Next rider can start immediately
- Ideal for: Multiple riders, demo mode, continuous training

**When OFF:**
- Finish screen remains displayed indefinitely
- User must manually tap screen to continue
- Gives more time to review results
- Ideal for: Solo practice, detailed analysis

**Use cases:**

**Club training with rotation:**
- Auto-Transition: ON
- Each rider finishes → 25 seconds → next rider ready

**Solo technique practice:**
- Auto-Transition: OFF
- Study each run's results carefully before continuing

### Volume

**Slider: 0-255**

```
|──────────────●──────────| 
0           125         255
(Silent)   (Medium)    (Max)
```

**What it controls:**
- Audio beep volume during start sequence
- System notification sounds
- Tone loudness for gate drop simulation

**Recommended settings:**

- **Indoor track:** 100-150 (moderate volume)
- **Outdoor track:** 180-220 (louder for ambient noise)
- **Solo practice:** 80-120 (lower is fine)
- **Silent mode:** 0 (visual only, no audio)

**Adjusting:**
- Drag slider left/right
- Or tap anywhere on slider bar to jump to that level
- Changes take effect immediately

### Brightness

**Slider: 0-255**

```
|──────────────●──────────| 
0           125         255
(Dim)     (Medium)    (Bright)
```

**What it controls:**
- Screen backlight intensity
- Display visibility

**Recommended settings:**

- **Bright sunlight:** 220-255 (maximum)
- **Indoor:** 120-180 (moderate)
- **Evening/night:** 60-100 (low to preserve night vision)
- **Battery saving:** 80-120 (lower uses less power)

**Tips:**
- Higher brightness drains battery faster
- Lower brightness harder to see outdoors
- Find balance between visibility and battery life

---

## Web Dashboard

Access real-time data and analytics from any device.

### QR Code Section

Located at the bottom of the Settings page. Always visible.

**What it provides:**

1. **QR code image** - Scan with phone/tablet camera
2. **Network name (SSID)** - For manual connection
3. **Network password** - If required
4. **URL** - Dashboard web address
5. **Server status** - Connection readiness indicator

### Using the Dashboard

**Quick connect (recommended):**

1. Open camera app on your phone or tablet
2. Point at QR code on CoreS3 screen
3. Tap the notification that appears
4. Your device connects to CoreS3 WiFi automatically
5. Dashboard opens in browser

**Manual connect:**

1. Go to WiFi settings on your device
2. Connect to network shown on screen (e.g., "AppGatePro_ABC123")
3. Enter password if prompted
4. Open browser and enter URL shown on screen
5. Dashboard loads

### Dashboard Features

**Live monitoring:**
- Current system state (Idle, Armed, Timing, Finished)
- Real-time G-force graph during runs
- Elapsed time updated continuously
- Reaction time when detected

**Results display:**
- Complete run statistics after each finish
- Acceleration vs. time chart
- All IMU analytics
- Speed calculation (if available)

**Session tracking:**
- View all runs in current session
- Compare performance across runs
- Download data as CSV or JSON
- Share results link

**Remote control:**
- Start/Stop functions (if enabled)
- Coach can trigger sequences
- Safety: Only when enabled in settings

### Status Indicators

**✓ Server Ready:**
- Dashboard is accessible
- CoreS3 web server running
- Ready for connections

**⚠ Starting Server...:**
- Dashboard initializing
- Wait a few seconds and refresh

**✗ Server Error:**
- Dashboard unavailable
- Check WiFi settings
- Restart CoreS3 if needed

---

## Typical Settings Combinations

### Solo Practice (No External Devices)

```
External Devices:
  LIGHTS: OFF
  TIMER: OFF
  GATE: OFF

Performance:
  G-Force: 2G
  Sprint Time: 5 seconds

Session:
  Session Mode: OFF
  Distance: OFF

System:
  Auto-Transition: OFF (take time to review)
  Volume: 100
  Brightness: Auto/Medium
```

**Result:** Simple standalone timing with on-screen feedback only.

---

### Sprint Training (Lights + Breakbeam)

```
External Devices:
  LIGHTS: ON
  TIMER: ON
  GATE: OFF

Performance:
  G-Force: 2G
  Sprint Time: N/A (ignored)

Session:
  Session Mode: OFF
  Distance: ON (20m)

System:
  Auto-Transition: ON (25s)
  Volume: 150
  Brightness: High (outdoor)
```

**Result:** Professional timing with lights and precise speed measurement.

---

### Club Training Session (5 Riders)

```
External Devices:
  LIGHTS: ON
  TIMER: ON
  GATE: OFF

Performance:
  G-Force: 2G
  Sprint Time: N/A (ignored)

Session:
  Session Mode: ON
  Gates per Session: 5
  Distance: ON (20m)

System:
  Auto-Transition: ON (25s)
  Volume: 180 (loud for outdoor)
  Brightness: 200
```

**Result:** Five riders rotate, system tracks all runs, saves together at end.

---

### Reaction Time Focus

```
External Devices:
  LIGHTS: ON
  TIMER: OFF
  GATE: OFF

Performance:
  G-Force: 1G (sensitive)
  Sprint Time: 3 seconds (short)

Session:
  Session Mode: ON
  Gates per Session: 10 (many reps)
  Distance: OFF (not relevant)

System:
  Auto-Transition: ON
  Volume: 120
```

**Result:** Quick repeats focused on minimizing reaction time.

---

## Advanced Tips

### Latency Optimization

**The system automatically measures latency during RESET:**
- Sends test signals to external devices
- Measures round-trip time
- Stores compensation values
- Adjusts trigger timing for perfect sync

**To ensure best latency compensation:**
1. Keep devices within 50m during operation
2. Minimize obstacles between CoreS3 and external devices
3. Run RESET sequence before each session
4. If sync seems off, power cycle all devices and re-pair

### Battery Life Optimization

**Settings that impact battery:**

**High drain:**
- Brightness: 200-255
- WiFi/Dashboard: Enabled
- External devices: All enabled

**Low drain:**
- Brightness: 80-120
- WiFi: Disabled when not needed
- External devices: Only what you need

**For all-day training:**
- Start at 50% brightness
- Disable WiFi except when viewing dashboard
- Enable Auto-Transition to reduce screen-on time

### Multi-Rider Efficiency

**For clubs with 5+ riders:**

1. **Enable Session Mode** with Gates per Session = rider count
2. **Enable Auto-Transition** (25s)
3. **Assign CoreS3** to one person (starter/coach)
4. **Each rider goes in turn:**
   - Rides up to start
   - Starter taps START
   - Rider completes run
   - System auto-advances
   - Next rider ready
5. **After all riders:** One save operation for entire session

**Efficiency gain:** No manual saving between runs, continuous flow.

### Competition Day Setup

**Day before:**
- Full system test with all devices
- Verify all pairings solid
- Check battery levels
- Update firmware if available
- Save configuration backup

**Morning of:**
- Fresh batteries in all devices
- Quick test run to verify sync
- Adjust brightness for conditions
- Set appropriate distance
- Enable Session Mode for heats

---

## Settings Reset

### Soft Reset (Settings Only)

**To restore default settings:**
1. Navigate to Settings
2. Scroll to bottom
3. Look for "Reset to Defaults" option
4. Confirm reset
5. All settings return to factory defaults
6. Device pairings are preserved

### Hard Reset (Full System)

**If experiencing issues:**
1. Power off CoreS3
2. Hold power button for 10 seconds
3. Release and power on normally
4. System performs full initialization
5. May need to re-pair external devices

---

## Next Steps

- **[External Devices](external-devices.md)** - Detailed setup for lights and timer
- **[Advanced Features](advanced-features.md)** - Session mode, analytics, web dashboard
- **[Basic Operation](operation.md)** - Complete system operation guide
- **[Troubleshooting](troubleshooting.md)** - Fix common issues
