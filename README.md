# OSTF Composer for Max for Live

**OSTF Composer** is a Max for Live songwriting, harmony, voicing, and MIDI workflow tool built around the **Open Song Timeline Format (OSTF)**.

It is designed for composers, songwriters, arrangers, and producers who want to build song structures, create chord progressions, generate playable voicings, capture MIDI from Ableton Live, reconstruct song sections, and move structured musical ideas between OSTF and Live.

OSTF Composer combines:

- Song structure editing
- Whole-song chord composition
- Section-level harmony generation
- Voicing generation and editing
- MIDI capture from Ableton Live
- Section reconstruction
- MIDI output back to Live
- OSTF 3.x / 4.x compatibility
- Non-destructive OSTF data preservation

Version **1.1** focuses on OSTF 4 compatibility, a more structured Voicing Studio workflow, improved Live output placement, and stability.

---

# Features

## OSTF-based songwriting workflow

Create and edit structured songs using OSTF.

You can:

- Create and rename song sections
- Build structures such as Intro, Verse, Pre-Chorus, Chorus, Bridge, Final Chorus, Outro, and custom sections
- Change section lengths
- Edit chord timelines
- Reorder song sections
- Duplicate and delete sections
- Preserve surrounding OSTF song data while editing
- Work with song-level key, tempo, meter, genre, and metadata
- Save edited songs back to OSTF

OSTF Composer is intended to edit the musical information it understands while preserving unrelated OSTF information wherever possible.

---

# Whole-Song Chord Composition

Use **Compose song** to generate chord progression ideas across the complete arrangement.

Generation can take into account musical context such as:

- Genre
- Mood
- Harmonic color
- Harmonic depth
- Section roles
- Local key maps
- Neighboring sections
- Pattern focus
- Variation level
- Harmonic continuity

Multiple progression ideas can be generated and compared before committing changes.

Progressions can be auditioned before they are applied.

The whole-song workflow is designed to consider the relationship between sections rather than treating every section as an isolated four-chord loop.

---

# Section Composer

Section Composer provides more detailed harmonic development for individual song sections.

Available approaches include:

- Automatic progression suggestions
- Harmonic function
- Emotional direction
- Bass movement
- Cadence ideas
- Harmonic color
- Variation
- Modulation
- Reverse analysis

Generated ideas can be auditioned before being committed.

This makes it possible to establish the overall structure with Whole-Song Composition and then refine individual sections where necessary.

---

# Voicing Studio

Voicing Studio generates and edits playable chord voicings based on the current OSTF chord progression.

Version 1.1 reorganizes Voicing Studio so that major tasks, secondary controls, and output operations are more clearly separated.

Main capabilities include:

- Whole-song voicing generation
- Candidate generation
- Candidate audition
- Original / Candidate comparison
- Per-section adoption
- Left-hand / right-hand arrangement
- Bass control
- Top-note control
- Tension handling
- Voice-leading control
- Guide-tone prioritization
- Fifth omission when necessary
- Avoid-note warnings
- Melody clearance
- Register control
- Manual piano-roll editing
- Commit / discard workflow

Related pitch controls are grouped together instead of being treated as unrelated top-level modes.

MIDI Capture remains a separate workflow and is not mixed automatically into generated voicings.

---

# Voicing comparison workflow

Whole-song voicing ideas can be generated without immediately replacing the current arrangement.

A typical workflow is:

1. Generate voicing candidates.
2. Audition the original version.
3. Audition a candidate.
4. Compare the musical result.
5. Choose which sections should adopt the candidate.
6. Commit the selected result.
7. Undo if necessary.

This allows voicing generation to remain exploratory until the user explicitly commits the result.

---

# Piano-roll editing

The built-in piano roll allows detailed editing of generated and committed voicings.

You can:

- Select notes
- Move notes
- Add notes
- Delete notes
- Edit chord tones
- Audition changes
- Commit chord changes
- Work with individual sections
- Work with the whole song

