# TinyCap Changelog & Feature Overview

TinyCap is a local HTTP(S) traffic debugging tool. Once the proxy is enabled, it captures and lists requests from browsers, mobile devices, or other clients, allowing inspection of request/response data for API debugging and protocol analysis.

This document focuses on **UI and functional changes per version**. For implementation details, please refer to the repository history.

---

## 1.1.3 (Current Version)

### Settings (Top-right Gear Menu)

- **Developer Tools**: Now available even in packaged builds. Used for viewing errors and copying console logs.
- **Open Config Directory**: Opens the local folder where TinyCap stores settings and global scripts. Useful for backup, migration, or manual inspection. If no configuration exists yet, it will be created automatically before opening.

### Capture & Scripts

- **Global Scripts**: Fixed an issue where scripts might not take effect when breakpoints were enabled or previously configured.
- **Breakpoints**: Improved stability to reduce unexpected behavior caused by invalid or abnormal breakpoint configurations.

### Request Details

- Fixed layout instability when switching requests.
- Top-level tabs (Overview / Headers / Body / Response, etc.) are now **always visible and fixed in order**, preventing accidental UI shifts when switching requests.
- Empty states are shown instead of hiding sections when no data is available.
- Inner tabs (e.g. Raw / Preview / Post-processed views) only appear when content exists, reducing unnecessary tab switching.

### Independent Windows

(Preferences, Script Manager, Breakpoints / SSL / Throttling settings, About, Replay, Update dialog, Script logs, Certificate guide, etc.)

- Unified window style with custom title bar and standard window controls (minimize / maximize / close).
- Consistent desktop experience across all dialogs.
- Certificate download and guidance windows also follow the same UI standard.

---

## 1.1.2

Improved consistency between light and dark themes across the entire UI.

### Main Window

- Title bar, menus, and window controls now adapt to theme.
- Better contrast in light mode; unified purple-gray style in dark mode.

### Debug Panel

- Right-side panels (Elements / Console / Network / Session) now follow theme styles.
- Improved readability of trees, logs, and request data.
- Device preview area now adapts visually to theme.

### Replay

- Unified styling for replay container, device frame, timeline, and side panels.

### Preferences

- Input fields (e.g. proxy port) now follow consistent styling in dark mode.

---

## 1.1.1

UI and menu restructuring.

### Settings & About

- “Version Changelog” and “About TinyCap” are now separate entries.
- Changelog is prioritized above About.
- About window shows version, runtime environment, and basic tech stack information.

---

## 1.0.1

Improvements in debugging preview, extension workflow, and replay stability.

### Debug Preview

- Improved request routing stability.
- Better synchronization between mirrored device view and real page.
- Console and network data are displayed more accurately.
- Local page debugging no longer forces proxy interception, reducing unnecessary routing issues.
- Fixed scroll and layout issues in mirrored view.

### Request List & Details

- Preserves active tab when switching requests.
- Response body opens in preview mode by default.
- Improved search consistency across raw and parsed content.

### Extension & Launch

- Added guidance for Chrome extension installation.
- Fixed replay timeline synchronization issues.
- Supports `tinycap://` protocol for external launch.

### Session & Replay

- Improved session caching visibility.
- Fixed replay blank screen and scaling issues.
- Replay moved to independent window.

---

## 1.0.0

First public release.

### Capture & Traffic

- Local HTTP(S) proxy server (default port: 8888).
- Captures HTTP/HTTPS requests from proxied devices.
- SSL decryption enabled by default using a generated CA certificate (for authorized use only).
- Request inspection: headers, body, response, and overview.
- Per-client IP filtering and session separation.
- Tree-style grouping by domain (optional).

### System Proxy

- One-click system proxy setup.
- Automatic proxy cleanup on exit.
- Periodic consistency check for proxy settings.

### HTTPS & Certificates

- Built-in SSL interception with CA certificate.
- Install/export certificate for local or mobile devices.
- Host-based HTTPS decryption rules.

### Breakpoints & Throttling

- Request/response breakpoints with rule-based control.
- Throttling simulation (latency, bandwidth limits).

### Global Scripts

- Script injection at different request lifecycle stages.
- Script logs available in dedicated window.

### UI & Preferences

- Theme switching (light/dark).
- Language support.
- Proxy port auto-restart on change.

### Replay

- Request replay from history with independent window support.

### Collaboration & Extension

- Local network sharing for session data.
- Chrome extension support for capturing and forwarding data.

### Update System

- Built-in update checking (Windows/macOS/Linux supported depending on distribution).

### Startup & Shutdown

- Automatic proxy start sequence.
- Graceful shutdown with proxy cleanup and certificate service stop.
