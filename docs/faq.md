# Frequently Asked Questions

Quick answers to common questions about AppGatePro.

## General Questions

### What is AppGatePro?

AppGatePro is a comprehensive BMX gate timing and biomechanical analysis system. It provides UCI-compliant random start timing, real-time performance analytics, and cloud-based session tracking at a fraction of the cost of commercial timing systems.

### How much does it cost?

- **Complete system:** £45-85 depending on configuration
- **No subscriptions** - Cloud features included free
- **Compare to:** Commercial systems £10,000-50,000

### Is it UCI compliant?

**Yes!** AppGatePro implements UCI-compliant random start delays:

- Random delay: 0.1 to 2.5 seconds
- Cryptographically secure randomization
- Validation logging for official use

### Can I use it for official competitions?

The timing is UCI-compliant, but you'd need to check with your local federation about approved timing equipment lists. AppGatePro is primarily designed for training, though the timing accuracy meets or exceeds official requirements.

## Hardware Questions

### What's included in the system?

- CoreS3 main unit (ESP32-based with IMU)
- JNS_Lights (external start light system)
- JNS_Timing (breakbeam timer with transmitter/receiver)
- Wireless remote control
- Mounting bracket and velcro straps
- USB-C charging cable
- Quick start guide with QR code
- Access to cloud dashboard

### What bike sizes does it fit?

All standard BMX bikes:

- 20" wheels (all tube diameters)
- 24" cruisers
- Works with micro, mini, junior, pro, and cruiser frames

### Is it waterproof?

**Water resistant but not waterproof:**

- Splash resistant: Light rain OK
- Not submersion proof: Don't submerge or use in heavy rain
- If wet: Dry before charging

### How long does the battery last?

**CoreS3:**

- Training session: 5-6 hours (WiFi off)
- With WiFi: 3-4 hours
- Standby: 30+ days

**Remote:**

- CR2032 battery: 12+ months typical use

### Can I mount it on multiple bikes?

Yes! The velcro mounting system makes it easy to move between bikes. Just ensure proper calibration and tire diameter settings for each bike.

## Operation Questions

### How accurate is the timing?

- **Reaction time:** ±1ms accuracy
- **Speed:** ±0.1 km/h at gate speeds
- **Power:** ±5W (dependent on accurate weight input)
- **IMU sampling:** 200Hz (5ms intervals)

Accuracy equals or exceeds commercial systems costing 100x more.

### Does it work indoors?

**Yes!** AppGatePro works anywhere:

- Indoor tracks
- Outdoor tracks  
- Driveways / parking lots
- No GPS required (all IMU-based)

### Can multiple riders use one system?

**Sort of:**

