# Matrix101 Fonts Edition 🌿
**101 Mesmerizing Matrix Effects with Smart Font Cycling System**

Advanced ESP32 Matrix Digital Rain Screensaver for 320x240 TFT Displays

## 🚀 What's New in Fonts Edition
⚡ **Smart Font Cycling**: Automatically cycles through 12 font sizes after completing all 101 modes
🎛️ **Font Control Toggle**: Turn auto font cycling ON/OFF via web portal
📱 **Complete WiFi Portal**: Full control interface with persistent settings
🔧 **Manual Font Selection**: Set specific font size (0-11) via web interface
🎯 **Perfect Mode Flow**: Runs modes 0-100, then cycles font and restarts
🔄 **Visual Feedback**: Shows "FONT X/12" notification when cycling occurs

## 🎭 101 Unique Matrix Effects

### 🌊 Core Matrix Variations (0-19)
- Classic Digital Rain, Binary Rain, GLMatrix 3D
- Speed variants, glitch effects, ghost trails
- Neon green, retro amber, multicolor themes

### 🎨 Advanced Color Series (20-39)  
- Fire (red/orange/yellow), Ice (blue/white/cyan)
- Toxic (sickly green), Cyber (purple/pink)
- Storm (lightning), Blood (dark red), Gold variants

### ⚡ Physics-Based Effects (40-79)
- **Wind Systems**: Lateral column sway, storm combinations
- **Ripple Effects**: Sine wave distortions, tsunami variants  
- **Fracture Physics**: Column splits, cascade reactions
- **Plasma Fields**: Energy distortions, multi-element combos
- **Drip Viscosity**: Blood, honey, acid, mercury, water

### 🎆 Advanced Combinations (80-100)
- **History Effects**: Past paths influence new rain (spacetime memory)
- **Fireworks Integration**: Explosions with matrix physics
- **Multi-Element Hybrids**: RippleWind, FireworksFracture, etc.
- **Entropy Systems**: Order→chaos→collapse→rebirth cycles
- **Tide Breathing**: Global synchronized pulsing effects

## 🔤 Font Cycling System

### **12 Font Sizes Available**
- **Font 0-2**: Small text sizes (compact matrix)
- **Font 3-5**: Medium text sizes (balanced visibility) 
- **Font 6-8**: Large text sizes (bold matrix)
- **Font 9-11**: Extra large text sizes (dramatic effect)

### **Smart Auto-Cycling Logic**
```
Mode Flow: 0 → 1 → 2 → ... → 99 → 100 → (Font Change) → 0 → 1 → ...
```
- Runs all 101 modes (0-100) with current font
- When wrapping from mode 100 back to mode 0: **Changes font size**
- Shows visual "FONT X/12" notification during change
- Continues with all 101 modes in new font size
- Cycles through all 12 fonts infinitely

### **Font Control Features**
- **Toggle Control**: Turn auto-cycling ON/OFF via web portal
- **Manual Selection**: Set specific font (0-11) and disable cycling
- **Persistent Memory**: Font preferences saved to ESP32 flash
- **Immediate Effect**: Manual font changes apply instantly

## 📱 WiFi Control Portal Features

### 🎮 Complete Control Interface
**Access Method**: restart device→ Connect to "Matrix101" WiFi → Browse to 192.168.4.1

**Full Control Panel**:
- 🎯 **Mode Selection**: Choose from 101 effects (0-100)
- 🔤 **Font Size**: Set specific font (0-11) 
- 🔄 **Font Auto-Cycling**: Toggle ON/OFF
- ⏰ **Auto-Advance Timer**: 30s, 1min, 10min, 1hr, or OFF  
- 🏃 **Speed Control**: Slow, Normal, Fast, or Ludicrous
- 💡 **Brightness**: 25%, 50%, 75%, or 100%

### 🔄 Smart Behavior
- Matrix effects continue while portal is active
- Settings apply immediately and persist through reboots
- Portal auto-closes after configuration

## 🛠️ Hardware Requirements

### **ESP32 Development Board with 320x240 TFT**
**Compatible Displays**:
- ESP32-2432S028 "Cheap Yellow Display" (CYD)
- ESP32 with ILI9341 320x240 TFT
- ESP32 with ST7796 320x240 TFT
- Any ESP32 + 320x240 SPI TFT display

