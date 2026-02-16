# Troubleshooting

Common issues and solutions for AppGatePro system.

## Quick Diagnostics

Before diving into specific issues, run the built-in diagnostic:

1. Navigate: **Settings → System → Diagnostics**
2. System tests:
   - Battery health
   - IMU sensors
   - Screen response
   - Storage space
   - WiFi connectivity
3. Review results for any ❌ failures

## Power & Charging Issues

### Device Won't Power On

!!! question "Symptom: No response when pressing power button"

**Try these steps in order:**

1. **Hold power button longer** - Must hold for full 2 seconds
2. **Check charge** - Connect USB-C cable, look for charging LED
3. **Try different cable/charger** - Use known-good USB-C cable and 5V adapter
4. **Hard reset** - Hold power button for 10 seconds, release, try powering on
5. **Battery depleted** - Leave on charger for 30 minutes, then try again

**Still not working?** Contact support with LED behavior description.

### Device Powers Off Randomly

!!! question "Symptom: Shuts down during use"

**Most common causes:**

1. **Low battery** - Check battery icon. Charge if below 20%
2. **Loose USB connection** - If mounted, ensure USB isn't pulling on port
3. **Overheating** - Rare, but device will shutdown if >60°C
   - Let cool for 10 minutes
   - Ensure mounting allows air circulation
4. **Firmware crash** - Check: Settings → System → Crash Logs
   - Update firmware if available

### Won't Charge / Charging Slowly

!!! question "Symptom: LED not turning red, or charges very slowly"

**Check these:**

1. **Cable quality** - Use provided USB-C cable or high-quality replacement
2. **Power source** - Must be 5V, 1A minimum. USB 2.0 may be too slow
3. **Port cleanliness** - Inspect USB-C port for lint/debris. Clean gently with toothpick
4. **Temperature** - Device won't charge if <0°C or >45°C
5. **Battery health** - Settings → System → Battery Info
   - If "Health: Poor", battery may need replacement

**Charge time expectations:** 0-100% should take 90-120 minutes

## Sensor & Accuracy Issues

### Inaccurate Measurements

!!! question "Symptom: Speed/power readings seem wrong"

**Calibration checklist:**

1. **Verify orientation** - Arrow MUST point forward
   ```
   Correct:  [→ CoreS3] ====> (front of bike)
   Wrong:    [← CoreS3] ====> (front of bike)
   ```

2. **Check mounting** - Shake bike, CoreS3 should not move at all
   - If loose, tighten velcro strap
   - Consider zip-tie backup

3. **Recalibrate IMU**
   - Settings → Sensors → Calibrate IMU
   - Must be on flat surface
   - Don't move for full 10 seconds

4. **Verify tire diameter** - Settings → Bike → Tire Diameter
   - Wrong tire size = wrong speed calculations
   - Measure: Roll bike one complete rotation, measure distance

5. **Update firmware** - Old firmware may have sensor bugs

### No Data Recording

!!! question "Symptom: Timer runs but no data saved"

1. **Check storage space** - Settings → Data → Storage
   - If <5% free, delete old sessions
2. **Verify sensors** - Run diagnostic test (Settings → System → Diagnostics)
3. **IMU failure** - If diagnostic shows IMU error:
   - Power cycle device
   - Recalibrate IMU
   - If persists, contact support

### "IMU Error" Message

!!! question "Symptom: Error message on startup or during use"

**Step-by-step fix:**

1. Remove CoreS3 from bike
2. Place on flat, stable surface
3. Power off completely (hold power 5 seconds)
4. Wait 10 seconds
5. Power on
6. Immediately: Settings → Sensors → Calibrate IMU
7. Keep perfectly still during calibration

**If error persists:**

- Firmware update may be needed
- Check for physical damage to device
- Contact support - may be hardware issue

## Remote Control Issues

### Remote Not Triggering

!!! question "Symptom: Pressing remote button doesn't trigger beep"

**Troubleshooting steps:**

1. **Check pairing** - Settings → Remote → Status
   - Should show "Remote #XXXX: Connected"
   - If "No remote paired", need to pair

