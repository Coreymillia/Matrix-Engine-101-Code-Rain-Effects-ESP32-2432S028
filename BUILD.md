# 🛠️ Matrix101CP Build Guide

**Complete build instructions for Matrix101CP - Complete Portal Edition**

---

## 🚀 **Quick Build (Recommended)**

### **Prerequisites:**
- **PlatformIO Core** (command line) or **PlatformIO IDE**
- **USB-C Cable** (data capable, not charge-only)  
- **Cheap Yellow Display** (CYD) board

### **One-Command Build & Flash:**
```bash
git clone https://github.com/[your-username]/Matrix101CP
cd Matrix101CP
pio run --target upload
```

That's it! The portal will auto-start on first boot.

---

## 📋 **Detailed Build Process**

### **1. Environment Setup**

#### **Option A: PlatformIO Core (Command Line)**
```bash
# Install Python 3.7+ if not already installed
python3 --version

# Install PlatformIO
pip install platformio

# Verify installation  
pio --version
```

#### **Option B: PlatformIO IDE (Visual Studio Code)**
1. Install **Visual Studio Code**
2. Add **PlatformIO Extension** from marketplace
3. Restart VS Code
4. PlatformIO icon should appear in left sidebar

### **2. Hardware Connection**
1. Connect CYD to computer via **USB-C cable**
2. **Windows**: Install CH340 drivers if needed
3. **Linux**: Add user to `dialout` group: `sudo usermod -a -G dialout $USER`
4. **macOS**: Install Silicon Labs CP210x drivers if needed

### **3. Project Setup**
```bash
# Clone the repository
git clone https://github.com/[your-username]/Matrix101CP
cd Matrix101CP

# Verify project structure
ls -la
# Should see: src/ lib/ platformio.ini README.md
```

### **4. Build Process**
```bash
# Clean previous builds (optional)
pio run --target clean

# Build firmware
pio run

# Expected output:
# RAM: [===       ] 28.3% (used 92788 bytes from 327680 bytes)  
# Flash: [======= ] 68.6% (used 899109 bytes from 1310720 bytes)
```

### **5. Flash to Device**
```bash
# Auto-detect port and flash
pio run --target upload

# Manual port specification (if auto-detect fails)
pio run --target upload --upload-port /dev/ttyUSB0    # Linux
pio run --target upload --upload-port COM3           # Windows  
pio run --target upload --upload-port /dev/cu.usbserial-*  # macOS
```

---

## 🔧 **Advanced Build Options**

### **Custom Build Environments**

#### **Debug Build (More Serial Output):**
```bash
pio run -e esp32dev_debug --target upload
```

#### **Optimized Release Build:**
```bash  
pio run -e esp32dev_release --target upload
```

### **Build Configuration** 
The `platformio.ini` file controls build settings:

```ini
[env:esp32dev]
platform = espressif32
board = esp32dev
framework = arduino
monitor_speed = 115200

; Graphics libraries
lib_deps = 
    moononournation/GFX Library for Arduino@^1.4.7
    paulstoffregen/XPT2046_Touchscreen
    
; Build optimizations    
build_flags = 
    -DCORE_DEBUG_LEVEL=1
    -DBOARD_HAS_PSRAM=0
    
; Upload settings
upload_speed = 460800
monitor_filters = esp32_exception_decoder
```

### **Memory Optimization**

#### **Reduce Flash Usage:**
- Remove unused effects from `main.cpp`
- Adjust `MAX_MODES` constant
- Comment out complex effects like QUANTUM

#### **Reduce RAM Usage:**  
- Lower `MATRIX_HEIGHT` or `MATRIX_WIDTH`
- Reduce character buffer sizes
- Simplify complex effect algorithms

---

## 🐛 **Troubleshooting Build Issues**

### **Common Build Errors:**

#### **"Library not found"**
```bash
# Clear library cache and rebuild
pio pkg uninstall --global
pio run --target clean
pio run
```

