# Sunshine-interception

[![GitHub license](https://img.shields.io/github/license/kyusieun/Sunshine-interception)](https://github.com/kyusieun/Sunshine-interception/blob/main/LICENSE)

**Sunshine-interception** is a fork of the high-performance, flexible game streaming host [Sunshine](https://github.com/LizardByte/Sunshine), replacing the input handling method from **SendInput** to the **Interception** driver. This project aims to provide broader input device compatibility and potentially lower latency by utilizing the Interception driver.

**Key Changes (SendInput → Interception):**

- **Interception Driver Usage:** Instead of Windows' default `SendInput` API, this project utilizes the [Interception](https://github.com/oblitum/Interception) driver to handle keyboard and mouse input. `SendInput` may not work correctly with some virtual input devices (e.g., Steam Deck controllers) or in environments with certain security software installed. Interception operates at the kernel level, bypassing these limitations and providing more reliable and broader compatibility.
- **Potential Latency Reduction:** The Interception driver may offer lower input latency compared to `SendInput` in some cases (results may vary depending on your environment).
- **Compatibility with Security Software:** Some anti-cheat or security software may block `SendInput`, but Interception is less likely to encounter such issues.

**Why Choose Sunshine-interception?**

- **If you encounter problems with `SendInput`:** If you experience issues with controller, keyboard, or mouse input not being transmitted properly or intermittently disconnecting when playing games remotely, Sunshine-interception might be the solution.
- **If you want the lowest possible input latency:** The Interception driver can potentially provide lower latency, resulting in a more responsive gameplay experience.
- **If you are concerned about conflicts with security software:** As a kernel-level driver, Interception reduces conflicts with security software.

**Installation and Usage:**

1.  **Install the Interception Driver:** First, you need to install the Interception driver. Refer to the [Interception driver installation guide](https://github.com/oblitum/Interception) for installation instructions. Make sure to use the **command line installer**, and **reboot** your system after installation.
2.  **Build or Download Sunshine-interception:**
    - **Build (Advanced Users):** Follow the build instructions for [Sunshine](https://github.com/LizardByte/Sunshine), but use the source code from this repository ([https://github.com/kyusieun/Sunshine-interception](https://github.com/kyusieun/Sunshine-interception)). The build process is identical to the original Sunshine.
    - **Download (Recommended):** You can download a pre-built Sunshine-interception executable from the Releases section of this repository. (If there is no Releases section, there may not be a release yet. In this case, you will need to build it.)
3.  **Configure Sunshine-interception:** Run Sunshine-interception and configure it through Sunshine's web interface. The settings are almost identical to the original Sunshine.

**Important Notes:**

- The Interception driver operates at the kernel level, so there is a _very_ small, but non-zero, chance of causing system issues. Please install and use it with caution. If you encounter any problems, you can uninstall the driver and reboot your system.
- You _must_ install the Interception driver using the **command line installer**.
- You _must_ **reboot** your system after installing the Interception driver.
- Not all anti-cheat programs allow the Interception driver. Check the anti-cheat policy of the game before playing online multiplayer games.

**License:**

This project is distributed under the [GPLv3 License](https://github.com/kyusieun/Sunshine-interception/blob/main/LICENSE) (same as the original Sunshine project). The Interception driver follows a separate license.

---

**Disclaimer:**

This project is a fork of Sunshine and utilizes the Interception driver. While efforts have been made to ensure stability and compatibility, there is always a (very small) risk associated with using kernel-level drivers. Use this software at your own risk. The developers are not responsible for any issues caused by the use of this software or the Interception driver.
