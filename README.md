# Matrix101 + Continuous WiFi Scanner

🛡️ **The ultimate ESP32 CYD dual-purpose deviceecho ___BEGIN___COMMAND_OUTPUT_MARKER___ ; PS1= ; PS2= ; EC=0 ; echo ___BEGIN___COMMAND_DONE_MARKER___0 ; }* 🌊

## Features

### 🌊 Matrix Mode
- 101 unique matrix rain effect variations
- 12 font sizes with auto-cycling option
- Touch screen and boot button controls
- Auto-advance timing controls
- Speed and brightness settings

### 🛡️ WiFi Scanner Mode
- **Continuous 3-second scanning** (Marauder-style)
- **Real-time threat detection** with 4 severity levels
- **Scrollable network list** with boot button navigation
- **Smart duplicate prevention** using BSSID tracking
- **Attack pattern recognition** (Pineapple, Marauder, Flipper, etc.)
- **Signal anomaly detection** and beacon flood detection
- **Survives extreme RF conditions** that crash other tools

## Controls

- **AP Web Interface**: Switch between Matrix/WiFi modes, configure settings
- **Boot Button**: Navigate matrix effects OR scroll WiFi networks
- **Touch Screen**: Cycle through matrix effects (Matrix mode only)

## Memory Usage

- **RAM**: 28.4% (93KB used)
- **Flash**: 70.3% (922KB used)
- **ESP32 Dev Module** with 4MB flash

## Hardware

- ESP32-2432S028R (Cheap Yellow Display)
- 320x240 ILI9341 TFT display
- XPT2046 resistive touchscreen
- Boot button for navigation

## Build Instructions

```bash
# Clone or download this project
cd /path/to/project

# Build and flash
pio run --target upload
```

## Usage

1. **Power on** - Boots in Matrix mode by default
2. **Connect to AP**: 'Matrix101_Control' (192.168.4.1)
3. **Switch modes** via web interface
4. **WiFi Scanner**: Use boot button to scroll through detected networks

---

**🎯 Perfect combination**: Beautiful screensaver + Professional security tool**
