# Advanced Features

Master the powerful features that make AppGatePro a professional training tool. This guide covers session mode, detailed analytics, and advanced timing capabilities.

---

## Session Mode

Track multiple runs as a connected session for comparative analysis and progress tracking.

### What is Session Mode?

Session Mode allows you to:
- Track multiple runs (1-20) as a batch
- Compare performance across runs
- Save all data together
- Analyze trends and improvement
- Perfect for structured training

**Example:** A 5-gate session tracks five separate runs, then prompts you to save all the data together with comparative statistics.

### Enabling Session Mode

1. Navigate to **Settings**
2. Toggle **Session Mode: ON**
3. Set **Gates per Session** (1-20)
4. Return to AppGatePro

The session counter appears on screen: **"GATES: 5/5"** (example)

### Running a Session

**Starting position:**
- Counter shows full count (e.g., 5/5)
- System is ready for first run

**Run 1:**
1. Tap RESET → START
2. Complete your run
3. Finish screen displays results
4. Counter updates: **"GATES: 4/5"**
5. After 25 seconds (if Auto-Transition is ON), returns to ready
6. OR tap screen to continue immediately

**Runs 2-4:**
- Same process repeats
- Counter decrements: 4/5 → 3/5 → 2/5 → 1/5
- Each run recorded independently

**Final Run (Run 5):**
1. Counter shows: **"GATES: 1/5"**
2. Complete the run
3. **Session Complete popup appears:**
   ```
   ╔════════════════════════════════╗
   ║    Session Complete!           ║
   ╠════════════════════════════════╣
   ║  5 gates completed             ║
   ║                                ║
   ║  [Save to SD]                  ║
   ║  [Upload to Web]               ║
   ║  [Cancel]                      ║
   ╚════════════════════════════════╝
   ```
4. Choose save option

### Save Options

**Save to SD:**
- Writes session data to SD card
- Creates CSV file with all runs
- Includes comparison table
- Individual acceleration graphs
- Can be opened in Excel/Google Sheets

**Upload to Web:**
- Requires WiFi connection
- Uploads to cloud dashboard
- Accessible from any device
- Generates shareable link
- Automatic backup

**Cancel:**
- Discards session data
- Counter resets to 5/5
- Cannot be recovered
- Use if session was invalid

### Session Data Contents

Each saved session includes:

**Per-run data:**
- Timestamp
- Elapsed time
- Reaction time
- Max G-force
- Average G-force
- Peak acceleration
- Distance (if configured)
- Speed (if breakbeam used)
- Wheelie analytics (if detected)

**Comparative statistics:**
- Best run (fastest time)
- Worst run (slowest time)
- Average time across all runs
- Consistency score
- Trend analysis (improving/declining)
- Personal records broken

**Graphs:**
- Individual acceleration curves for each run
- Overlay comparison (all runs on one chart)
- G-force distribution

### Use Cases for Session Mode

**Individual Training:**
- Set Gates = 5-10
- Practice consistent starts
- Identify best technique
- Track fatigue effects (later runs vs. early runs)

**Club Practice (Multiple Riders):**
- Set Gates = number of riders
- Each rider completes one run
- Save captures all riders' data
- Coach can compare and rank

**Competition Heats:**
- Set Gates = number of heats
- Track performance across qualifying rounds
- Identify best heat
- Strategy for finals

**Technique Experimentation:**
- Set Gates = 4-6
- Try different starting techniques
- Run 1-2: Normal technique
- Run 3-4: Modified technique
- Compare results objectively

---

## Distance Tracking & Speed Calculation

Measure performance over known distances with automatic speed calculation.

### Configuring Distance

1. **Enable Distance toggle** in Settings
2. **Set Distance per Run:** 5m, 10m, 15m, 20m, 25m, 30m
3. **Measure your track:**
   - Use tape measure from start line to breakbeam
   - Ensure accurate measurement for speed calculations

### Distance Tracking Modes

**Mode 1: Internal Timer (External Timer OFF)**

Configuration:
```
TIMER: OFF
Distance: ON (20m)
Sprint Time: 10 seconds
```

Behavior:
- Timer counts down to configured time (10s)
- Distance is stored but no speed calculated
- Speed displays as 0.00 m/s
- Useful for: Tracking distance metadata without timing equipment

**Mode 2: External Breakbeam (External Timer ON)**

Configuration:
```
TIMER: ON (JNS_Timing paired)
Distance: ON (20m)
Breakbeam at 20m mark
```

Behavior:
- Timer runs until beam break
- System calculates: **Speed = Distance ÷ Time**
- Speed displayed in m/s and km/h
- Precise measurement for performance tracking

