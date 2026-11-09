# OSTF Composer for Max for Live

**OSTF Composer v3.0** is a Max for Live MIDI device for structured songwriting, chord progression composition, harmony exploration, arrangement-aware review, chord voicing, MIDI capture, and Ableton Live integration. It is built around the **Open Song Timeline Format (OSTF)**.

Instead of working with isolated chord loops, OSTF Composer treats the song as a connected timeline of sections, harmony events, voicings, and other musical information. You can sketch a complete arrangement, develop individual sections, compare harmonic alternatives, inspect finished progressions against written parts, capture chords from Live, and return MIDI to Live.

## What's new in v3.0

Version 3.0 focuses on connecting **Live MIDI capture with editable OSTF harmony** while retaining the composition, review, and voicing tools introduced in earlier releases.

- **Range-first MIDI Capture** with a source-note timeline, detected harmonic boundaries, range selection, and staged section assignments.
- **Existing-section overwrite** of selected harmony/voicing targets, not just creation of new sections.
- **Chord-name confirmation** before capture changes are written, including alternative harmonic interpretations and slash-chord candidates when available.
- **One Review → Commit operation** for queued capture assignments, with Undo available for the committed change.
- **New-section construction and section reconstruction** from captured MIDI while keeping the source Live clip read-only.
- **Standard MIDI File (`.mid`) export** in addition to MIDI output to Ableton Live.
- Continued development of **Harmony Studio, Section Composer, Review Studio, and Voicing Studio**, with explicit separation between analysis, audition, and committed changes.
- **Explicit-key generation policy:** harmony suggestions require a supported, specified tonal key. Missing or unsupported keys should produce guidance, not silently inferred changes to the saved key map.
- Preservation-oriented editing of compatible **OSTF 3.x / 4.x**, including 4.1-era song information the device does not directly edit.

> **Release note:** The v3.0 documentation describes the intended feature set. Verify the exact device build in Ableton Live before publishing it as a tested release, especially the three harmony studios and capture-to-commit workflow.

---

## Core features

- OSTF song structure and chord timeline editing
- Whole-song chord composition and section-aware progression generation
- Genre, section-role, harmonic-depth, and pattern-focus controls
- Section Composer for detailed local harmonic development
- Harmony Studio for cross-section exploration and theory maps
- Review Studio for conservative, arrangement-aware harmonic refinement
- Voicing Studio with candidates, auditioning, voice-leading, and piano-roll editing
- MIDI Capture from selected Ableton Live MIDI clips
- New-section creation and explicit overwriting of existing harmony/voicing data
- Confirmation of detected or alternative chord names before capture commit
- MIDI output to Live and Standard MIDI File export
- OSTF import/export, transposition, Undo/Redo, and non-destructive editing safeguards

## Song structure and OSTF workflow

Create or edit complete song arrangements. OSTF Composer supports sections such as **Intro, Verse, Pre-Chorus, Chorus, Drop, Breakdown, Bridge, Solo, Final Chorus, Outro**, and custom section names.

You can create, rename, duplicate, delete, reorder, and resize sections; edit chord events; split harmonic regions when needed; transpose supported content; and maintain song-level tempo, meter, key, genre, and other metadata. Section-local key maps can be used where the song changes key.

The left-hand song editor is the main destination for committed song structure and chord information. The studios on the right are designed for proposing, auditioning, reviewing, or preparing changes before those changes are applied.

Composer edits the OSTF data relevant to the operation and aims to preserve unrelated lyrics, melody tracks, arrangement parts, performance information, and unknown compatible fields.

## Keys and harmony suggestions

**A supported tonal key must be specified before generating key-dependent harmony suggestions.** This is intentional. A progression can exist in OSTF without a declared key, but the generation engine should not silently decide the song's key for you.

- **Supported explicit key:** suggestions and harmonic analysis can proceed.
- **Missing key:** generation is withheld and the interface should explain that a supported key is required.
- **Unsupported mode or key representation:** the interface should explain the limitation rather than generate against an arbitrary substitute.
- **Local key maps:** the relevant key at the target section or position is used when supported.
- **Temporary local override:** Section Composer can use an explicitly selected preview/generation key without silently changing the stored OSTF song key.

Music-theory inspection and editing of existing chord symbols are not the same operation as key-dependent suggestion generation. The saved key map must not be changed merely because a generated alternative was auditioned.

---

## Whole-song chord composition

Use **Compose song** to explore progressions across the complete arrangement, rather than constructing every section as an unrelated four-chord loop.

