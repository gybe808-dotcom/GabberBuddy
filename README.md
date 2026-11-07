# GabberBuddy for the M-VAVE FM-1

GabberBuddy is a free, non-commercial **hack of [X0X](https://github.com/charlesvestal/fm1-x0x)**, the groovebox
firmware for the M-VAVE FM-1, aimed at experimental noise and gabber. It is early: it has run in a simulator and in
CI builds, and has not had much time on a real FM-1. Installing it is at your own risk.

## What GabberBuddy adds

- **gabber909**: the 909 KIT page has a **Style** knob: `909` (the original sound, untouched), `GAB-S` (saturated kick,
  snare, clap and hats, and the 303s driven hard) and `GAB-F` (the same with a wavefolded kick and snare and the 303s
  through the RAT fuzz).
- **Master section** (on the FX bus): a hard-clip distortion type, an independent bit crusher (**Bits** and **Rate**),
  and a 3-band **EQ** (Bass, Mid, High).
- **303 SUPER**: a detuned super-saw (3, 5 or 7 saws) on the Saw wave.
- **303 NOISE**: an 8-bit noise oscillator (Long, Short and Chaos shift registers) with a clock that follows the note.
- **NEON** theme: black screen, neon green, with seven-segment digits (the default).

Everything else is X0X. Its original README is [README.X0X.md](README.X0X.md), and its manual is in `docs/`.

## Install

**Web installer: <https://gybe808-dotcom.github.io/GabberBuddy/install/>**

1. Open the installer in **Chrome or Edge** (it needs Web MIDI, so not Firefox or Safari).
2. Connect the FM-1 with a **USB data cable** (a charge-only cable won't work) and switch it on.
3. Press **Install** and allow the MIDI permission when the browser asks.
4. **Don't unplug it** while it writes. When it finishes, the FM-1 restarts into GabberBuddy.

Things to know first:

- Installing replaces whatever firmware is on the FM-1, and a different firmware doesn't keep your patterns and sounds.
  Back up anything you care about first.
- To go back to M-VAVE's own firmware, use **Back to the stock firmware** at the bottom of the same installer page.
- If an FM-1 running GabberBuddy keeps crashing, it starts in a safe mode where the installer can put a working firmware back.
  The manual's Troubleshooting section covers the rest, and Felucca's
  [FM-1-transporter](https://github.com/kurogedelic/FM-1-transporter) (a small RP2040 board) is the last resort.
- Installing firmware is at your own risk.

Also on the site: the **[emulator](https://gybe808-dotcom.github.io/GabberBuddy/emu/)** (hear it in your browser, no FM-1
needed) and the **[manual](https://gybe808-dotcom.github.io/GabberBuddy/manual/)**.

Command-line install (for people who prefer it): get `gabberbuddy-0.0.1-beta.fwsc` from the site's firmware folder, run
`pip install mido python-rtmidi`, then `python tools/fm1_install.py gabberbuddy-0.0.1-beta.fwsc`.

## Credits

GabberBuddy stands on other people's work. Please go and look at theirs:

- **[X0X](https://github.com/charlesvestal/fm1-x0x)** by **Charles Vestal**: the groovebox firmware this is a hack of
  (the sequencer, the user interface, the five parts, the manual, the emulator and the installer pages).
- **[Felucca](https://github.com/hugelton/Felucca)** by **Leo Kuroshita (@kurogedelic), Hügelton Instruments**: the platform
  X0X is a fork of (hardware layer, USB, update loader, web installer and storage).
- **[9W9](https://github.com/athousanddetails/schwung-9W9)** by athousanddetails, after
  **[ER-99](https://github.com/matthewcieplak/er-99)** by Matthew Cieplak: the 909 and its hat and cymbal samples.
- **[8W8](https://github.com/athousanddetails/schwung-8W8)** by athousanddetails: the 808.
- **[schwung-303](https://github.com/charlesvestal/schwung-303)**, built on **Open303** by Robin Schmidt (MIT), with
  Devilfish extensions after jc303 (midilab) and the RAT drive after dm-Rat (Dave Mollen): the 303.
- **[schwung-tb3po](https://github.com/charlesvestal/schwung-tb3po)**, a port of the Phazerville Hemisphere Suite `TB_3PO`
  applet (djphazer and contributors): the 303 line generator.
- **[BB Gen](https://github.com/mestela/schwung-breakbeat)** by mestela, used with the author's permission: the break generator.
- **Melodee** (keremimo), **Jangada** (zednaked) and **Optimist** (henri / hdavid): the second core and speed-ups.
- **luchak**: the reverb. **Groove OS** (Peter Gombos): the idea of an in-browser emulator.
- Fonts: Barlow Semi Condensed (The Barlow Project Authors) and Terminus (Dimitar Toshkov Zhekov), SIL OFL 1.1.

The full table, with licences, is in [LICENSING.md](LICENSING.md).

## Licence

GPL-3.0-only, as X0X and Felucca. If you share a build, you must share its source under the same licence. This is a free
hack and is not for sale.

M-VAVE and FM-1 are trademarks of their owners. TR-808, TR-909 and TB-303 are trademarks of Roland Corporation, used
only to describe what the parts emulate. GabberBuddy is independent: it is not affiliated with, endorsed by or
supported by M-VAVE, Roland, Hügelton Instruments or the X0X project.
