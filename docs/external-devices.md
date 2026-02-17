# External Devices Setup

Your AppGatePro system includes wireless external devices for professional-grade timing. This guide covers pairing, positioning, and configuring your lights and breakbeam timer.

## What's Included

Your system comes with:

- **JNS_Lights** - Professional start light system for visual timing cues
- **JNS_Timing** - Breakbeam timer for precise finish line detection
- **Main Controller Unit** - Central controller with built-in IMU sensors

These devices communicate wirelessly using ESP-NOW protocol for ultra-low latency (typically <10ms).

---

## System Architecture

```
┌─────────────────┐
│   Main Controller Unit   │ ──wireless──> ┌──────────────┐
│  (on your bike) │                │  JNS_Lights  │
└─────────────────┘                └──────────────┘
         │                         (at start line)
         │
         │ wireless
         ▼
┌─────────────────┐
│   JNS_Timing    │
│  (breakbeam at  │
│   finish line)  │
└─────────────────┘
```

!!! tip "Range and Positioning"
    All devices use 2.4GHz wireless with typical range of 50-100m outdoors. Position devices within line of sight when possible for best reliability.

---

## Initial Setup Checklist

Before your first session, complete these steps:

- [ ] Charge all devices fully
- [ ] Pair JNS_Lights to Main Controller
- [ ] Pair JNS_Timing to Main Controller
- [ ] Position lights at start line
- [ ] Set up breakbeam at finish line
- [ ] Verify wireless connectivity
- [ ] Run a test session

---

## JNS_Lights Setup

### What JNS_Lights Does

The JNS_Lights unit displays the UCI-compliant start sequence visually:
- Four warning lights (illuminating in sequence)
- Final "gate drop" indication
- Synchronized with Main Controller audio beeps
- Latency compensation for perfect timing

### Physical Setup

**1. Positioning the Lights**

Place JNS_Lights at the start line where all riders can clearly see it:

```
        Riders
          ▼
    ┌─────────────┐
    │             │
    │  [Lights]   │  ← Mount at eye level
    │             │     when on bike
    └─────────────┘
         Gate
```

- **Height:** Approximately 1.5-2m (rider eye level when seated)
- **Distance:** 2-3m in front of gate position
- **Visibility:** Ensure no obstructions
- **Power:** Connect to included power supply or battery pack

**2. Powering On**

1. Connect power cable to JNS_Lights unit
2. Power switch on back of unit
3. Status LED should illuminate (solid blue = ready)
4. Unit enters pairing mode automatically on first power-up

### Pairing JNS_Lights

!!! warning "Pair Before First Use"
    Pairing must be completed before the lights will respond to timing commands.

**Step-by-step pairing:**

1. **Power on JNS_Lights** - Status LED flashes blue (pairing mode)
2. **On Main Controller:** Navigate to **Settings → External Devices**
3. **Tap the LIGHTS icon** - It will begin searching
4. **Wait for discovery** - Takes 5-10 seconds
5. **Confirm pairing** - Tap "Pair" when device appears
6. **Success indication:**
   - LIGHTS icon glows green on Main Controller
   - JNS_Lights status LED turns solid blue
   - Test lights will flash briefly

**If pairing fails:**
- Ensure JNS_Lights is within 10m during pairing
- Restart JNS_Lights by power cycling
- Clear previous pairings: Settings → External Devices → Reset Devices
- Try pairing again

### Testing JNS_Lights

After pairing, test the connection:

1. **From Settings page:** Tap the LIGHTS icon to toggle it ON (green glow)
2. **Return to main menu** and select **AppGatePro**
3. **Tap RESET** button
4. **Watch JNS_Lights:**
   - Should flash four times during warning sequence
   - Synchronized with audio beeps from Main Controller
5. **Tap START** to run full sequence
6. **Lights should illuminate** in sequence with perfect timing

!!! success "What Good Synchronization Looks Like"
    Lights should illuminate within 10-20ms of the Main Controller beep. Any person watching should perceive them as simultaneous.

### JNS_Lights Troubleshooting

**Lights don't respond during sequence:**
- Check LIGHTS toggle is ON in Settings (green glow)
- Verify status LED on JNS_Lights is solid blue
- Re-pair the device if LED is flashing
- Check battery/power supply