Generation can consider the global genre, local style, mood, chord color, harmonic depth, pattern focus, variation, section roles, neighboring sections, key maps, cadences, harmonic continuity, tension, and release. Multiple ideas can be auditioned and compared before committing.

Initial suggestions aim to stay close to the chosen genre and section function. **More ideas** supports broader exploration without automatically replacing the original song.

### Genre-aware behavior

Genre-aware suggestions cover a broad range of styles, including **Pop, J-Pop, Rock, Ballad, RnB, Neo Soul, House, Deep House, Tech House, Techno, Minimal Techno, Trance, EDM, Jazz, Metal, and Ambient**, plus compatible genre definitions.

Genre influences ranking and harmonic vocabulary; changing it does not by itself rewrite unrelated OSTF data. Electronic subgenres and RnB/Neo Soul are treated as distinct harmonic contexts rather than a single generic category.

### Section-role-aware behavior

Intro, Verse, Pre-Chorus, Chorus, Drop, Breakdown, Bridge, Solo, Outro, and custom roles can influence stability, repetition, dominant preparation, contrast, cadence strength, energy, and finality. A Breakdown or Drop need not behave like a Verse.

### Harmonic Depth and Pattern Focus

**Harmonic Depth** ranges from genre-appropriate core progressions to more colorful or advanced choices. **Pattern Focus** can emphasize cadences, secondary dominants, borrowed harmony, backdoor motion, chromatic and tritone movement, extended colors, slash-chord bass movement, line cliché, suspension/release, and complete phrases.

These options guide candidate generation; they are not destructive transformations of the current song.

---

## Section Composer

Open **Compose** from a section header to develop a particular section in detail. Section Composer provides automatic suggestions and focused approaches such as harmonic function, emotion, bass movement, cadence, color, variation, modulation, and reverse analysis.

The **Song Blueprint** view helps you examine the chosen section in the context of the overall arrangement and its intended tension arc. Suggested progressions can be auditioned and compared before application. A working key can be explicitly overridden for generation-only purposes when required.

Section Composer is intended for local development after the broad song structure has been established. The generated proposal should not change other sections or unrelated tracks unless an explicit operation calls for it.

## Harmony Studio

**Harmony Studio** explores harmonic alternatives and relationships across a selected range that may span section boundaries. It works with existing progressions, neighboring chords, harmonic functions, root movement, key relationships, cadences, tension, resolution, and section-to-section transitions.

Its exploration tools include:

- Substitution, harmonic color, variations, and transitions to the next section
- Borrowed harmony, applied dominants, chromatic movement, and modulation pathways
- Visual **Circle of Fifths**, **Harmonic Functions**, **Tonnetz (P/R/L)**, and **Camelot Wheel** maps
- Original-versus-proposal comparison and audition before applying a chosen idea

Tonnetz visualizes Neo-Riemannian relationships: **P** (Parallel), **L** (Leading-tone exchange), and **R** (Relative). Theory maps support exploration but are not a substitute for the progression generator.

Harmony Studio can suggest different directions while keeping the original material intact until an explicit commit is made.

## Modulation and transitions

Composer can explore direct modulation, pivot harmony, dominant preparation, common-tone links, chromatic approaches, borrowed chords, and transition chords.

Existing OSTF key maps represent intentional musical decisions. Auditioning a proposal must not silently alter those maps; any saved key change should result from an explicit editing operation.

---

## Review Studio

**Review Studio**, introduced in v2.0, is intended for refining an already-developed progression without needlessly rewriting it. It can open for the whole song or with one section preselected.

Review considers the existing harmony, section roles, neighboring and recurring sections, song-wide contrast, key maps, chord duration, harmonic rhythm, and available written musical context.

Where the OSTF song includes pitched arrangement data, review can consider primary and additional melody tracks, strong or sustained notes, bass notes, supporting pitched tracks, beat position, and chord overlap. Structural and sustained notes generally matter more than brief passing ornaments; bass evidence is distinguished from inner voices.

Possible ideas include:

- Keep the progression unchanged when it already fits
- Improve section handoffs, cadences, and bass motion
- Add restrained chord color supported by the melody
- Refine a chord to fit written arrangement notes
- Introduce an A → A′ variation or reduce unnecessary repetition
- Improve section contrast, tension, and release
- Refine transitions into declared key changes
- Optionally split a long chord region **within its existing time span** when arrangement evidence supports a harmonic change

### Review safeguards

Review can evaluate **benefit, confidence, risk, and overall quality**. Low-confidence or unnecessarily disruptive ideas may be withheld from normal automatic results. “Keep the current progression” is a valid result. Experimental changes should remain intentional rather than being forced into a finished song.

