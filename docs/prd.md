# Gladio — Product Requirements Document

**Version:** 0.1 (MVP)  
**Status:** In development  
**Last updated:** May 2026

---

## Problem

WKF karate tournaments run 4–8 simultaneous tatamis. Parents, coaches, and fans inside the venue — or watching from home — have no way to follow their athlete in real time. Paper brackets get lost. Scoreboards face the wrong direction. There is no app.

## Solution

A live tournament management platform that lets organizers run WKF-compliant scoring while giving supporters a real-time spectator view — from any device, no install required.

## Target Users

| Role | Need |
|------|------|
| Tournament organiser | Run brackets, manage fighters, scoreboard control |
| Head referee / Shiro | Score entry, penalty cycle, time control |
| Coach | Follow their fighters across tatamis |
| Parent / spectator | Live score tracking, bracket position, next match alert |

## Primary Buyer

National karate federations. Starting Belgium (WKBF / VKF / FBKC), scaling to Western Europe.

---

## Phase 1 — MVP (current)

Single HTML file, zero dependencies.

### Functional requirements

- Tournament setup: name, categories, duration, fighter import (CSV or manual)
- Single-elimination bracket: auto-sized to next power of 2, byes distributed
- WKF scoring: Yuko (1), Waza-ari (2), Ippon (3), Senshu, Kansa (8-pt lead)
- Penalty cycle: W → W2 → HC → HC2 → H (each +1pt to opponent)
- Victory conditions: score lead, Kansa, Hansoku, Senshu tiebreak
- WKF repechage: traces full finalist path, runs per-group mini bracket
- Spectator view: read-only, QR code, BroadcastChannel cross-tab sync
- Reporting: standings, match stats, club rankings, CSV export

### Non-functional requirements

- Works offline (localStorage persistence)
- Mobile-first responsive layout
- No build step, no server required for local use

---

## Phase 2 — Cross-device sync

- Supabase Realtime replaces BroadcastChannel
- Multi-device: scoring table laptop + spectator phone = same live state
- Offline resilience: Zustand persist + retry queue

## Phase 3 — Auth & roles

- Organiser PIN lock
- Referee mode (score entry only)
- Spectator URL (public read-only, shareable)
- Multi-tatami organiser dashboard

## Phase 4 — Registration & reporting

- Form-based fighter registration
- Club management
- Print-ready PDF report (branded Gladio layout)
- Advanced stats: points for/against, W-L distribution, match duration

## Phase 5 — Native / PWA

- PWA manifest: home screen install, offline-first
- Push notifications for next-match alerts
- No app store required

---

## Out of scope (v1)

- Kata scoring
- Team Kumite
- Age/weight category enforcement
- Payment / entry fees
- Video replay