**Lights are delayed or out of sync:**
- Main Controller measures and compensates for latency automatically
- If sync is consistently off by >50ms, check for wireless interference
- Keep devices within 50m during operation
- Ensure line of sight between Main Controller and JNS_Lights

**Status LED meanings:**
- **Solid Blue:** Paired and ready
- **Flashing Blue:** Pairing mode / not paired
- **Red Flash:** Low battery or power issue
- **Off:** No power

---

## JNS_Timing Setup (Breakbeam)

### What JNS_Timing Does

The JNS_Timing unit provides precise finish line detection:
- Infrared breakbeam sensor
- Detects when rider crosses finish line
- Sends timing data back to Main Controller wirelessly
- Calculates speed based on distance and time
- Accuracy: ±1ms

### Physical Setup

**1. Understanding the Breakbeam System**

The breakbeam consists of two units:

```
    [Transmitter]                [Receiver]
         │                            │
         │    Invisible IR Beam       │
         │ ════════════════════════>  │
         │                            │
    (One side                    (Other side
     of track)                    of track)
```

- **Transmitter:** Emits infrared beam
- **Receiver:** Detects beam, connected to JNS_Timing controller
- **When broken:** Controller sends "STOP" signal to Main Controller

**2. Positioning the Breakbeam**

Set up at your desired finish line distance:

```
Start Line                                    Finish Line
    ║                                              ▼
    ║                                    [TX]═══════[RX]
    ║                                      ↑         ↑
    ║<─────── Track Distance ────────> │ Beam at wheel height
    ║        (10m, 20m, etc.)          │
```

**Positioning guidelines:**

- **Height:** 30-40cm above ground (wheel axle height)
- **Beam width:** Ensure full track width is covered
- **Alignment:** Transmitter and receiver must face each other directly
- **Distance:** Can span 0.5m to 10m across track
- **Stability:** Mount on tripods or stable stands

**Common distances:**
- **Sprint training:** 10m or 20m from start
- **Full straight:** 50m or more
- **Club practice:** 30m typical

**3. Connecting the Components**

1. **Plug transmitter** into "TX" port on JNS_Timing controller
2. **Plug receiver** into "RX" port on JNS_Timing controller
3. **Power on** JNS_Timing controller
4. **Verify beam:** Status LED on receiver lights up when beam is intact
5. **Test break:** Wave hand through beam - LED should turn off

### Pairing JNS_Timing

**Step-by-step pairing:**

1. **Power on JNS_Timing controller** - Status LED flashes green (pairing mode)
2. **On Main Controller:** Navigate to **Settings → External Devices**
3. **Tap the TIMER icon** - Begin scanning
4. **Wait for discovery** - Takes 5-10 seconds
5. **Confirm pairing** - Select "Pair" when JNS_Timing appears
6. **Success indication:**
   - TIMER icon glows green on Main Controller
   - JNS_Timing status LED turns solid green
   - Main Controller displays "External Timer Connected"

### Configuring Distance

!!! important "Distance Setting Required"
    For accurate speed calculations, you must tell the system the distance from start to finish line.

1. **Navigate to Settings**
2. **Enable Distance toggle** - Turns ON
3. **Set Distance per Run** - Choose from: 5m, 10m, 15m, 20m, 25m, 30m
4. **Or enter custom:** Scroll to "Custom" option and enter exact distance

This distance is used to calculate: **Speed = Distance ÷ Time**

### Testing JNS_Timing

After pairing and distance configuration:

1. **Ensure TIMER is enabled** in Settings (green glow)
2. **Start a test run:**
   - Navigate to AppGatePro
   - Tap RESET, then START
   - Run through start sequence
3. **Cross the beam** at finish line
4. **Timing stops immediately**
5. **Results display:**
   - Elapsed time (precise to millisecond)
   - Distance (as configured)
   - Speed (calculated automatically)

**Example result:**
```
Time: 5.234 seconds
Distance: 20 meters
Speed: 3.82 m/s (13.75 km/h)
```

### JNS_Timing Troubleshooting

**Beam won't establish (receiver LED off):**
- Check transmitter/receiver connections to controller
- Verify power to JNS_Timing controller
- Align transmitter and receiver - must be directly facing
- Clean lenses on both transmitter and receiver
- Check for obstructions in beam path