**Review Studio does not regenerate note performances or voicings.** It primarily proposes changes to chord identity, chord color, slash-bass interpretation, harmonic boundaries, and related harmonic information. The user chooses and applies a proposal explicitly. Changes to other OSTF tracks are not implied.

### Song-wide context

Repeated Chorus sections, Verse 1 versus Verse 2, similar shapes in different keys, weak contrast, and harmonic energy across Intro → Verse → Build → Chorus → Outro can be compared as supporting evidence. These are musical heuristics, not strict rules.

---

## Voicing Studio

Voicing Studio generates and edits **actual MIDI note voicings** for OSTF chord events. This is separate from Review Studio's harmonic-name and chord-boundary suggestions.

Available controls and workflows include:

- Whole-song and per-section voicing candidates
- Original/Candidate comparison and MIDI audition
- Presets for different accompaniment and voicing styles
- Register, inversions, bass and top-note control
- Voice leading, guide tones, fifth omission, tensions, and avoid-note warnings
- Left-hand/right-hand voicing layout and melody clearance
- Manual piano-roll editing and per-section adoption
- Explicit Commit, Discard, and Undo workflows

**Voicing presets are not the same as OSTF Genre.** The genre can influence a suggested preset but does not automatically overwrite a manually selected voicing style.

The piano roll supports inspecting and editing notes, including selection, movement, addition and deletion, and audition. Harmonic roles may be visually distinguished to help identify roots, guide tones, fifths, and tensions.

A typical voicing workflow is: generate candidates → audition Original and Candidate → choose sections to adopt → optionally edit notes → commit → undo if needed.

---

## MIDI Capture from Ableton Live — v3.0 workflow

The **Capture from Live** workspace reads the selected Live MIDI clip and represents its harmonic content as a source timeline. The original Live clip remains **read-only**.

Capture is designed to determine **which pitches belong to each harmonic interval**. The source's original note starts and gate lengths are used for selection and analysis but are not automatically copied as the stored rhythm of a harmony/voicing event. The resulting OSTF voicing information can retain pitches and velocities while the chord timeline defines its harmonic boundaries.

### Step 1 — Read and analyze

1. Select a compatible MIDI clip in Ableton Live.
2. Open the Composer editor and go to **Capture from Live**.
3. Select the source and click **Capture MIDI**.
4. Inspect source notes and detected chord intervals on the Capture Timeline.
5. Adjust the chord-boundary resolution or reanalyze a selection if required.

Capture can show possible chord labels and slash-bass interpretations, but these are **candidates**, not final labels until the review step.

### Step 2 — Select a range and assign it

Drag across the source timeline or select the required bar/chord range. Stage an assignment that maps it to an OSTF destination. Depending on the operation and available controls, you can:

- **Create a new section** using the captured harmonic intervals
- **Overwrite an existing section's selected harmony/voicing events**
- **Extend or reconstruct a section** when the assignment and destination allow it
- Repeat to queue additional non-conflicting ranges

For existing-section overwrite, select the destination section and starting bar. The intended operation replaces only the selected chord names/voicings according to the chosen capture mode; it is **not** a request to wipe the entire song, rewrite the Live clip, or regenerate unrelated performance tracks.

For chord-name/voicing replacement, chord identity and note pitches may change while the existing target's timing, event identity, and links to lyrics or other data are preserved where the operation requires that behavior. When the desired chord boundaries are structurally different, create or reconstruct a section instead of assuming an in-place rename can change the timeline safely.

### Step 3 — Review detected harmony

Click **Add Range & Review** or **Review queued assignments**, depending on the current interface state.

The confirmation screen presents the captured voicings and chord-label choices **for each target interval**. Where the pitches admit more than one harmonic interpretation, Composer can offer multiple candidates, including slash-chord names when applicable.

You can keep a written chord name, accept a suggested name, or choose another available interpretation. **A suggested chord name is not silently forced on the song.** Verify the musical interpretation and destination before committing.

### Step 4 — Commit and Undo

Use the explicit confirmation action to write the reviewed assignments into the left-hand OSTF song editor. The intended result is visible as new or replaced sections/chords in the main song timeline.

The queued assignments are temporary workspace data until Commit. A successful commit is a single Undo operation. If the result is not correct, Undo should restore the previous committed song state.

**Important:** Review-confirmed existing chord destinations are editable. A legacy voicing lock must not silently prevent a user-approved overwrite. Safety checks should reject invalid or ambiguous destination operations, not permanently lock an otherwise valid chord event.

### Capture versus Voicing Studio

