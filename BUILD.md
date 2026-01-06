# Build Instructions

## Quick Start
```bash
# Install PlatformIO
pip install platformio

# Build and flash
cd Matrix101
pio run --target upload
```

## Hardware
- ESP32-2432S028 "Cheap Yellow Display"
- USB-C cable for programming
- No additional wiring required

## Controls
- Touch screen: Cycle through modes 0-100
- Boot button: Toggle auto-scroll
- Long press boot: Enable/disable auto-scroll

## Performance
- Flash: 28.6% usage (71.4% free)
- RAM: 21.3% usage (78.7% free)
- Frame rate: 60fps maintained
- Modes: 101 complete effects

## Troubleshooting
- Ensure ESP32 is connected via USB-C
- Check that PlatformIO can detect the board
- Verify all dependencies are installed
- Flash memory is sufficient for all 101 modes

The matrix awaits... 🌌