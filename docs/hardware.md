# Hardware Setup

Complete guide to assembling and configuring your AppGatePro system.

## System Components

### CoreS3 Main Unit

The CoreS3 is the heart of your system:

- **Display**: 320×240 touchscreen for menu navigation
- **Sensors**: 6-axis IMU sampling at 200Hz
- **Battery**: 1200mAh Li-Po (4-6 hours typical use)
- **Connectivity**: WiFi, ESP-NOW wireless protocol
- **Storage**: 8GB internal flash memory

![CoreS3 Diagram](images/cores3-ports.png)

### Remote Control

Wireless gate trigger with 100m+ range:

- **Battery**: CR2032 coin cell (12+ months typical)
- **Protocol**: ESP-NOW for instant trigger response
- **Latency**: <10ms trigger to beep delay
- **Buttons**: Single trigger button with LED feedback

## Initial Setup

### 1. Charge All Devices

!!! warning "First Charge Important"
    Fully charge all components before first use to calibrate battery management.

- Connect CoreS3 via USB-C to any 5V power source
- Charging: Red LED pulsing
- Full charge: Green LED solid
- Typical charge time: 90 minutes from empty

### 2. CoreS3 Mounting

#### Recommended Mounting Locations

```
     Handlebars
         |
    ┌────┴────┐
    │  HEAD   │  ← BEST: Head tube mounting
    │  TUBE   │     (most stable, clearest IMU data)
    └────┬────┘
         |
    ┌────┴────┐
    │   TOP   │  ← GOOD: Top tube mounting
    │  TUBE   │     (easier access, good for younger riders)
    └─────────┘
```

#### Step-by-Step Mounting

1. **Clean the surface**: Use provided alcohol wipe
2. **Attach bracket**: Secure velcro strap through bracket loops
3. **Position correctly**:
   - Arrow on device points **forward**
   - Screen visible and accessible
   - No interference with cables/brake lines
4. **Tighten securely**: Unit should not shift when pulled
5. **Insert CoreS3**: Slide into bracket until click

!!! tip "Orientation Matters"
    The forward arrow MUST point toward the front wheel. Incorrect orientation will cause inaccurate measurements.

### 3. Remote Pairing

First-time pairing:

1. Power on CoreS3
2. Navigate: **Main Menu → Settings → Remote → Add Device**
3. Hold remote trigger button for 3 seconds (LED flashes rapidly)
4. CoreS3 shows: `Scanning for remote...`
5. When found: `Remote #1234 found - Pair? [Yes/No]`
6. Select **Yes**
7. Test: Press remote button → CoreS3 beeps

!!! info "Multiple Remotes"
    You can pair up to 4 remotes to one CoreS3. Useful for club training with multiple riders.

## Calibration

### IMU Calibration

Required for accurate measurements. Perform in these situations:

- First time setup
- After firmware update
- If measurements seem inaccurate
- Monthly maintenance

**Calibration Procedure:**

1. Remove CoreS3 from bike
2. Place on **flat, level surface**
3. Navigate: **Settings → Sensors → Calibrate IMU**
4. Device shows: `Keep still for 10 seconds...`
5. **Do not touch** during calibration
6. Success: `Calibration complete ✓`

!!! warning "Level Surface Required"
    Use a proper table or floor. Do NOT calibrate on the bike frame.

### Tire Diameter Setup

For accurate speed calculations:

1. Navigate: **Settings → Bike → Tire Diameter**
2. Select from tire database or enter manually:

| Tire Size | Diameter (mm) |
|-----------|---------------|
| 20 × 1.75 | 508 |
| 20 × 1.95 | 510 |
| 20 × 2.00 | 512 |
| 24 × 1.75 | 610 |

3. Or measure: Roll bike one complete wheel rotation, measure distance

## WiFi Configuration

Connect to WiFi for cloud features:

1. Navigate: **Settings → WiFi → Configure**
2. Select your network from list
3. Enter password using on-screen keyboard
4. Status changes to: `Connected ✓`

**Cloud Features Require WiFi:**

- Session auto-upload to web dashboard
- Firmware updates
- Remote monitoring
- Data backup

!!! tip "Save Battery"
    Disable WiFi during training to extend battery life. Data saves locally and uploads when next connected.

## Battery Management

### Checking Battery Level

- **On screen**: Battery icon top-right corner
- **Percentage**: Settings → System → Battery Info

### Battery Life Tips

- **Disable WiFi** when not needed: +40% battery life
- **Lower screen brightness**: Settings → Display → Brightness
- **Auto-sleep**: Device sleeps after 2 minutes idle
- **Full cycles**: Occasionally drain to 10% then charge to 100%

### Low Battery Warnings

| Level | Warning |
|-------|---------|
| 20% | Yellow battery icon |
| 10% | Red icon + "Low Battery" warning |
| 5% | "Charge soon or data loss possible" |
| <2% | Auto-save and shutdown |

## Maintenance

### Weekly

- Wipe screen with microfiber cloth
- Check mounting tightness
- Verify remote battery (press button, LED should flash)

### Monthly

- Full charge/discharge cycle
- IMU calibration
- Check for firmware updates

### Storage

If storing for >1 month:

1. Charge to 60-70%
2. Power off completely
3. Store in cool, dry place
4. Recharge every 3 months

## Troubleshooting

!!! question "Screen won't respond?"
    - Clean screen with microfiber cloth
    - Try hard reset: Hold power 10 seconds
    - Check battery charge

!!! question "Mounting keeps loosening?"
    - Use provided velcro extender for larger tubes
    - Consider zip tie backup through velcro loops
    - Check for oil/grease on tube surface

!!! question "Remote range seems short?"
    - Replace CR2032 battery in remote
    - Check for metal objects between remote/CoreS3
    - Typical range: 100m+ in open space, 30-50m with obstacles