Capture source notes and Voicing Studio notes are kept separate by default. A capture overlay can be enabled for comparison. Captured notes do not automatically appear as committed Voicing Studio notes, and captured source MIDI is never edited in place.

---

## Send MIDI to Ableton Live

Composer can output generated or edited voicing MIDI to a selected Live MIDI track. Output can cover the whole song, a section, or a supported selected range, depending on the active context.

### Append to an existing MIDI clip

When the selected destination supports clip append, Composer can add output notes beginning at a specified **clip bar**, without deleting existing notes. This is an append operation, not a blanket replace operation.

### Create a new MIDI clip

A new clip can be created on a selected MIDI track. Available settings include output scope, destination, Arrangement placement, splitting behavior, and start position. For precise Arrangement placement, use **Specific Live bar** where available.

Safety checks aim to avoid overwriting unrelated Arrangement clips without explicit intent. A conflicting or unsupported write can be blocked.

### Standard MIDI File export — v3.0

Version 3.0 adds **direct `.mid` export** of generated/edited MIDI using the device's native file-save workflow. This is separate from sending notes to a Live clip.

The MIDI file export applies to the selected available output scope. Save the file using the file dialog and check the destination. Exporting a MIDI file does not itself change the OSTF song or the Live clips.

For additional editing or a Live-specific export workflow, you can still send the MIDI to Live and export from Live.

---

## Other editing tools

### Transposition

Composer provides transposition tools for compatible chord symbols, voicings, notes, and key-related information. Information that should not transpose is preserved when possible. Unsupported transformations should stop rather than damage the song.

### Undo and Redo

Committed chord, structure, voicing, capture, and review edits can participate in Undo/Redo as supported by the operation. Auditioning a candidate is not itself a committed edit.

### OSTF import and save

Use **New**, **Open**, and **Save OSTF** for the song-document workflow. Composer is designed to preserve information it does not directly edit and to avoid silent format downgrades.

---

## OSTF compatibility and data preservation

OSTF Composer works with the **OSTF 3.x / 4.x family** and aims to retain compatible 4.1-era content. The supported behavior depends on the structure and fields understood by the version of Composer in use; this should not be interpreted as a guarantee that every possible future OSTF field is editable.

OSTF 4.x can include additional musical and performance information, for example:

- Multiple melody tracks and lyric voices
- Chord and voicing information
- Arrangement parts and pitched performance tracks
- Control Change, Program Change, Pitch Bend, and channel/polyphonic pressure
- MIDI channel and bus information
- Song, section, tempo, meter, key, and genre metadata

Composer focuses on harmony, structure, review, voicings, MIDI capture, and related workflows. Other compatible fields are preserved wherever possible rather than regenerated or discarded.

Principles of the non-destructive design:

1. Suggestions are not applied until an explicit **Apply** or **Commit**.
2. Captured Live MIDI is never modified in place.
3. Capture assignments remain staged until reviewed and committed.
4. Confirmed target chords can be intentionally overwritten; unrelated chords and performance tracks should not be.
5. Existing chord timing, IDs, lyric associations, and section structure are preserved where required by the chosen operation.
6. Unknown compatible OSTF data should not be silently dropped.
7. Harmonic review should not implicitly regenerate existing performance parts.
8. Existing Live notes should not be deleted during append output.
9. Saving should stop or warn if protected data would change unexpectedly.
10. Back up important OSTF files and Ableton Live projects before major operations.

---

## Typical workflow

1. **New** or **Open** an OSTF song.
2. Set a supported song key or the appropriate section-local key before key-dependent generation.
3. Build the arrangement structure and edit chords.
4. Use **Compose song** to generate whole-song progression ideas.
5. Develop individual sections with **Section Composer**.
6. Explore transitions or alternatives in **Harmony Studio**.
7. Review an already developed song in **Review Studio** and apply only useful refinements.
8. Generate, audition, and edit voicings in **Voicing Studio**.
9. **Send to Live** or **Export .MID** as appropriate.
10. If you have an existing Live MIDI chord part, **Capture MIDI**, assign its intervals to sections, review chord names, and commit them back to OSTF.
11. Save the OSTF song, and continue arranging in Live.

---

## Installation

1. Download **`OSTF_Composer_v3.0.amxd`** from the release.
2. Place it in your Max for Live device folder or another location accessible from Ableton Live.
3. Drag the device onto an **Ableton Live MIDI track**.
4. Click **Open** in the device view to open the separate Composer editor window.
5. Use an appropriate Live MIDI instrument when auditioning through Live.

