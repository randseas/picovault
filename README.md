# Picovault

An offline hardware password and totp token manager based on the Raspberry Pi Pico 2. Designed for security-conscious users who prefer local and verifiable credential management.

-

### Features
- **Offline Security:** Your master password and totp secrets never leave the device.
- **HID emulation:** Acts as a generic keyboard to type passwords and totp codes directly into your device.
- **Navigation:** 3-button simple control (`Up`, `Down`, `hold 3s = Enter`/`1 click = Escape`).

--

### Bill of Materials
| Component | Amount | Description |
| :--- | :--- | :--- |
| **Raspberry Pi Pico 2** | `1x` | The core controller RP2350. |
| **OLED Display** | `1x` | 128x64 monochrome OLED (I2C or SPI interface can be selected inside `Cargo.toml`). |
| **Buttons** | `3x` | Tactile momentary switches. |
| **Connectivity** | `1x` | USB Micro-B cable. |

---

### 3D-printed Enclosure

The `3d/` directory includes the necessary files for printing the enclosure.

---

### Circuit Diagram

| Pico 2 Pin | Device Pin (I2C) | Device Pin (SPI) |
| :--- | :--- | :--- |
| `GP4` | `SDA` | `MOSI` |
| `GP5` | `SCL` | `SCK` |
| `GP6` | `Button 1 (Up)` | - |
| `GP7` | `Button 2 (Down)` | - |
| `GP8` | `Button 3 (Enter)` | - |
| `GP9` | - | `DC (Data/Command)` |
| `GP10`| - | `CS (Chip Select)` |

---

### Building
1. **Toolchain:** Install Rust (`rustup`).
2. **Environment:** Setup the `thumbv8m.main-none-eabihf` target.
3. **Compile:**
```bash
   cargo build --release
```
4. **Flash:** Copy the generated .uf2 file to your Pico 2 in Bootloader mode.

---

### Contributing

Any contributions you make are greatly appreciated.
If you have a suggestion that would make this project better, please fork the repo and create a pull request.

1. Create a fork
2. Create your feature branch `git checkout -b feature/AmazingFeature`
3. Commit your changes `git commit -m 'Add some AmazingFeature'`
4. Push to the branch `git push origin feature/AmazingFeature`
5. Open a pull request

---

### License
Distributed under the GPLv3 License. See `LICENSE` for more information.