**Features Used**:
- Touch screen support (XPT2046) not used.
- Physical button for manual control  -BOOT button.
- WiFi for control portal
- Flash storage for persistent settings

### **Where to Buy**:
- **AliExpress**: Search "ESP32-2432S028" or "Cheap Yellow Display"
- **Amazon**: "ESP32 TFT Display 320x240"
- **eBay**: "CYD ESP32 Display"

## ⚡ Quick Start Guide

### 1. Flash the Firmware
```bash
git clone https://github.com/Coreymillia/Matrix-Engine-101-Code-Rain-Effects-ESP32-2432S028
cd Matrix101GithubFonts  
pio run --target upload
```

### 2. First Boot Experience
- Matrix effects start immediately with font cycling enabled
- Cycles through modes 0-100, then changes font and repeats
- Visual "FONT X/12" notification shows font changes

### 3. Configure Font Settings (Optional)
- **activate WiFi portal
- Connect to **"Matrix101"** WiFi network (no password)
- Set **Font Auto-Cycling** to ON/OFF as desired
- Choose specific **Font Size (0-11)** if desired
- Click **"SAVE SETTINGS & CLOSE PORTAL"**

### 4. Enjoy!
- Portal closes and saves your preferences  
- Matrix effects continue with your font settings
- Settings persist through power cycles

## 🎮 Physical Controls

- **Boot Button Short Press**: Next effect manually  
- **Boot Button Long Press**: Toggle auto-advance on/off
- **Reset Settings**: Available via web portal

## 🔧 Advanced Features

### **Persistent Settings**
- All configurations saved to ESP32 flash memory
- Font preferences survive power loss and reboots
- Manual font selection overrides auto-cycling

### **Performance Optimized**  
- **60 FPS** smooth animations across all effects
- **Efficient memory**: 28% RAM, 69% Flash usage
- **Dual-core optimization** for ESP32 architecture
- **Smart font rendering** with optimized text display

### **Matrix Effect Framework**
Each effect follows proven framework:
- Consistent 60fps performance across all 101 modes
- Smooth transitions between effects and font changes
- Color-coordinated themes with proper contrast
- Physics-based realistic motion systems

## 📊 Technical Specifications

### **Performance Metrics**:
- **Frame Rate**: 60 FPS sustained across all effects
- **Memory Usage**: 92KB RAM (28% of available)  
- **Flash Usage**: 900KB (69% of available)
- **Font Change Time**: <1 second with visual feedback
- **Power Draw**: ~200mA @ 5V typical

### **Compatibility**:
- ✅ ESP32-2432S028 (2.8" CYD)
- ✅ ESP32-2432S032 (3.2" CYD)  
- ✅ ESP32 + ILI9341 320x240 displays
- ✅ ESP32 + ST7796 320x240 displays
- ⚠️ Requires SPI TFT display
- ⚠️ Touch functionality optional

## 🔍 Troubleshooting

### **Font Issues**:
- **Fonts not cycling**: Check "Font Auto-Cycling" setting in web portal
- **Wrong font size**: Use web portal to manually select font (0-11)
- **Font change not visible**: Ensure "FONT X/12" notification appears

### **Common Issues**:
- **Portal won't open**: Hold screen firmly for full 3 seconds
- **Settings not saving**: Complete web portal process, click "SAVE SETTINGS"  
- **Effects not smooth**: Use quality 5V power supply, check connections

## 🎯 Perfect For:
- **Digital Art Displays**: 101 unique visual experiences with font variety
- **Retail Displays**: Eye-catching matrix effects with controllable fonts
- **Home Decoration**: Customizable matrix ambiance with font personality
- **Gifts**: Ultimate Matrix fan present with full control
- **Learning**: ESP32 graphics programming with font management

## 🌟 Version History

**v2026.01.13 - GitHub Fonts Edition** (Current)
- ✅ Smart font cycling system (12 fonts)  
- ✅ Font control toggle in web portal
- ✅ Visual font change notifications
- ✅ Persistent font preferences  
- ✅ 101 total matrix effects
- ✅ Complete WiFi control portal

---

**"Welcome to the Matrix... now with the perfect font for every mood." 🌿⚡🔤**

**Last Updated**: January 13, 2026  
**Version**: GitHub Fonts Edition  
**Total Effects**: 101 unique Matrix variations  
**Font System**: 12 sizes with smart auto-cycling  
**Control Method**: WiFi Portal + Physical Controls  
**Status**: Production Ready ✅