### Example Speed Calculations

**20m sprint:**
```
Distance: 20 meters
Time: 5.234 seconds
Speed: 20 ÷ 5.234 = 3.82 m/s
      = 13.75 km/h
```

**10m sprint:**
```
Distance: 10 meters
Time: 2.891 seconds
Speed: 10 ÷ 2.891 = 3.46 m/s
      = 12.46 km/h
```

**30m sprint:**
```
Distance: 30 meters
Time: 7.102 seconds
Speed: 30 ÷ 7.102 = 4.22 m/s
      = 15.19 km/h
```

### Finish Screen with Speed

When distance and breakbeam are configured:

```
╔══════════════════════════════════╗
║     RUN #47 - 14:32:18          ║
╠══════════════════════════════════╣
║  TIME:         5.234s           ║
║  DISTANCE:     20 meters        ║
║  SPEED:        3.82 m/s         ║
║                13.75 km/h        ║
║                                  ║
║  REACTION:     0.287s           ║
║  MAX G:        1.8 G            ║
║  AVG G:        0.9 G            ║
╠══════════════════════════════════╣
║  [VIEW GRAPH]  [SAVE]  [NEXT]   ║
╚══════════════════════════════════╝
```

### Training with Distance Goals

**Progressive Distance Training:**

Week 1: 10m focus
- Session 1: Average 3.2 m/s
- Session 2: Average 3.4 m/s
- Session 3: Average 3.5 m/s

Week 2: 20m focus
- Session 1: Average 3.6 m/s
- Session 2: Average 3.7 m/s
- Session 3: Average 3.8 m/s

Track improvement by:
- Comparing average speeds week-over-week
- Identifying plateau points
- Setting incremental goals (e.g., +0.1 m/s per week)

---

## IMU Analytics Deep Dive

Understanding the detailed biomechanical data captured during each run.

### What the IMU Measures

**6-Axis Inertial Measurement Unit:**
- 3-axis accelerometer (X, Y, Z acceleration)
- 3-axis gyroscope (pitch, roll, yaw rotation)
- Sampling rate: 200Hz (every 5ms)
- Gravity compensation for true acceleration
- Complementary filter for sensor fusion

### Key Metrics Explained

#### Reaction Time

**Definition:** Time from gate drop beep to first detectable forward motion

**How it's detected:**
1. System monitors for backward pull (rider loading bike)
2. Detects forward surge when acceleration exceeds threshold
3. Calculates time delta between beep and motion

**Typical values:**
- **Elite:** 0.15-0.25 seconds
- **Advanced:** 0.25-0.35 seconds
- **Intermediate:** 0.35-0.50 seconds
- **Novice:** 0.50+ seconds

**Improving reaction time:**
- Focus on anticipation without false starting
- Practice "loading" the bike before gate drops
- Consistency more important than raw speed

#### G-Force (Acceleration)

**Definition:** Gravitational force units measuring acceleration intensity

**Calculation:**
- System measures linear acceleration in all axes
- Compensates for gravity (1G baseline)
- Filters noise for clean readings
- Reports peak and average G-force

**Typical values:**
- **Max G-force:** 1.5-2.5 G during initial pedal strokes
- **Average G-force:** 0.6-1.2 G over full sprint
- **Elite riders:** Sustain higher average G longer

**What it means:**
- Higher peak G = explosive power
- Higher average G = sustained power
- G-force at specific times shows power curve

#### Pitch Angle

**Definition:** Forward/backward tilt of bike relative to ground

**Why it matters:**
- Indicates body position and weight distribution
- Shows wheelie control
- Affects power transfer efficiency

**Typical values:**
- **Start position:** -2° to 2° (level)
- **Acceleration:** 5° to 12° (slight nose-up)
- **Wheelie:** 15° to 25° (front wheel up)
- **Over-rotation:** 25°+ (loss of control)

**Optimal range:**
- 8-12° during peak acceleration
- Maintains traction while maximizing power
- Too low = front-heavy, less power
- Too high = wheelie, loss of forward drive

#### Roll Angle

**Definition:** Side-to-side tilt of bike

**Why it matters:**
- Shows straightness of line
- Indicates balance and control
- Excessive roll = wasted motion

**Typical values:**
- **Good technique:** ±3° maximum
- **Acceptable:** ±5-8°
- **Poor technique:** ±10°+ (bike weaving)

### Wheelie Detection & Analysis

The system automatically detects and analyzes wheelies:

**Detection criteria:**
1. Pitch angle exceeds 15° (configurable)
2. Sustained for >0.1 seconds
3. Pitch returns below 10.5° to end (hysteresis prevents flicker)

**Wheelie metrics:**

