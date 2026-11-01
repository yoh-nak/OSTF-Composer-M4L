# OSTF Composer for Max for Live

OSTF Composer is a Max for Live songwriting and arrangement tool built around the Open Song Timeline Format (OSTF).

It is designed for composers, songwriters, arrangers, and producers who want to create chord progressions, generate voicings, capture MIDI from Ableton Live, reconstruct song sections, and move musical ideas between OSTF and Live.

The device combines song structure, harmony generation, voicing tools, MIDI capture, and Live clip output in a single workflow.

## Features

### OSTF-based songwriting workflow

- Create and edit song sections
- Build song structures such as Intro, Verse, Pre-Chorus, Chorus, Bridge, Final Chorus, Outro, and custom sections
- Edit section lengths and chord timelines
- Preserve OSTF song structure while editing
- Work with OSTF 3.5 metadata and song information

### Whole-song chord composition

Use **Compose Whole Song** to generate chord progression ideas for the entire arrangement.

Generation can take into account:

- Genre
- Mood
- Harmonic color
- Harmonic depth
- Section roles
- Local key maps
- Neighboring progressions
- Pattern focus
- Variation level

Multiple progression ideas can be generated and compared before applying them.

Each progression idea can be auditioned directly before committing changes.

The progression cards show the harmonic shape of the song section by section, making it easier to compare ideas visually.

### Section Composer

Generate and develop chord progressions for individual sections.

Section Composer provides multiple approaches for exploring harmony, including:

- Automatic suggestions
- Harmonic function
- Emotional direction
- Bass movement
- Cadence ideas
- Harmonic color
- Variation
- Modulation
- Reverse analysis

Generated ideas can be auditioned before being applied.

### Voicing Studio

Generate and edit playable chord voicings based on the current chord progression.

Features include:

- Whole-song voicing generation
- Left-hand / right-hand arrangement
- Bass rules
- Voice-leading control
- Top-note movement
- Tension handling
- Guide-tone prioritization
- Fifth omission when needed
- Avoid-note warnings
- Melody clearance
- Candidate comparison
- Audition before commit
- Per-section adoption

The piano-roll editor displays harmonic roles using different colors so roots, thirds, fifths, sevenths, tensions, and other notes can be distinguished visually.

### Piano-roll editing

The built-in piano roll allows detailed editing of generated voicings.

You can:

- Select notes
- Move notes
- Add notes
- Delete notes
- Edit chord tones
- Commit chord changes
- Audition edited chords
- Lock chord structures
- Work with individual sections or the whole song

### MIDI Capture from Ableton Live

OSTF Composer can capture MIDI directly from a selected Ableton Live MIDI clip.

Captured MIDI is analyzed without modifying the original Live clip.

The Capture workspace allows you to:

- Read MIDI from Live
- Analyze detected chords
- Select ranges directly on the piano roll
- Assign selected ranges to OSTF sections
- Create new sections
- Extend existing sections
- Insert sections before or after another section
- Reconstruct an OSTF song from existing MIDI material

The source MIDI remains read-only.

### Section reconstruction

Captured MIDI ranges can be assigned progressively to song sections.

This makes it possible to take an existing MIDI progression from Live and reconstruct its song structure inside OSTF.

Typical workflow:

1. Select a MIDI clip in Ableton Live.
2. Capture the MIDI.
3. Select a range in the Capture Timeline.
4. Assign it to an existing OSTF section or create a new section.
5. Repeat for the remaining parts of the song.
6. Commit the assignments.

### Send MIDI back to Ableton Live

Generated and edited MIDI can be written back to Ableton Live.

OSTF Composer supports:

- Writing to an existing selected MIDI clip
- Creating a new MIDI clip
- Choosing the destination MIDI track
- Whole-song output
- Selected-range output
- Arrangement placement
- Clip splitting options
- Output review before writing

The device verifies Live output where possible before reporting success.

### Capture overlay

Captured MIDI and generated voicings are intentionally separated.

Captured MIDI is not automatically mixed into the Voicing Studio piano roll.

If needed, the Capture overlay can be enabled manually for comparison.

This prevents captured source notes from being mistaken for generated or committed voicing notes.

### Transposition

OSTF Composer includes transposition tools designed to preserve OSTF structure.

Depending on the source data, transposition can update:

- Chord symbols
- Voicings
- Performance notes
- Key-related information

OSTF 3.5 `fixedTrigger` notes and drum-oriented trigger data are not transposed.

When data cannot be safely transformed, OSTF Composer prefers to stop rather than silently damage the song.

### Undo and Redo