2. **Test remote battery**
   - Press button away from CoreS3
   - LED should flash bright green
   - Dim or no flash = dead battery
   - Replace with CR2032 coin cell

3. **Check range** - Must be within 100m
   - Test closer (5m) to eliminate range issues

4. **Re-pair remote**
   - Settings → Remote → Remove Device
   - Then: Add Device
   - Hold remote button 3 seconds until LED flashes rapidly
   - Confirm pairing

5. **Interference check**
   - Large metal objects can block signal
   - Try from different location

### Multiple Remotes Interfering

!!! question "Symptom: Other riders' remotes triggering your device"

**Solution:**

- Each CoreS3 can pair with specific remotes only
- Other remotes should NOT trigger your device
- If they do:
  1. Settings → Remote → Remove All Devices
  2. Re-pair only your remote(s)
  3. Verify: Settings → Remote → Show Paired Devices

## Screen & Display Issues

### Screen Not Responding

!!! question "Symptom: Touch screen doesn't respond to taps"

1. **Clean screen** - Use microfiber cloth (included)
2. **Remove screen protector** - If installed, remove and test
3. **Check for moisture** - Dry completely if damp
4. **Calibrate touch** - Settings → Display → Calibrate Touch
5. **Hard reset** - Hold power 10 seconds, restart

### Screen Too Dim / Too Bright

!!! question "Symptom: Can't see screen in sunlight or too bright at night"

**Adjust brightness:**

- Settings → Display → Brightness
- Options: Auto / Low / Medium / High
- Auto uses light sensor for optimal brightness

**Sunlight visibility:**

- Use maximum brightness
- Shield screen with hand temporarily
- Consider matte screen protector (reduces glare)

### Display Shows Wrong Information

!!! question "Symptom: Garbled text, incorrect metrics"

1. **Soft reset** - Settings → System → Reboot
2. **Factory reset display** - Settings → Display → Reset
   - Note: Does NOT delete your data
3. **Firmware update** - Check for available updates

## WiFi & Connectivity Issues

### Won't Connect to WiFi

!!! question "Symptom: Can't connect to home/track WiFi"

**Common solutions:**

1. **Verify password** - Settings → WiFi → Configure
   - Re-enter password carefully
   - Check for caps lock/special characters

2. **WiFi band** - CoreS3 supports 2.4GHz only
   - If your router is 5GHz only, CoreS3 won't connect
   - Enable 2.4GHz band in router settings

3. **Signal strength** - Move closer to router
   - Need at least 2 bars for stable connection

4. **Router compatibility**
   - Some public/track WiFi require web login
   - These won't work with CoreS3
   - Use mobile hotspot instead

5. **Forget and reconnect**
   - Settings → WiFi → Forget Network
   - Scan and connect again

### Cloud Sync Not Working

!!! question "Symptom: Sessions not appearing on web dashboard"

**Check these:**

1. **WiFi connected?** - Must be online for sync
2. **Auto-upload enabled?** - Settings → Cloud → Auto-Upload
3. **Manual sync** - Settings → Cloud → Sync Now
4. **Account linked?** - Settings → Cloud → Account
   - Must sign in to dashboard first
   - Then link device using QR code

**Sync status indicators:**

- ☁ = Synced
- ☁↑ = Uploading
- ☁✗ = Sync error (check internet)

## Data & Storage Issues

### "Storage Full" Warning

!!! question "Symptom: Device warns storage is full"

**Free up space:**

1. **Delete old sessions** - Settings → Data → Manage Storage
   - Select sessions to delete
   - Tip: Export to USB first if needed

2. **Clear cache** - Settings → Data → Clear Cache
   - Removes temporary files
   - Does NOT delete your sessions

3. **Upload to cloud** - Settings → Cloud → Sync All
   - Once uploaded, can safely delete local copies

**Storage capacity:** ~500 sessions or 40,000 individual runs

### Lost Data / Missing Runs

!!! question "Symptom: Past sessions disappeared"

**Recovery options:**

