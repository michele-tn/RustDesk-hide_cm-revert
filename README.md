# SYNTRIX automatic update and hide_cm fix

Read [the English overview](index.html) and [the complete field guide](hide-cm-guide-en.html).

Download the complete `SYNTRIX-Auto-Update-Fix.zip` from the latest release. Extract it, review the files, then run:

```powershell
.\Update-Syntrix.ps1 -Plan
.\Update-Syntrix.ps1
```

Python 3.11+ alternative: `python update_syntrix.py`. The PowerShell entry point provisions Python if needed. Windows x64 is required. Build tools are provisioned automatically and may require administrator privileges or a restart. No RustDesk installation, service or tray is updated.

The default selects the newest published upstream release, including prereleases and nightly Windows asset dates. It maps nightly builds to exact CI source commits, applies the public SYNTRIX patch, obtains verified bridge bindings, provisions the toolchain, tests and builds EXE/ZIP packages. A conflict or missing verified dependency stops the build. The public toolkit contains no private profile.

**Both entry points require the companion files. Download the complete ZIP.**

Validation recorded: 9 Python tests, PowerShell syntax checks, and patch preparation for both workspace variants on the 19 November 2026 nightly commit. The complete fresh-machine tool bootstrap and build pipeline is not yet tested end to end. Manual remote-session validation remains unrecorded.

The final application change restores hide_cm for eligible authorized sessions, suppresses automatic CM show/focus from session events, opens the full manager on local tray request and removes the earlier compact session indicator. Authorization requirements remain in force.

Patch baseline: official RustDesk 1.5.3, commit `95cca3f661f635b3cc85c04935fe8d96d8f432ef`. The patch includes full public SYNTRIX branding/customization and the visibility regression test. Based on RustDesk; see LICENCE-RustDesk for the upstream AGPL-3.0 license. The pre-existing repository LICENSE is retained.