```
╔══════════════════════════════════╗
║    Wheelie Analysis              ║
╠══════════════════════════════════╣
║  Start Time:    0.82s            ║
║  Duration:      1.15s            ║
║  Max Pitch:     18.3°            ║
║  End Time:      1.97s            ║
║                                  ║
║  Distance:      4.2m @ wheelie   ║
║  G-force:       1.6G at start    ║
╚══════════════════════════════════╝
```

**Training with wheelie data:**

**Controlled wheelie (good):**
- Starts around 0.8-1.2s after gate drop
- Duration: 0.8-1.5s
- Max pitch: 15-20°
- Smooth transition back to ground

**Excessive wheelie (problematic):**
- Starts too early (<0.5s)
- Duration: >2.0s
- Max pitch: >22°
- Hard landing or loss of speed

**Use wheelie data to:**
- Practice consistent wheelie timing
- Control wheelie height (pitch angle)
- Minimize airborne time
- Optimize transition for speed

### Acceleration Graph

The finish screen displays a detailed acceleration vs. time graph:

```
G-force
  ↑
2.0┤     ●
   │    ╱ ╲
1.5┤   ╱   ╲
   │  ╱     ╲___
1.0┤ ╱          ╲___
   │╱               ╲___
0.5┤                    ╲___
   └───────────────────────────→ Time (s)
   0   1   2   3   4   5   6
```

**Reading the graph:**

**Phase 1 (0-1s): Explosive start**
- Rapid rise to peak G-force
- Reaction time visible as delay from 0
- Peak G indicates maximum power output

**Phase 2 (1-3s): Sustained power**
- Gradual decline from peak
- Area under curve = total work done
- Flatness indicates power endurance

**Phase 3 (3-6s): Maintenance**
- Lower G-force, approaching cruise
- Indicates transition to steady state
- Shows fatigue effects

**Comparing runs:**
- Overlay multiple graphs (session mode)
- Look for: Higher peaks, larger area under curve
- Consistency in peak timing
- Longer sustained power phase

---

## Web Dashboard Features

Access real-time data and advanced analytics from any device with a web browser.

### Connecting to Dashboard

**Quick method (QR code):**
1. Open Settings on Main Controller
2. Scroll to QR code at bottom
3. Scan with phone/tablet camera
4. Tap notification to connect
5. Dashboard opens automatically

**Manual method:**
1. Go to WiFi settings on your device
2. Connect to network shown on Main Controller (e.g., "AppGatePro_ABC123")
3. Open browser
4. Navigate to URL shown on Main Controller
5. Dashboard loads

### Live Monitoring

**During a run, dashboard displays:**

**Status section:**
- Current state: IDLE / ARMED / TIMING / FINISHED
- Elapsed time (updating continuously)
- Gate counter (if session mode active)

**Real-time chart:**
- G-force graph updates at 20Hz
- Smooth animation showing acceleration
- Color-coded zones (peak, sustained, cruise)

**Quick stats:**
- Current G-force value
- Reaction time (when detected)
- Distance covered (calculated from acceleration)

### Results View

**After each run completes:**

**Summary card:**
```
┌─────────────────────────────────┐
│  Run #47 - 14:32:18             │
├─────────────────────────────────┤
│  Time:        5.234s            │
│  Reaction:    0.287s            │
│  Max G:       1.8 G             │
│  Avg G:       0.9 G             │
│  Speed:       3.82 m/s          │
└─────────────────────────────────┘
```

**Interactive graph:**
- Acceleration vs. time
- Zoomable and pannable
- Hover for exact values at any point
- Export as PNG image

**Detailed breakdown:**
- Reaction time analysis
- Power phases (explosive, sustained, cruise)
- Wheelie detection (if occurred)
- Pitch and roll throughout run

### Session Comparison

**When session mode is active:**

**Runs table:**
```
╔═══════════════════════════════════════════╗
║  Run  │  Time   │ React │ Max G │ Speed   ║
╠═══════════════════════════════════════════╣
║   1   │ 5.345s  │ 0.298 │ 1.7G  │ 3.75    ║
║   2   │ 5.234s  │ 0.287 │ 1.8G  │ 3.82 ●  ║
║   3   │ 5.412s  │ 0.312 │ 1.6G  │ 3.69    ║
║   4   │ 5.289s  │ 0.291 │ 1.8G  │ 3.79    ║
║   5   │ 5.201s  │ 0.283 │ 1.9G  │ 3.85 ●  ║
╚═══════════════════════════════════════════╝
● = Personal Record
```

**Comparative charts:**
- All runs overlaid on one graph
- Compare acceleration curves
- Identify most efficient technique
- Spot consistency issues

