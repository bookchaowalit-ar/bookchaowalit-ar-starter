# Upgrade plan

## Current state

**Score: 3/10** (was 2/10) for a starter: owner-model README, MIT license
and a CI contract that now checks something meaningful. No AR/MR code yet,
by design.

## Backlog

### P0 (only once an AR/MR product is approved)
- Pick the stack and record the decision here. Candidates, in order of
  fit with the rest of the portfolio (TypeScript/Next.js on the web):
  1. **WebXR** (TypeScript + three.js or Babylon.js, Vite): runs in
     browsers on Quest and Android; shares tooling with other web repos.
  2. **Unity + AR Foundation**: best device coverage (ARKit/ARCore/Quest),
     but adds a C#/Unity toolchain the portfolio does not use elsewhere.
  3. **Native** (ARKit/RealityKit or ARCore): only for a single-platform
     product.
- Add the scaffold, stack-specific `.gitignore` entries, and CI that runs
  that stack's lint/test/build. Change README **Status** from `starter` so
  `scripts/check-starter.sh` stops treating code as out of place.

### P1
- Shared conventions doc: coordinate units (metres), anchor persistence,
  camera-permission copy, privacy note (no camera frames leave the device
  unless the product says so).
- Accessibility baseline for XR: seated mode, comfort vignette, text size.

### P2
- Template for device test notes (headset/phone model, OS, result).

## Done in this pass (2026-09-30)
- Replaced the "files exist" CI check with `scripts/check-starter.sh`
  (README sections, MIT license, link check, tracked-secret guard, honest
  Status). Verified locally, including negative cases.
- Added `.gitignore` (secrets, OS/editor, common build output) and
  `.editorconfig`.
- CI now also runs on pull requests to any branch and on demand.
