# Project Sentinel (v3.7.2 Production Release)

**Autonomous Multi-Tier Emergency Rescue & Dispatch Infrastructure**  
Engineered by **Alisto Network PH** · Philippine Civic & Institutional Safety Grid

---

## 1. Platform Overview

**Project Sentinel** is a high-availability, low-latency emergency dispatch and perimeter containment platform engineered for Philippine Local Government Units (LGUs), Command Operations Centers (PNP, BFP, EMS, MDRRMO, Barangay), and partnered residential, commercial, and academic institutions.

All field and station binaries communicate over encrypted **TLS 1.3 Port 443** transport channels to bypass carrier-grade NAT (CGNAT) restrictions on mobile and broadband networks nationwide.

---

## 2. Three-Tier Operational Architecture

| Tier | Deployment Node | Binary Package | Core Capabilities |
| :--- | :--- | :--- | :--- |
| **Tier 1** | **Citizen & Tenant BYOD Mobile App** | `sentinel-tier1-byod.apk` *(Android 8.0+ / API 26+)* | • Native Kotlin architecture with **Jetpack CameraX** & **8,000 Hz 16-bit PCM `AudioRecord`** telemetry.<br>• **Silent Coercion / Duress Mode:** Drops physical screen backlight to `1%` (`#000000` curtain) while streaming live video, audio, and GPS coordinates.<br>• **30-Second Autonomous Fail-Safe:** Automatically escalates unacknowledged property alarms directly to Tier 3 municipal stations.<br>• **Out-of-Zone Fallback:** Automatic municipal AOR geofence verification with instant National 911 dialer handoff. |
| **Tier 2** | **Guardhouse Gatekeeper Kiosk** | `sentinel-tier2-kiosk.apk` *(Android Tablet / Handheld)* | • Native Kotlin receiver for subdivision guardhouses, commercial complexes, and school security desks.<br>• **Hardware Klaxon & Live Stream Triage:** Immediate `STREAM_ALARM` siren with live Port 443 video and `AudioTrack` voice verification.<br>• **Gatekeeper Controls:** `+60s Investigation Hold`, `Immediate Tier 3 Escalation`, and `False Alarm Stand-Down`.<br>• **Perimeter Containment Broadcasts:** One-tap `LOCKDOWN`, `EVACUATE`, and `ALL CLEAR` alerts pushed to all registered Tier 1 devices within the property. |
| **Tier 3** | **Station Command & Master Admin Suite** | `sentinel-tier3-setup.exe` *(Windows 10 / 11 64-bit)* | • Native 64-bit Windows workstation suite (`SentinelDispatch.exe` & `SentinelAdmin.exe`) with NSIS desktop installer.<br>• **Multi-Agency Command:** Real-time GPS tracking, exact room/floor/building telemetry, and cross-agency co-dispatch (PNP, BFP, EMS, Barangay).<br>• **Local Shift Evidence Recording:** Automatic local hard drive recording (`.webm` VP8/Opus) stored in `Documents\Sentinel_Shift_Recordings` for post-incident review. |

---

## 3. Security, Hardening & Regulatory Compliance

* **Compiled & Obfuscated Release Binaries:** Android packages are compiled with **R8 bytecode minification** and runtime **XOR byte-array credential masking**. Windows executables are compiled with stripped symbol tables (`-O3 -s`) and engine-level DevTools restrictions.
* **Role-Isolated Authentication Gateway:** Dedicated operator authentication (`login.html`) with synchronous session guards and server-side PostgreSQL `SECURITY DEFINER` verification.
* **RA 10173 (Data Privacy Act of 2012) Alignment:** Location and audiovisual streams are transmitted strictly during active, user-initiated SOS or Duress events.
* **COA Audit Trail Integrity:** Every alarm trigger, guardhouse hold, escalation, and station dispatch action is recorded in an append-only audit log with immutable timestamps and operator callsigns.

---

## 4. Official Binary Distribution

Production installers are served directly via the **Project Sentinel Public Deployment Portal**:

1. **Tier 1 Citizen Mobile Client:** `sentinel-tier1-byod.apk` *(v3.7.2-hardened)*
2. **Tier 2 Guardhouse Gatekeeper Kiosk:** `sentinel-tier2-kiosk.apk` *(v3.7.2-hardened)*
3. **Tier 3 Windows Command Workstation Installer:** `sentinel-tier3-setup.exe` *(v3.7.2 x64 Setup Wizard)*

---

## 5. Institutional Deployment & Technical Inquiries

For LGU pilot demonstrations, municipal station provisioning, or institutional onboarding:

* **Engineering & Provisioning Team:** Alisto Network PH
* **Official Contact:** `dev.projectsentinel@gmail.com`

---
*Copyright © 2026 Alisto Network PH. All rights reserved. Unauthorized reverse engineering, redistribution, or tampering with operational command nodes is strictly prohibited.*