**Statistics:**
- Average time
- Best/worst run
- Standard deviation (consistency metric)
- Trend analysis (improving/declining)

### Data Export

**Export options from dashboard:**

**CSV format:**
- Opens in Excel, Google Sheets
- Each run as a row
- All metrics as columns
- Time-series data in separate sheet

**JSON format:**
- For programmers/data scientists
- Complete data structure
- All arrays preserved (acceleration, pitch, etc.)
- Import into custom analysis tools

**PDF report:**
- Formatted document
- Graphs embedded
- Summary statistics
- Shareable with coaches/parents

### Sharing Results

**Generate shareable link:**
1. Click "Share" on any run or session
2. System generates unique URL
3. Copy link to clipboard
4. Share via text, email, social media

**Recipients can:**
- View results without logging in
- See graphs and statistics
- Download data
- Compare to their own results (if they have accounts)

**Privacy:**
- Links are unique and hard to guess
- Can be made private (password protected)
- Can expire after set time
- You control who sees your data

### Remote Control

**If enabled in settings, coach/parent can:**

**Start/Stop functions:**
- Trigger RESET sequence remotely
- Initiate START sequence
- Abort run if necessary
- Useful for solo riders with remote coach

**View-only mode (default):**
- Dashboard shows live data
- No control functions
- Safe for spectators

**Enabling remote control:**
1. Settings → Web Dashboard
2. Toggle "Remote Control: ON"
3. Dashboard gains control buttons
4. Use responsibly (no false starts!)

---

## UCI Compliance & Abort Window

Understanding the official rules implemented in AppGatePro.

### UCI Random Start Rules

**Requirement:** Random delay between "Watch the Gate" and gate drop

**AppGatePro implementation:**
- Random delay: 100ms to 2700ms
- Cryptographically secure randomization (not predictable)
- Meets UCI specifications exactly
- Audit log for verification

**Sequence timing:**
```
"Random Start" announcement
    ↓ (1.8 seconds)
"Riders Ready - Watch the Gate"
    ↓ (random: 0.1-2.7 seconds)
Light sequence begins (4 lights)
    ↓ (480ms: 4 × 120ms)
Gate drop tone (2250ms)
```

### Abort Window Rules

**UCI rule:** Riders can abort before "Watch the Gate" completes, but not after.

**AppGatePro enforcement:**

**Valid abort (before "Watch the Gate"):**
1. User presses ABORT button
2. Sequence stops immediately
3. Abort light pattern plays (on external lights if connected)
4. Returns to idle state
5. No timing recorded

**Invalid abort (after "Watch the Gate"):**
1. "Watch the Gate" completes
2. **Abort button disabled automatically**
3. Pressing ABORT has no effect
4. Sequence continues to completion
5. Run is timed normally

**Visual indication:**
- ABORT button grayed out when disabled
- Warning text: "Abort window closed"
- Ensures fair starts in competition

### Competition Mode

**For official use:**
1. Enable all external devices (Lights, Timer, Gate if available)
2. Enable Session Mode for multiple heats
3. Enable Distance Tracking
4. Verify UCI random start enabled (default)
5. Log all sessions for verification

**Logged data includes:**
- Exact random delay used
- Timestamp of gate drop
- All device synchronization data
- Proof of UCI compliance

---

## Advanced Troubleshooting & Optimization

### Performance Tuning

**Maximizing IMU accuracy:**
1. Tight mounting - zero movement when bike shaken
2. Arrow pointing forward (critical)
3. Monthly calibration
4. Firmware updates

**Optimizing wireless sync:**
1. Devices within 50m during operation
2. Line of sight when possible
3. Fresh batteries in all units
4. Run RESET before each session (latency compensation)

### Data Quality Checks

**Signs of good data:**
- Smooth acceleration curve (no spikes)
- Reaction time 0.15-0.60s (reasonable range)
- Max G-force 1.0-2.5G (typical for BMX)
- Pitch stable during run (±5° variation)

**Signs of bad data (check mounting):**
- Jagged acceleration curve
- Reaction time <0.10s or >1.0s
- Max G-force <0.5G or >3.5G
- Pitch swinging wildly (±20°+)

### Session Strategy

**For best comparative results:**
1. Same distance for all runs
2. Consistent rest periods between runs
3. Similar conditions (wind, temperature)
4. Track any technique changes
5. Note fatigue effects in later runs

---

## Next Steps

- **[Settings Guide](settings.md)** - Configure all system options
- **[External Devices](external-devices.md)** - Setup lights and timer
- **[Basic Operation](operation.md)** - Core features and modes
- **[Troubleshooting](troubleshooting.md)** - Fix issues and optimize