Notes are visually differentiated by harmonic function so that roots, thirds, fifths, sevenths, tensions, and other chord roles are easier to identify.

When chord information changes, harmonic interpretation can be updated accordingly.

---

# MIDI Capture from Ableton Live

OSTF Composer can capture MIDI from a selected Ableton Live MIDI clip.

The original Live clip remains read-only.

The Capture workflow can:

- Read MIDI from Live
- Display captured MIDI
- Analyze detected chords
- Select ranges from the captured material
- Assign ranges to OSTF sections
- Create new sections
- Extend existing sections
- Insert sections before or after existing sections
- Reconstruct an OSTF song structure from existing MIDI

Captured MIDI is intentionally kept separate from Voicing Studio data.

Version 1.1 retains the established MIDI Capture workflow without major structural changes.

---

# Section reconstruction

Captured MIDI can be progressively assigned to OSTF song sections.

Typical workflow:

1. Select or open a MIDI clip in Ableton Live.
2. Open the MIDI Capture workspace.
3. Capture the MIDI.
4. Select a range in the Capture Timeline.
5. Assign the range to an existing OSTF section or create a new one.
6. Repeat for additional ranges.
7. Review the reconstructed structure.
8. Commit the assignments.

This makes it possible to take an existing MIDI chord progression and reconstruct its structural representation inside OSTF.

---

# Capture overlay

Captured source MIDI and generated Voicing Studio notes are kept separate by default.

Captured MIDI is **not automatically mixed into the Voicing Studio piano roll**.

A Capture overlay can be enabled when comparison is useful.

This avoids confusion between:

- Captured source material
- Generated candidates
- Committed voicings

---

# Send MIDI to Ableton Live

Voicing Studio can send generated and edited MIDI directly back to Ableton Live.

Two output approaches are supported.

## Append to a selected MIDI clip

When an existing compatible MIDI clip is selected, OSTF Composer can add the generated notes to that clip.

Existing notes are preserved.

This is an **append operation**, not a destructive replacement operation.

The insertion point can be specified by clip bar so that generated material can be added at a defined location inside the selected clip.

For example:

- Clip bar 1
- Clip bar 5
- Clip bar 17

Existing notes are not automatically deleted.

Safety checks prevent obviously conflicting or invalid writes where possible.

## Create a new MIDI clip

OSTF Composer can also create a new MIDI clip on a selected Live MIDI track.

Options include:

- Destination MIDI track
- Output scope
- Arrangement placement
- Clip splitting behavior
- Start position
- Specific Live bar

For Arrangement output, a specific Live bar can be entered.

For example:

**Live start bar: 37**

will place the new output beginning at bar 37 in the Arrangement.

OSTF Composer attempts to avoid silently overwriting existing Arrangement clips.

If the intended range conflicts with an existing clip, the write can be blocked instead of replacing existing material.

---

# Output scope

Depending on the current editing context, MIDI output can target different ranges, including:

- Whole song
- Current section
- Selected chord range

Output information is shown before writing where possible.

---

# MIDI file export

OSTF Composer v1.1 does **not** include direct Standard MIDI File export.

An experimental MIDI export implementation was evaluated during development but was removed before the v1.1 release because it did not meet the required stability standard.

For reliable MIDI file export:

1. Send the MIDI to Ableton Live.
2. Use Ableton Live's standard MIDI clip export workflow.

This keeps file export outside OSTF Composer's Live API and Max file-writing path.

---

# Transposition

OSTF Composer includes transposition tools designed to preserve OSTF structure.

Depending on the source data, transposition can update:

- Chord symbols
- Voicings
- Performance notes
- Key-related information

Data that should not follow harmonic transposition can remain unchanged.

When a transformation cannot be performed safely, OSTF Composer prefers to stop or preserve the original information rather than silently damage the song.

---

# Undo and Redo

Editing operations support Undo and Redo where possible.

This includes operations such as:

- Chord changes
- Voicing changes
- Song structure operations
- Candidate commits
- Other Composer editing actions