Editing operations are designed to support Undo and Redo where possible.

This includes chord edits, voicing changes, song operations, and other editing actions.

## Typical workflow

A common OSTF Composer workflow is:

1. Create a song structure.
2. Generate whole-song chord progression ideas.
3. Audition and select a progression.
4. Refine individual sections with Section Composer.
5. Generate whole-song voicings.
6. Edit voicings in the piano roll.
7. Send MIDI to Ableton Live.
8. Continue editing in Live.
9. Capture edited MIDI back into OSTF Composer if needed.
10. Reconstruct or update the OSTF structure.
11. Save the result as an OSTF file.

This allows OSTF Composer to work as a bridge between structured composition and practical DAW production.

## OSTF compatibility

OSTF Composer is designed around the Open Song Timeline Format.

The device is intended to preserve song information that is not directly being edited.

Important principles include:

- Do not silently discard unknown OSTF data
- Preserve unrelated song information
- Preserve lyrics and external track information when possible
- Avoid destructive timeline changes when dependent data cannot be safely updated
- Preserve OSTF 3.5 note semantics such as `fixedTrigger`
- Mark dependent information stale when appropriate instead of pretending it is still current

OSTF project:

https://github.com/yoh-nak/Open-Song-Timeline-Format-3.5

## Requirements

- Ableton Live
- Max for Live
- A supported Windows or macOS environment
- MIDI track and instrument when auditioning through Live

## Installation

1. Download `OSTF_Composer_v1.0.amxd`.
2. Place the device in your Max for Live device folder or another location accessible from Ableton Live.
3. Drag OSTF Composer onto a MIDI track.
4. Click **Open** on the device view.
5. The OSTF Composer editor window will open.

## Basic usage

### Start a new song

Use **New** and create your song structure manually or choose a template.

Add sections such as:

- Intro
- Verse
- Pre-Chorus
- Chorus
- Bridge
- Outro

### Generate chord progressions

Click **Compose song** to open the Whole Song Composer.

Choose the desired:

- Genre
- Mood
- Harmonic color
- Pattern focus
- Variation

Generate multiple ideas, click a progression card to audition it, and apply the progression you prefer.

### Generate voicings

Open **Voicing Studio**.

Choose the desired accompaniment and voice-leading settings, then generate whole-song voicings.

Audition the candidate before committing it.

### Capture MIDI

1. Double-click the source MIDI clip in Ableton Live.
2. Open the MIDI Capture workspace.
3. Click **Capture MIDI**.
4. Drag across the Capture Timeline to select a range.
5. Assign the range to an OSTF section.
6. Repeat as needed.
7. Commit the assigned ranges.

### Send MIDI to Live

Use **Send to Live** from Voicing Studio.

Choose:

- Destination track
- Scope
- Clip split behavior
- Start position

Review the output and click **Write to Live**.

## Safety and non-destructive behavior

OSTF Composer is designed to avoid silently changing data that the current operation does not need to modify.

Examples:

- Captured Live MIDI is never edited in place
- Unassigned Capture ranges are ignored
- Existing Live clips are not overwritten without explicit action
- OSTF lyrics and unrelated tracks are preserved when possible
- Unsupported timeline transformations are blocked instead of applied destructively

Always keep backups of important project files.

## Version

### v1.0

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
- OSTF 3.5-oriented metadata and note handling
- Transposition support
- Undo / Redo
- Non-destructive editing safeguards

## Known considerations

OSTF Composer combines a large number of song editing, MIDI capture, Live API, and OSTF state-management functions.

If you encounter a repeatable issue, please include:

- Ableton Live version
- Max version
- Operating system
- Steps needed to reproduce the issue
- OSTF file if relevant
- Screenshot of the problem
- Max Console output if available

This makes problems much easier to reproduce and fix.

## License

No license is currently bundled with this repository unless one is added separately.

If you plan to reuse, redistribute, or modify the project, please check the repository license status first.

## Support the project

If OSTF Composer or the wider OSTF project is useful to you, you can support development here:

**Buy Me a Coffee**

https://buymeacoffee.com/yohsukenak

Support helps continued development, testing, documentation, and maintenance of the OSTF ecosystem.

## Links

### Open Song Timeline Format

https://github.com/yoh-nak/Open-Song-Timeline-Format-3.5

### Buy Me a Coffee

https://buymeacoffee.com/yohsukenak

## Author

Developed by **yoh-nak**.

OSTF Composer is part of the broader Open Song Timeline Format ecosystem for structured songwriting, composition, arrangement, and DAW interoperability.