#### **"Port access denied"** 
```bash  
# Linux: Add user to dialout group
sudo usermod -a -G dialout $USER
# Log out and back in

# Windows: Check Device Manager for correct COM port
# macOS: Try different /dev/cu.usbserial-* ports
```

#### **"Flash write failed"**
```bash
# Hold BOOT button while flashing
# Try lower upload speed in platformio.ini:
# upload_speed = 115200

# Check USB cable (must be data-capable)
# Try different USB port
```

#### **"Compilation error"**
```bash
# Update PlatformIO
pio upgrade

# Clean and rebuild
pio run --target clean
pio run
```

### **Hardware-Specific Issues:**

#### **CYD Variant Compatibility:**
- **ESP32-2432S028**: Standard 2.8" - fully supported ✅
- **ESP32-2432S032**: Standard 3.2" - fully supported ✅  
- **Clone boards**: May need pin modifications ⚠️
- **Other ESP32 TFT**: Likely incompatible ❌

#### **Display Driver Issues:**
```cpp
// Verify your CYD uses ILI9341 (should be standard)
// If different driver needed, modify in main.cpp:
#include <Arduino_ILI9341.h>  // Change this line if needed
```

---

## 📊 **Build Performance Metrics**

### **Expected Build Times:**
- **First Build**: 2-5 minutes (downloads libraries)
- **Incremental**: 10-30 seconds
- **Clean Build**: 1-2 minutes  
- **Flash Time**: 15-25 seconds

### **Resource Requirements:**
- **Disk Space**: ~500MB (includes PlatformIO tools)
- **Build RAM**: 1GB+ recommended
- **Flash Size**: 899KB firmware + bootloader
- **Available Flash**: ~2.4MB remaining for future expansion

### **Optimization Results:**
```
Original ESP32 specs: 4MB Flash, 320KB RAM
Matrix101CP usage:   68.6% Flash, 28.3% RAM  
Performance:         60 FPS sustained
Power draw:          ~200mA @ 5V
```

---

## 🔬 **Development Build**

### **For Contributors & Developers:**

#### **Enable Debug Output:**
```ini
; Add to platformio.ini [env] section
build_flags = 
    -DCORE_DEBUG_LEVEL=4    ; Max debug output
    -DDEBUG_MATRIX=1        ; Custom Matrix debugging
```

#### **Serial Monitor:**
```bash  
# Monitor serial output during runtime
pio device monitor --baud 115200

# Common debug output:
# ✅ MULTI-EFFECT SCREENSAVER INITIALIZED  
# 🌐 WiFi Control Portal started: 'Matrix101_Control'
# 📱 Matrix effects running! Connect to WiFi to configure
```

#### **Memory Analysis:**
```bash
# Detailed memory report
pio run --target size

# Memory map analysis
pio run --verbose | grep -A 20 "Memory Usage"
```

---

## 🚀 **Production Deployment**

### **For eBay/Commercial Sales:**

#### **Pre-Flash Multiple Devices:**
```bash
# Batch flash script (Linux/macOS)
for port in /dev/ttyUSB*; do
    echo "Flashing $port"
    pio run --target upload --upload-port $port
    sleep 5
done
```

#### **Quality Assurance:**
1. **Flash Verification**: Power cycle, verify Matrix effects start
2. **Portal Test**: Connect to "Matrix101_Control", configure settings  
3. **Persistence Test**: Power cycle, verify settings saved
4. **Performance Test**: Run for 1+ hours, check for stability

#### **Customer Instructions:**
Include these key points for buyers:
- WiFi portal opens automatically on first boot
- Matrix effects start immediately - working properly!
- Connect to "Matrix101_Control" to customize  
- Boot button works for manual control
- Portal reopens after power cycles (until configured)

---

*Ready to build the future of Matrix screensavers? Let's code the Matrix! 🌿⚡*