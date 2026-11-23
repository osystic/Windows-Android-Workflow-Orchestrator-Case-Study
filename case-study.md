# Windows & Android Workflow Orchestrator — Engineering Case Study

**OSYSTIC · Completed engineering delivery · Anonymized public showcase**

## Challenge

Stateful Android workflows require more than a sequence of UI actions. Imports can misalign records, emulators can be unavailable, controls can change, a private operator action may be required, and uncertain external submissions must not be automatically repeated.

The objective was an understandable Windows desktop control plane with deterministic input handling, bounded operation, and trustworthy error visibility.

## Solution

**All-or-nothing onboarding.** A five-column keyed text import validates every row before creating or matching Pending tasks. Duplicate, malformed and conflicting input is rejected without partial import. Legacy input formats remain available.

**Explicit task ownership.** Imported records are not automatically selected for execution. An operator chooses each authorized task and the corresponding supported emulator.

**Accessible UI state inspection.** Android accessibility snapshots guide supported transitions. Unknown screens or ambiguous controls trigger a manual checkpoint or safe stop, not a speculative tap.

**Durable one-shot protection.** An attempt ledger records irreversible actions before they are sent, guarding against accidental replay when an external result is unknown.

**Sensitive data boundaries.** Personal fields are held only in active-session memory while queue metadata persists separately. Password and verification stages were operator controlled in the approved engineering baseline.

## Evidence

| Layer | Verified result |
| --- | --- |
| Windows Release regression | 752/752 passing |
| Focused data import/per-record suite | 40/40 passing |
| Windows WPF synthetic single-file import | Both import controls PASS |
| Explicit Run selection default | No automatic selection |
| Encrypted delivery package | 275/275 decrypted entries checked |
| Frozen source baseline | 276/276 file hashes matched |

The engineering baseline was client-approved. Successful third-party service registration or verification-code arrival was **not independently validated** in the cited evidence. No performance, uptime or throughput figures are invented.

## Lessons

- Validate user input before persistent mutation.
- Match by stable identifier rather than record position.
- Separate import from authorization.
- Prefer explicit UI readback and manual checkpoints over optimistic navigation.
- Record possible irreversible attempts before issuing them.
- Freeze signed-off baselines and build future work as distinct versions.
- Do not conflate unit tests with external-provider acceptance.

## Disclosure policy

Client name, historic internal project branding, source code, account identifiers, sensitive screenshots, credentials, executable archives, contract terms and private communications are intentionally excluded.

© OSYSTIC. All rights reserved.
