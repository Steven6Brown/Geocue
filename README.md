<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="branding/geocue-wordmark-on-dark.png">
    <img src="branding/geocue-wordmark-on-light.png" alt="Geocue" width="460">
  </picture>

  <p><strong>Arrive, and your phone adapts.</strong></p>

  <img src="https://img.shields.io/badge/status-In%20design-F2A33A?style=flat-square" alt="status"> <img src="https://img.shields.io/badge/platform-iOS%2017%2B-FF6B1A?style=flat-square" alt="platform"> <img src="https://img.shields.io/badge/license-proprietary-555555?style=flat-square" alt="license"> <img src="https://img.shields.io/badge/by-Aquila%20Digital%20LLC-14213D?style=flat-square" alt="Aquila Digital LLC">
</div>

> **Status: in design.** Geocue is a fully briefed and branded product concept. The plan, scope and open questions are documented; the app has not been built yet.

## The idea

Your phone changes mode based on where you are: at the gym it shows your workout, at the office it quiets social distractions, at home after 9pm it winds down.

- **For:** People who want their phone to fit the place they are in without fiddling with settings.
- **Outcome:** Cross a place boundary and the phone is already set up for it.

## How it will work

```mermaid
flowchart LR
  A["Define a place and a mode"] --> B["CoreLocation region monitoring detects arrival"] --> C["The matching mode is applied or suggested"] --> D["Leave the place and the mode ends"]
```

## Planned features

- Place-based modes (gym, office, home-evening and more)
- Geofence boundaries stored only on the device
- Built around what iOS actually allows: Focus Filters (App Intents), Shortcuts automations, geofence notifications, widgets, Live Activities
- Honest about platform limits: third-party apps cannot silence other apps or switch Focus on their own

## Tech plan

| Layer | Choice |
|---|---|
| Language / UI | Swift, SwiftUI (iOS 17+) |
| Location | CoreLocation region monitoring |
| Integration | App Intents, Focus Filters, Shortcuts |
| Storage | Local, on-device |
| Backend | None |

## Privacy by design

Place boundaries are stored on the device only.

## Open decisions

Tracked openly in [`docs/PROJECT_BRIEF.md`](docs/PROJECT_BRIEF.md). A few of the big ones:

- PLATFORM LIMIT (verify against current Apple documentation before designing): iOS does not let a third-party app silence or block other apps, or switch the system Focus on its own. The mechanisms that appear to be available are Focus Filters (App Intents), user-installed Shortcuts location automations, geofence-triggered local notifications, widgets and Live Activities. Which of these make a worthwhile v1?
- Background region monitoring needs "Always" location access, which App Review scrutinizes. Is the value worth it?
- How many modes and places in v1.
- Pricing model.

## Brand

| | Name | Hex | Role |
|---|---|---|---|
| <img src="https://placehold.co/44x22/FF6B1A/FF6B1A.png" alt="#FF6B1A" /> | Cue Orange | `#FF6B1A` | Icon field, accent, key actions |
| <img src="https://placehold.co/44x22/FFFFFF/FFFFFF.png" alt="#FFFFFF" /> | White | `#FFFFFF` | Pin, light surfaces |
| <img src="https://placehold.co/44x22/1B1F4B/1B1F4B.png" alt="#1B1F4B" /> | Midnight | `#1B1F4B` | Geofence ring, text, dark surfaces |
| <img src="https://placehold.co/44x22/FF9A5C/FF9A5C.png" alt="#FF9A5C" /> | Peach | `#FF9A5C` | Ring and accents on dark |

**Mark.** A location pin with a lightning-bolt cutout over a dashed midnight geofence ring: arrive somewhere, trigger the change.

**Voice.** Quiet, confident, low-drama. Describe what the phone will do, in the present tense, without promising what iOS does not allow.

Full logo set (mark, wordmark, app icon in light and dark) and the brand guide are in [`branding/`](branding/BRAND_GUIDE.md).

## Repository contents

```
docs/PROJECT_BRIEF.md   Confirmed requirements, assumptions, open questions, scope
branding/               Logo files and BRAND_GUIDE.md
```

## License

Proprietary. Shared publicly for portfolio and demonstration purposes only. See [LICENSE](LICENSE).

---

<div align="center">

Built by [Aquila Digital LLC](https://github.com/Steven6Brown) · *Per Aspera Ad Astra*

</div>
