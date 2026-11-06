# Geocue — Project Brief

Use together with the *Aquila Digital — Mobile & Web App Build Standards*. This brief is the product source of truth; anything not listed under Confirmed is not decided.

## 1. Project overview
Geocue is an application for Aquila Digital LLC. Your phone changes mode based on where you are: at the gym it shows your workout, at the office it quiets social distractions, at home after 9pm it winds down.

- **Platform scope:** iOS (assumed: see below).
- **Primary users:** People who want their phone to fit the place they are in without fiddling with settings.
- **Primary user outcome:** Cross a place boundary and the phone is already set up for it.

## 2. Confirmed requirements
- Standalone app. Working title during brainstorm: "Quiet Hours"; renamed Geocue because "Quiet Hours" is already an App Store title.
- Core idea: place-based modes (gym, office, home-evening are the examples given).

## 3. Reasonable assumptions (change freely)
- iOS first, SwiftUI, iOS 17+.
- Place boundaries use CoreLocation region monitoring and are stored on the device only.

## 4. Open questions (decide before building the affected part)
- PLATFORM LIMIT (verify against current Apple documentation before designing): iOS does not let a third-party app silence or block other apps, or switch the system Focus on its own. The mechanisms that appear to be available are Focus Filters (App Intents), user-installed Shortcuts location automations, geofence-triggered local notifications, widgets and Live Activities. Which of these make a worthwhile v1?
- Background region monitoring needs "Always" location access, which App Review scrutinizes. Is the value worth it?
- How many modes and places in v1.
- Pricing model.

## 5. Out of scope
- Any claim or implication that the app blocks or force-silences other apps.
- Location sharing with other people.
- Android.

## 6. Project context
| Item | Value |
|---|---|
| Project type | Mobile app |
| Platform | Swift / SwiftUI, iPhone (assumed) |
| Backend | NONE |
| Database | LOCAL |
| Authentication | NONE |
| Hosting / deployment | App Store |
| Analytics | NONE |
| AI / ML | NONE |
| Sensitive data classes | LOCATION (saved place boundaries, sensitive: home and work). |
| Data processing location | ON-DEVICE |

## Notes
- Do not retain location history. Store only the boundaries the user creates.

## 7. Documents to keep (per the build standards)
README.md · SECURITY.md · ARCHITECTURE.md · PRIVACY.md · TESTING.md · CHANGELOG.md · .env.example (names only)