**Timing doesn't stop when crossing beam:**
- Verify TIMER is enabled in Settings (green glow)
- Check pairing status - re-pair if needed
- Ensure Main Controller is within wireless range (50m)
- Check JNS_Timing controller battery/power
- Review status LED on controller (should be solid green)

**Inconsistent triggering / false triggers:**
- Beam may be too low (catching shadows or debris)
- Sunlight interference - shield receiver from direct sun
- Vibration causing alignment issues - secure mounting
- Battery low - replace or recharge

**Speed calculation is wrong:**
- Verify distance setting matches actual track distance
- Measure distance accurately from gate position to beam
- Check that beam is perpendicular to track (not angled)

**Safety timeout (2 minute limit):**
- If beam doesn't break within 2 minutes, run auto-finishes
- Speed will show as 0.00 m/s
- Check beam alignment and retry

**Status LED meanings:**
- **Solid Green:** Paired and ready, beam intact
- **Flashing Green:** Pairing mode / not paired
- **Flashing Red:** Beam broken (normal during detection)
- **Solid Red:** Error state or low battery
- **Off:** No power

---

## System Integration

### Enabling Devices in Settings

After pairing, you control which devices are active:

**Settings → External Devices Section:**

1. **LIGHTS** - Tap to toggle ON (green glow) or OFF (gray)
2. **TIMER** - Tap to toggle ON (green glow) or OFF (gray)
3. **GATE** - Leave OFF (you don't have a physical gate)

**Active device indicators:**
- **Green glow** = Device enabled and will be used
- **Gray/no glow** = Device disabled, system runs standalone
- **Status text** below each icon shows connection state

### Understanding System Behavior

**With External Timer DISABLED:**
- System uses internal countdown timer
- You set duration in Settings: "Sprint Time" (1-10 seconds)
- Timer expires at configured time
- Speed = 0.00 (no beam break measurement)

**With External Timer ENABLED:**
- System ignores "Sprint Time" setting
- Timer runs until beam break detected
- Speed calculated automatically from distance/time
- 2-minute safety timeout if no beam break

### Latency Compensation

The system automatically measures and compensates for wireless latency:

**During RESET sequence:**
1. Main Controller sends test signal to each device
2. Measures round-trip time
3. Stores latency values (typically 5-15ms)
4. Adjusts trigger timing to compensate

**Result:** Lights and timing appear perfectly synchronized despite wireless transmission delays.

You'll see this in action:
- RESET sequence includes timing calibration
- Lights flash in perfect sync with Main Controller beeps
- No manual adjustment needed

---

## Complete System Test

### Pre-Session Checklist

Before each training session, verify:

- [ ] All devices powered on
- [ ] Status LEDs showing ready state (solid blue/green)
- [ ] LIGHTS and TIMER enabled in Settings (green glow)
- [ ] Distance configured correctly
- [ ] Breakbeam aligned and clear
- [ ] Main Controller mounted securely on bike

### Running Your First Full System Test

**1. Position Everything:**
- JNS_Lights at start line (visible to rider)
- Breakbeam at finish line (configured distance)
- Main Controllermounted on bike

**2. Start Sequence:**
- On Main Controller: Navigate to **AppGatePro**
- Tap **RESET** button
- **Watch/listen for:**
  - Audio warning sequence on Main Controller
  - JNS_Lights flashing in sync
  - "Gate Armed" state after sequence

**3. Execute Test Run:**
- Tap **START** on Main Controller
- **Observe:**
  - "Random Start" announcement
  - "Riders Ready - Watch the Gate"
  - Random delay (0.1-2.7 seconds)
  - Light sequence on JNS_Lights
  - Four beeps + lights
  - Final long beep (gate drop simulation)
- **Accelerate through course**
- **Cross breakbeam at finish**

**4. Verify Results:**
- Timing should stop immediately at beam break
- Finish screen displays:
  - Precise elapsed time
  - Configured distance
  - Calculated speed
  - Reaction time (from IMU)
  - Max G-force
  - Complete acceleration graph

**5. If Everything Works:**
- You're ready for training!
- System is properly configured
- All devices communicating correctly

### What Success Looks Like

✓ Lights flash in perfect sync with beeps  
✓ Timing starts at gate drop  
✓ Timing stops immediately when crossing beam  
✓ Speed is calculated accurately  
✓ No error messages or warnings  
✓ All IMU data recorded properly  

---

## Optimizing Your Setup

### Track Layout Recommendations

**For Sprint Training (10-20m):**
```
Start                    Finish
  ║                       ║
  ║ [Lights]              ║ [Beam]
  ║    │                  ║   │
  ║    ▼                  ║   ▼
  ║  ═══>  10-20m   ═══>  ║
```

**For Longer Distances (30m+):**
- Ensure wireless range is adequate
- Both devices should be within 50m of Main Controller
- Line of sight helps but not required

### Battery Management

**Expected battery life:**
- **JNS_Lights:** 4-6 hours continuous use
- **JNS_Timing:** 6-8 hours continuous use
- **Main Controller:** 4-5 hours (with WiFi off)

**Tips:**
- Charge all devices between sessions
- Carry spare batteries for full-day training
- JNS units show low battery warnings
- Power off devices when not in use

### Weather Considerations

**All devices are splash-resistant but not waterproof:**

- **Light rain:** Generally OK, protect from prolonged exposure
- **Heavy rain:** Cover or shelter devices
- **Extreme cold:** Battery life may decrease
- **Extreme heat:** Keep out of direct sun when possible

**Infrared beam in sunlight:**
- Direct sunlight can interfere with breakbeam
- Shield receiver from direct sun if possible
- Increase transmitter power (if adjustable on your model)

---

## Multiple Rider Sessions

### Quick Device Sharing

The system supports rapid switching between riders:

**Method 1 - Sequential (one at a time):**
1. Rider 1 completes run
2. Results displayed on Main Controller
3. After 25 seconds, auto-advances to ready
4. Rider 2 starts next run
5. All devices remain active and synced

**Method 2 - Session Mode (batch tracking):**
1. Enable "Session Mode" in Settings
2. Set "Gates per Session" (e.g., 5 for 5 riders)
3. System counts down: 5/5 → 4/5 → 3/5 → 2/5 → 1/5
4. After final run, save all data together
5. Perfect for club training with rotation

### Coach/Parent Viewing

Use the web dashboard for remote monitoring:

1. **Scan QR code** in Settings with phone/tablet
2. **Dashboard connects** to Main Controller WiFi
3. **Live updates** during each run:
   - Current state (Armed, Timing, Finished)
   - Real-time G-force graph
   - Elapsed time
4. **View results** after each run
5. **Compare sessions** across multiple riders

---

## Maintenance

### Weekly

- Wipe down device housings with dry cloth
- Check all cable connections
- Verify battery charge levels
- Test beam alignment

### Monthly

- Deep clean infrared lenses with lens cloth
- Verify wireless pairing still solid
- Check for firmware updates
- Inspect mounting hardware for wear

### Before Competition/Important Sessions

- Full device test the day before
- Fresh batteries in all devices
- Spare cables and batteries packed
- Backup Main Controller configuration to cloud

---

## Next Steps

Now that your external devices are set up:

- **[Settings Guide](settings.md)** - Detailed walkthrough of all configuration options
- **[Advanced Features](advanced-features.md)** - Session mode, distance tracking, analytics
- **[Basic Operation](operation.md)** - Complete guide to all system features
- **[Troubleshooting](troubleshooting.md)** - Solutions for common issues

---

## Quick Reference

### Device Status LEDs

| Device | Solid Blue/Green | Flashing Blue/Green | Red | Off |
|--------|------------------|---------------------|-----|-----|
| **JNS_Lights** | Paired & Ready | Pairing Mode | Low Battery | No Power |
| **JNS_Timing** | Paired & Ready | Pairing Mode | Error/Low Batt | No Power |

### Wireless Range

- **Pairing range:** 10m maximum
- **Operating range:** 50-100m typical
- **Best performance:** Line of sight
- **Through obstacles:** 30-50m

### Common Settings

**Sprint training:**
- LIGHTS: ON
- TIMER: ON
- Distance: 20m
- Session Mode: OFF

**Multi-rider club session:**
- LIGHTS: ON
- TIMER: ON
- Session Mode: ON
- Gates per Session: 5-10