**Requirements:** Ableton Live with Max for Live, on an operating system supported by that Live/Max combination. Compatibility may vary by Live/Max version; consult release notes and test your setup. The editor interface is in English.

## Troubleshooting and known considerations

**No chord suggestions appear:** Confirm that the song/section has a supported, explicitly specified tonal key. If the key field appears populated but Composer reports it as missing or unsupported, report the OSTF file and reproduction steps; do not assume this is intended behavior.

**A studio stays at “Preparing…”:** This is not a normal final result. Close and reopen the studio and report the version, song, and repeatable steps. Do not commit unintended proposals.

**Capture does not update the left-hand song editor:** Verify that the captured range was assigned, that the assignment was reviewed, and that the confirmation/Commit action completed. Merely capturing MIDI or adding a queued assignment does not alter the song.

**Detected chord names look different from the intended harmony:** The same pitch set can have multiple chord-name interpretations. Inspect the alternatives in the capture confirmation screen and choose the intended meaning before committing.

**Live MIDI cannot be heard:** Check that the output track has a suitable instrument, that Live is in the expected transport/monitor state, and that the device is using the intended audition/output route.

**Send to Live is blocked:** Confirm the destination track/clip, output scope, placement, and any overlap warning. The device favors explicit and safe writes over silent replacement.

For repeatable bugs, include the Composer version, Ableton Live/Max version, operating system, reproduction steps, screenshots, relevant OSTF file, and Max Console output where available.

---

## Version history

### v3.0 — MIDI Capture and workflow integration

- Range-first Capture from Live timeline and chord-boundary analysis
- Staged assignment of captured ranges to OSTF sections
- New-section generation and existing-section chord/voicing overwrite
- Chord interpretation choices before capture commit, including alternative/slash-chord names where available
- Explicit Review → Commit workflow with Undo
- Preservation of the original Live MIDI and unrelated OSTF performance tracks
- Direct Standard MIDI File (`.mid`) export
- Continued Harmony Studio, Section Composer, and Review Studio integration
- Explicit supported-key requirement for key-dependent suggestions
- Continued compatibility and preservation work for OSTF 3.x / 4.x, including 4.1-era structures
- UI and stability refinements

### v2.0 — Harmony generation and Review Studio

- Review Studio with arrangement-aware chord review and conservative suggestions
- Melody- and bass-aware chord color and slash-bass proposals
- Optional chord-boundary refinement within an existing time span
- Song-wide section comparison and harmonic-energy analysis
- Benefit/confidence/risk-based review quality gating
- Better whole-song generation and Section Composer behavior
- Improved genre-specific ranking, especially electronic genres, RnB, and Neo Soul
- Dedicated Drop, Breakdown, and Solo generation behavior
- Improved modulation pathways, Harmony Studio maps, and Tonnetz layout
- Voicing preset and candidate workflow refinements
- Compatibility and non-destructive OSTF data preservation

### v1.1 — OSTF 4.x and Live output improvements

- Compatibility and preservation work for OSTF 4.x performance/multi-voice information
- Voicing Studio UI and candidate workflow updates
- Selected-clip append and specific placement controls
- Improved protection against unintended Live clip replacement
- MIDI capture stability work
- Experimental MIDI file export removed from the v1.1/v2.0 workflow in favor of Live output

### v1.0 — Initial release

- OSTF song/structure/chord editing
- Whole-song composition and Section Composer
- Voicing Studio and piano-roll editing
- MIDI Capture and section reconstruction
- MIDI output to Live, transposition, Undo/Redo, and preservation safeguards

---

## Open Song Timeline Format

OSTF provides a structured, text-based representation of song structure, chord progressions, melody, lyrics, arrangements, performance information, key and tempo changes, and musical metadata. Composer is one tool in a broader ecosystem for exchanging musical ideas between applications and Ableton Live workflows.

See the OSTF repositories for specifications, examples, and related tools.

## License

No license is currently bundled with this repository unless one is added separately. Check the repository's actual license status before reusing, redistributing, or modifying this project.

## Support the project

If OSTF Composer is useful to you, you can support continued development, testing, documentation, and maintenance through **Buy Me a Coffee**:

https://buymeacoffee.com/yohsukenak

## Links

- **OSTF Composer:** https://github.com/yoh-nak/OSTF-Composer-M4L
- **Open Song Timeline Format:** https://github.com/yoh-nak/
- **Buy Me a Coffee:** https://buymeacoffee.com/yohsukenak

## Author

Developed by **yoh-nak** as part of the Open Song Timeline Format ecosystem for structured songwriting, harmony exploration, arrangement review, and MIDI/DAW interoperability.