- One CoreS3 can store multiple rider profiles
- One rider at a time (can't time multiple gates simultaneously)
- Best for: Family training, club coaches rotating between riders
- For simultaneous timing: Need one system per gate

### Do I need WiFi?

**No, but it's useful:**

**Works without WiFi:**

- All timing modes
- Data recording
- View past sessions
- All core features
- External device communication (uses ESP-NOW, not WiFi)

**Requires WiFi:**

- Cloud backup
- Web dashboard access
- Firmware updates
- Remote session sharing

### How do external devices connect?

**ESP-NOW wireless protocol:**
- 2.4GHz communication (not WiFi)
- Ultra-low latency (<10ms typical)
- Range: 50-100m outdoors
- Direct device-to-device (no router needed)
- Automatic latency compensation

**Setup process:**
1. Power on external device (enters pairing mode)
2. Navigate to Settings on CoreS3
3. Tap device icon (LIGHTS or TIMER)
4. System scans and pairs automatically
5. Green glow indicates successful pairing

See **[External Devices Setup](external-devices.md)** for complete guide.

### Do I need the external lights and timer?

**No - the system works standalone:**
- CoreS3 displays visual sequence on screen
- Audio beeps provide timing cues
- Internal timer can be used instead of breakbeam
- Perfect for solo practice

**External devices add:**
- Professional competition experience
- Visible light sequence at start line
- Precise speed measurement with breakbeam
- Better for multiple riders (easier to see lights)
- UCI-compliant setup for official training

### What's the difference between internal and external timing?

**Internal Timer Mode:**
- Uses CoreS3 countdown (1-10 seconds configurable)
- Timer expires at set duration
- Speed = 0.00 (no beam sensor)
- Good for: Technique practice, reaction time focus

**External Timer Mode (JNS_Timing):**
- Uses breakbeam sensor at finish line
- Timer stops when beam is broken
- Speed calculated automatically (Distance ÷ Time)
- 2-minute safety timeout if no beam break
- Good for: Accurate performance measurement, sprint training

### Can I use without a coach?

**Absolutely!** AppGatePro is designed for self-coaching:

- Instant on-screen feedback
- Track your own progress
- Web dashboard with analytics
- Compare runs side-by-side
- No coach required

## Data & Cloud Questions

### Where is my data stored?

**Two places:**

1. **Locally** - On CoreS3 internal storage (~500 sessions)
2. **Cloud** - Auto-uploaded when WiFi available (unlimited storage)

### Can I access my data from phone/computer?

**Yes!** Login to **dashboard.appgatepro.com**

- View all sessions
- Detailed analytics and graphs
- Export data (CSV, JSON, PDF)
- Share sessions with coaches
- Compare across dates

### What if I don't want cloud storage?

No problem! Cloud is optional:

- Disable: Settings → Cloud → Auto-Upload: Off
- All data stays local on device
- Export via USB anytime
- Can enable cloud later without losing data

### Can I export my data?

**Two export methods:**

1. **USB Export**
   - Connect to computer
   - Export as CSV files
   - Import to Excel, Google Sheets, etc.

2. **Cloud Export**
   - Login to dashboard
   - Download any format (CSV/JSON/PDF)
   - Individual sessions or bulk export

### How do I share data with my coach?

**From web dashboard:**

1. Open session
2. Click "Share"
3. Enter coach email
4. They receive view-only link
5. No account required for viewing

## Training Questions

### What training modes are available?

1. **Gate Timing** - UCI-compliant random starts
2. **Sprint Training** - Timed sprints (10m to 100m)
3. **Cadence Analysis** - Pedaling efficiency tracking
4. **Interval Timer** - Custom work/rest intervals

### What metrics does it measure?

**For gate starts:**

- Reaction time (beep to movement)
- Gate exit speed (0-10m average)
- Peak power output
- Average cadence
- Wheelie timing and distance
- Pitch angle through start
- Acceleration curve

### How does it detect wheelies?

Using pitch angle from the IMU:

- Detects when front wheel lifts
- Measures duration of wheelie
- Calculates distance traveled in wheelie
- Shows timing relative to gate exit

### Can it help me improve?

**Yes! Several ways:**

- **Instant feedback** - See results immediately
- **Progress tracking** - Compare to past runs
- **PR indicators** - Know when you beat personal records
- **Trend analysis** - Web dashboard shows improvement over time
- **Identify weaknesses** - Metrics show specific areas to work on

### Does it replace coaching?

**No, it complements coaching:**

- Provides objective data coaches can use
- Makes practice more focused
- Helps riders self-coach between sessions
- Great tool for coaches to track multiple riders

## Technical Questions

### What sensors does it use?

**6-axis IMU (Inertial Measurement Unit):**

- 3-axis accelerometer
- 3-axis gyroscope  
- Sampling rate: 200Hz
- Complementary filter for sensor fusion

### How does it calculate speed without GPS?

**Integration of acceleration data:**

1. IMU measures acceleration in 3D
2. Gravity compensation using gyroscope
3. Pitch angle correction
4. Numerical integration: acceleration → velocity
5. Tire diameter for distance calculation

This is why mounting orientation and tire diameter are critical!

### What about drift/error accumulation?

**Multiple techniques prevent drift:**

- Zero-velocity updates (when bike is still)
- Complementary filtering (combines accel + gyro)
- Regular calibration recommended
- 8-second recording windows (limits drift accumulation)

For gate starts (8 seconds), drift is negligible (<1% error).

### Can I update the firmware?

**Yes, over WiFi:**

1. Settings → System → Check for Updates
2. Download when available
3. Install (takes 2-3 minutes)
4. Device reboots with new firmware

**Never interrupt update** - keep on charger during process.

### What if firmware update fails?

Device has recovery partition:

- If update fails, auto-rolls back to previous version
- You'll see "Update failed - rolled back to vX.X.X"
- Try update again with better WiFi signal
- If repeatedly fails, contact support

## Purchase & Support Questions

### Where can I buy it?

Currently available through:

- **Direct:** appgatepro.com
- **Beta program:** Limited systems available for testing

### Is there a trial period?

Contact us about our **Beta Testing Program:**

- Free system for qualified testers
- Provide feedback on features
- Post progress on social media
- Help shape future development

### What's the warranty?

- **12 months** from purchase date
- Covers manufacturing defects and hardware failures
- Does NOT cover: drops, water damage, battery wear

### How do I get support?

**Email:** support@appgatepro.com

**Include:**

- Device serial number (Settings → System → About)
- Firmware version
- Description of issue
- What you've tried

**Response time:** Usually <24 hours weekdays

### Can I get replacement parts?

**Available separately:**

- Mounting brackets
- Velcro straps
- USB-C cables
- Remote controls
- Batteries (device is NOT user-serviceable for main battery)

Contact support@appgatepro.com for parts orders.

## Comparison Questions

### How does it compare to [commercial system]?

**Advantages of AppGatePro:**

- 100-200x cheaper (£45-85 vs £10,000-50,000)
- Portable (fits in pocket)
- Cloud analytics included
- No subscription fees
- Regular firmware updates

**Commercial systems advantages:**

- Multi-rider simultaneous timing
- Integrated with track infrastructure  
- Photo finish capabilities
- Official UCI approval for competition

**AppGatePro is for:** Individual training, club practice, coaching  
**Commercial systems are for:** Official competitions, professional tracks

### Can I use a smartwatch or phone instead?

**Phones/watches limitations:**

- Can't measure acceleration accurately (wrong mounting position)
- GPS too slow (1-5Hz vs 200Hz)
- GPS doesn't work indoors
- Not designed for BMX-specific metrics
- No UCI-compliant timing

**AppGatePro advantages:**

- Designed specifically for BMX gate starts
- Proper mounting position for accurate data
- Works indoors
- BMX-specific analytics (wheelies, gate exit speed, etc.)
- Much more accurate for short sprints

### Is it better than timing with a stopwatch?

**Yes, dramatically:**

**Stopwatch:**

- Human reaction time (~200ms error)
- Only measures total time
- No detailed analytics
- Hard to be consistent

**AppGatePro:**

- ±1ms accuracy
- Reaction time, speed, power, cadence, etc.
- Detailed analytics on every run
- Perfectly consistent

---

## Still Have Questions?

- **Email:** support@appgatepro.com
- **Website:** appgatepro.com
- **Dashboard:** dashboard.appgatepro.com

**Beta Testers:** Share your results and tag us on social media!
