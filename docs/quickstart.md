# Quick Start Guide

Get up and running with AppGatePro in under 5 minutes!

!!! info "Your System Includes External Devices"
    Your AppGatePro system includes external lights and breakbeam timer. This Quick Start covers basic operation with just the CoreS3 main unit. For full system setup with external devices, see **[External Devices Setup](external-devices.md)** after completing this guide.

## Before You Begin

!!! warning "Battery Check"
    Ensure both the CoreS3 main unit and remote are fully charged before first use. Connect via USB-C and charge until the LED shows solid green.

## Step 1: Power On

1. Press and hold the **Power button** on the CoreS3 for 2 seconds
2. Wait for the boot screen showing the AppGatePro logo
3. You should see the main menu within 5 seconds

```
╔══════════════════════════════════╗
║      APPGATEPRO v2.4.1          ║
║                                  ║
║   [1] Start Gate Timing         ║
║   [2] Sprint Training           ║
║   [3] Cadence Analysis          ║
║   [4] Settings                  ║
╚══════════════════════════════════╝
```

## Step 2: Mount to Bike

!!! tip "Mounting Location"
    Mount the CoreS3 to the frame's **head tube** or **top tube** for best results. Ensure the arrow on the device points **forward** toward the handlebars.

### Mounting Instructions

1. Clean the mounting surface with the provided alcohol wipe
2. Attach the velcro strap through the CoreS3 mounting bracket
3. Position with the **arrow pointing forward**
4. Tighten the strap securely - the unit should not move when shaken
5. Press the CoreS3 into the bracket until it clicks

![Mounting Diagram](images/mounting-diagram.png)

## Step 3: Start Your First Session

=== "Gate Timing Mode"

    1. Select **[1] Start Gate Timing** from main menu
    2. Choose delay type:
        - **Random** (UCI compliant) - recommended
        - **Fixed** - for specific training
    3. Press **OK** to arm the system
    4. You'll see: `ARMED - Waiting for trigger...`
    5. Use the remote control to trigger the gate beep
    6. Pedal hard! The system records for 8 seconds
    7. View your results instantly on screen

=== "Sprint Training Mode"

    1. Select **[2] Sprint Training** from main menu
    2. Set your target distance (10m, 20m, 50m, 100m)
    3. Position at start line
    4. Press **OK** to begin countdown
    5. Sprint when you hear the beep!
    6. System automatically detects finish

## Understanding Your Results

After each run, you'll see key metrics:

| Metric | What It Means |
|--------|---------------|
| **Reaction Time** | Time from beep to first pedal stroke (ms) |
| **Gate Speed** | Average speed first 10m from gate (km/h) |
| **Peak Power** | Maximum power output during start (watts) |
| **Pedal Cadence** | Revolutions per minute in power phase |

!!! success "Your First Run Complete!"
    Data is automatically saved to local memory and uploaded to your cloud dashboard when WiFi is available.

## Next Steps

- **[External Devices Setup](external-devices.md)** - Connect your lights and breakbeam timer
- **[Settings Guide](settings.md)** - Configure all system options
- **[Basic Operation](operation.md)** - Learn about all features and modes
- **[Hardware Setup](hardware.md)** - Advanced mounting and calibration

## Quick Troubleshooting

!!! question "Device won't power on?"
    - Hold power button for full 2 seconds
    - Check battery charge (connect USB-C)
    - Try a hard reset: hold power for 10 seconds

!!! question "Remote not triggering?"
    - Check remote battery (red LED = low battery)
    - Ensure you're within 100m range
    - Re-pair: Settings → Remote → Pair New Device

!!! question "Results seem inaccurate?"
    - Verify arrow points forward on bike
    - Check mounting is secure (no movement)
    - Calibrate: Settings → Sensors → Calibrate IMU