Undo behavior is intentionally tied to committed editing operations rather than temporary audition states.

---

# OSTF compatibility

OSTF Composer v1.1 supports the OSTF 3.x family and OSTF 4.x compatibility workflow.

The device can work with older OSTF song structures while also recognizing OSTF 4 data.

OSTF 4 introduces additional musical performance information such as:

- Control Change data
- Program Change
- Pitch Bend
- Channel Pressure
- Polyphonic Pressure
- MIDI channel information
- MIDI bus information
- Multiple melody tracks
- Multiple lyric voices

OSTF Composer is primarily a chord, structure, voicing, and composition editor.

It therefore does **not** attempt to reinterpret or regenerate every OSTF 4 performance field.

Instead, OSTF 4 information that Composer does not directly edit is preserved whenever possible.

Important principles include:

- Do not silently discard unknown OSTF data
- Preserve unrelated song information
- Preserve MIDI performance information that Composer does not edit
- Preserve lyrics and additional voices where possible
- Preserve external track information
- Avoid destructive timeline transformations
- Stop saving if protected OSTF 4 information changes unexpectedly
- Do not downgrade OSTF 4 songs to OSTF 3.x during normal editing
- Allow compatible future OSTF 4.x files when the inherited core structure remains understandable

OSTF Composer favors preservation over aggressive conversion.

---

# Non-destructive design

OSTF Composer is designed to avoid silently changing information that the current operation does not need to modify.

Examples include:

- Captured Live MIDI is never edited in place
- Capture source MIDI remains separate from generated voicings
- Existing Live notes are preserved during append operations
- New Arrangement clips are not intended to silently overwrite existing clips
- Unrelated OSTF data is preserved where possible
- Unsupported OSTF data is not automatically discarded
- Protected OSTF 4 performance information is checked during save operations
- Unsafe transformations can be blocked rather than applied

Always keep backups of important project and OSTF files.

---

# Typical workflow

A common OSTF Composer workflow is:

1. Create or open an OSTF song.
2. Build or refine the song structure.
3. Generate whole-song chord progression ideas.
4. Audition and select a progression.
5. Refine individual sections with Section Composer.
6. Generate whole-song voicing candidates.
7. Compare Original and Candidate versions.
8. Adopt the desired sections.
9. Edit voicings in the piano roll if necessary.
10. Commit the result.
11. Send MIDI to Ableton Live.
12. Continue arranging or editing in Live.
13. Capture edited MIDI back into Composer if structural reconstruction is needed.
14. Save the updated OSTF file.

This allows OSTF Composer to act as a bridge between structured composition and practical DAW production.

---

# Installation

1. Download:

   `OSTF_Composer_v1.1.amxd`

2. Place the device in your Max for Live device folder or another location accessible from Ableton Live.

3. Drag OSTF Composer onto a MIDI track.

4. Click **Open** in the device view.

5. The OSTF Composer editor window will open.

---

# Basic usage

## Start a new song

Click **New**.

Create the song structure manually or use the available structure tools.

Typical sections include:

- Intro
- Verse
- Pre-Chorus
- Chorus
- Bridge
- Final Chorus
- Outro

Custom sections can also be created.

---

## Open an OSTF song

Click **Open** and select an OSTF file.

Supported OSTF song information is loaded into Composer while unrelated compatible information is preserved where possible.

OSTF files can also be opened using the supported drag-and-drop workflow where available.

---

## Generate chord progressions

Click **Compose song**.

Configure the desired generation settings such as:

- Genre
- Mood
- Harmonic color
- Pattern focus
- Variation

Generate several ideas.

Audition the candidates and apply the progression you prefer.

---

## Generate voicings

Open **Voicing Studio**.

Configure accompaniment and voice-leading options.

Generate whole-song voicing candidates.

Compare:

- Original
- Candidate

Choose the sections that should adopt the candidate, then commit the result.

---

## Edit voicings

Use the Voicing Studio piano roll to:

- Select notes
- Move notes
- Add or remove notes
- Inspect harmonic roles
- Audition changes
- Commit the edited result

---

## Capture MIDI

1. Open or select the source MIDI clip in Ableton Live.
2. Open the Capture workspace.
3. Capture the MIDI.
4. Select a range in the Capture Timeline.
5. Assign the range to an OSTF section.
6. Repeat as necessary.
7. Commit the reconstructed structure.

The original Live MIDI remains unchanged.

---

## Send MIDI to Live

Open the **Output** section in Voicing Studio and click **Send to Live**.

### Existing selected MIDI clip

Use the selected-clip option to append notes to an existing MIDI clip.

Choose the clip bar where the new material should begin.

Existing notes are preserved.

### New MIDI clip

Choose **Create a new MIDI clip**.

Configure:

- MIDI track
- Scope
- Destination
- Clip split
- Start position

For Arrangement output, choose **Specific Live bar** when you want exact placement.

Enter the desired Live bar and click **Write to Live**.

---

# Version history

## v1.1

Current release.

Main changes:

- OSTF 4.x compatibility
- Preservation of OSTF 4 performance and multi-voice information not directly edited by Composer
- Improved future OSTF 4.x compatibility handling
- Voicing Studio UI restructuring
- Clearer separation between primary modes and secondary voicing controls
- Improved Candidate / Audition / Commit workflow
- Consolidated Send to Live workflow
- Existing selected MIDI clip append workflow
- Specific clip-bar placement for append operations
- Specific Live-bar placement for new Arrangement clips
- Improved protection against accidental clip replacement
- Internal `__unset__` values hidden from user-facing inherited-value displays
- Continued MIDI Capture workflow stability
- Direct experimental MIDI file export removed for release stability
- General stability and UI cleanup

---

## v1.0

Initial public release.

Main features:

- OSTF-based song editing
- Whole-song chord composition
- Section Composer
- Voicing Studio
- Piano-roll voicing editing
- MIDI Capture from Ableton Live
- Section reconstruction from captured MIDI
- MIDI output back to Live
- Transposition support
- Undo / Redo
- Non-destructive editing safeguards

---

# Known considerations

OSTF Composer combines song editing, MIDI capture, Live API communication, harmony generation, voicing generation, and OSTF state management in a single Max for Live device.

If you encounter a repeatable problem, please include:

- OSTF Composer version
- Ableton Live version
- Max version
- Operating system
- Steps required to reproduce the issue
- OSTF file if relevant
- Screenshot of the problem
- Max Console output if available

Clear reproduction steps make issues significantly easier to diagnose and fix.

---

# Requirements

- Ableton Live
- Max for Live
- Windows or macOS environment supported by your Ableton Live / Max installation
- MIDI track and MIDI instrument when auditioning through Live

---

# Open Song Timeline Format

OSTF Composer is part of the **Open Song Timeline Format** ecosystem.

OSTF is intended to provide a structured representation of songs that can include information such as:

- Song structure
- Sections
- Chord progressions
- Melodies
- Lyrics
- Arrangement information
- MIDI performance data
- Musical metadata

See the OSTF project repositories for format specifications and examples.

---

# License

No license is currently bundled with this repository unless one is added separately.

Before reusing, redistributing, or modifying the project, check the repository license status.

---

# Support the project

If OSTF Composer or the wider OSTF ecosystem is useful to you, you can support continued development here:

**Buy Me a Coffee**

https://buymeacoffee.com/yohsukenak

Support helps continued development, testing, documentation, compatibility work, and maintenance of the OSTF ecosystem.

---

# Links

## OSTF Composer

https://github.com/yoh-nak/OSTF-Composer-M4L

## Open Song Timeline Format

https://github.com/yoh-nak/

## Buy Me a Coffee

https://buymeacoffee.com/yohsukenak

---

# Author

Developed by **yoh-nak**.

OSTF Composer is part of the broader Open Song Timeline Format ecosystem for structured songwriting, composition, arrangement, MIDI workflows, and DAW interoperability.