1. **Check cloud** - Login to dashboard.appgatepro.com
   - Data may be safe in cloud even if deleted locally

2. **Check USB backup** - If you've exported before
   - Data can be re-imported from CSV files

3. **Recent deletions** - Settings → Data → Recently Deleted
   - Undelete sessions within 30 days

**Prevention:**

- Enable cloud auto-upload (Settings → Cloud)
- Regular USB exports (weekly recommended)
- Don't use "Delete All" unless certain

## Error Messages

### "UCI Compliance Failed"

!!! warning "Meaning: Random delay validation failed"

**This is rare. Causes:**

- Firmware bug (update firmware)
- IMU timing drift (recalibrate IMU)
- System clock error (sync with WiFi)

**If persistent, contact support** - this may indicate hardware issue

### "Calibration Required"

!!! info "Meaning: IMU needs recalibration"

**When this appears:**

- After firmware update
- After physical impact/drop
- If device hasn't been calibrated in 30+ days

**Solution:** Settings → Sensors → Calibrate IMU

### "Temperature Warning"

!!! warning "Meaning: Device too hot or too cold"

**Safe operating range:** 0°C to 45°C (32°F to 113°F)

- **Too hot**: Let cool in shade for 10 minutes
- **Too cold**: Warm in pocket before use

## Performance Issues

### Slow / Laggy Interface

!!! question "Symptom: Menu navigation is slow"

**Improvements:**

1. **Close background tasks** - Settings → System → Running Apps
2. **Clear cache** - Settings → Data → Clear Cache
3. **Reduce screen effects** - Settings → Display → Animations: Off
4. **Storage space** - Ensure >20% free space
5. **Restart device** - Often fixes temporary slowness

### Battery Drains Too Fast

!!! question "Symptom: Battery doesn't last as long as expected"

**Optimize battery life:**

1. **Disable WiFi** when not needed
   - Quick toggle: Swipe down → WiFi icon
   - Saves ~40% battery

2. **Lower brightness** - Settings → Display → Brightness: Low or Auto

3. **Enable auto-sleep** - Settings → Display → Sleep: 2 minutes

4. **Check battery health** - Settings → System → Battery Info
   - If health <70%, battery may need replacement

5. **Close unused apps** - Settings → System → Running Apps

**Expected battery life:**

- Gate timing (WiFi off): 5-6 hours
- With WiFi on: 3-4 hours
- Standby: 30+ days

## Still Having Issues?

### Before Contacting Support

Run through this checklist:

- [ ] Firmware updated to latest version?
- [ ] IMU calibrated recently?
- [ ] Tried hard reset (power off, wait 30 seconds, power on)?
- [ ] Checked diagnostic results?
- [ ] Searched FAQ page?

### Contact Information

**Email Support:** support@appgatepro.com

**Include in your message:**

1. Device serial number (Settings → System → About)
2. Firmware version
3. Detailed description of issue
4. Steps you've already tried
5. Any error messages (screenshot if possible)

**Response time:** Usually within 24 hours weekdays

### Warranty Information

- **Standard warranty:** 12 months from purchase
- **Covers:** Manufacturing defects, hardware failure
- **Does NOT cover:** Drops, water damage, normal battery wear

**RMA Process:**

1. Email support with issue description
2. Diagnostic steps provided
3. If faulty, RMA number issued
4. Ship device with RMA number
5. Replacement/repair within 7-10 business days

---

## FAQ

**Q: How often should I calibrate the IMU?**  
A: Monthly is recommended, or whenever you notice accuracy issues.

**Q: Can I use while charging?**  
A: Yes, but cable may interfere with mounting. Best to charge between sessions.

**Q: What happens if I drop the device?**  
A: CoreS3 is built tough but not indestructible. After any impact, recalibrate IMU and run diagnostics.

**Q: Why does my remote need to be close sometimes?**  
A: Check remote battery. Weak battery = reduced range (normal is 100m+).

**Q: Can I share data with my coach?**  
A: Yes! Use cloud sharing: Dashboard → Session → Share → Enter coach email.
