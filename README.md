# OSTF Composer for Max for Live

**OSTF Composer** is a Max for Live songwriting, chord composition, harmony exploration, review, voicing, MIDI capture, and Ableton Live workflow tool built around the **Open Song Timeline Format (OSTF)**.

It is designed for composers, songwriters, arrangers, and producers who want to build complete song structures, generate and refine chord progressions, explore harmony across song sections, review finished harmony in the context of written melodies and arrangement parts, create playable voicings, capture MIDI from Ableton Live, reconstruct song sections, and move structured musical ideas between OSTF and Live.

OSTF Composer combines:

- Song structure editing
- Whole-song chord composition
- Section-level chord generation
- Cross-section harmony exploration
- Arrangement-aware harmony review
- Chord progression suggestions
- Genre- and section-role-aware generation
- Modulation and harmonic transition ideas
- Voicing generation and editing
- MIDI capture from Ableton Live
- Section reconstruction
- MIDI output back to Live
- OSTF 3.x / 4.x compatibility
- Non-destructive OSTF data preservation

Version **2.0** significantly expands chord-generation quality, song-wide harmonic context, suggestion ranking, section-aware harmony workflows, and introduces the new **Review Studio** for refining already-developed songs without unnecessarily rewriting them.

---

# Features

## OSTF-based songwriting workflow

Create and edit structured songs using OSTF.

You can:

- Create and rename song sections
- Build structures such as Intro, Verse, Pre-Chorus, Chorus, Drop, Breakdown, Bridge, Solo, Final Chorus, Outro, and custom sections
- Change section lengths
- Edit chord timelines
- Split chord regions where needed
- Reorder song sections
- Duplicate and delete sections
- Preserve surrounding OSTF song data while editing
- Work with song-level key, tempo, meter, genre, and metadata
- Work with section-local key maps
- Save edited songs back to OSTF

OSTF Composer is intended to edit the musical information it understands while preserving unrelated OSTF information wherever possible.

---

# Whole-Song Chord Composition

Use **Compose song** to generate chord progression ideas across the complete arrangement.

Generation can take into account:

- Genre
- Mood
- Harmonic color
- Harmonic depth
- Section roles
- Local key maps
- Neighboring sections
- Song structure
- Pattern focus
- Variation level
- Harmonic continuity
- Cadence behavior
- Section-to-section tension and release

Multiple progression ideas can be generated and compared before committing changes.

Progressions can be auditioned before they are applied.

The whole-song workflow is designed to consider the relationship between sections rather than treating every section as an isolated four-chord loop.

Version 2.0 improves the ranking of generated ideas so that the first suggestions remain closer to the selected genre and section role.

Additional exploration through **More ideas** can gradually move toward broader harmonic alternatives.

---

# Genre-aware generation

OSTF Composer includes genre-aware progression behavior for styles including:

- Pop
- J-Pop
- Rock
- Ballad
- RnB
- Neo Soul
- House
- Deep House
- Tech House
- Techno
- Minimal Techno
- Trance
- EDM
- Jazz
- Metal
- Ambient
- Additional compatible genre definitions

Version 2.0 improves separation between electronic genres.

House, Tech House, Techno, Trance, and EDM are no longer treated as a single generic electronic style during initial suggestion ranking.

RnB and Neo Soul also receive more dedicated progression behavior instead of being dominated by generic Jazz harmony.

Genre selection influences generation and suggestion ranking, but does not silently rewrite unrelated OSTF information.

---

# Section-role-aware generation

Chord generation can respond to the musical role of a section.

Supported roles include concepts such as:

- Intro
- Verse
- Pre-Chorus
- Chorus
- Drop
- Breakdown
- Bridge
- Solo
- Outro
- Custom or inferred section roles

Section roles affect behavior such as:

- Harmonic stability
- Tension
- Cadence strength
- Dominant preparation
- Repetition
- Resolution
- Contrast
- Finality
- Energy

Version 2.0 gives Drop, Breakdown, and Solo dedicated generation behavior instead of relying on Verse-style fallback patterns.

---

# Section Composer

Section Composer provides detailed harmonic development for individual song sections.

Available approaches include:

- Automatic progression suggestions
- Harmonic function
- Emotional direction
- Bass movement
- Cadence ideas
- Harmonic color
- Variation
- Borrowed harmony
- Applied dominants
- Backdoor movement
- Chromatic movement
- Tritone-related ideas
- Slash chords
- Line cliché
- Same-root harmonic movement
- Suspension and release
- Modulation pathways
- Reverse analysis
- Complete phrase generation

Generated ideas can be auditioned before being committed.

This makes it possible to establish the overall structure with Whole-Song Composition and then develop individual sections where necessary.

---

# Harmonic Depth

Generation can be limited or expanded through **Harmonic Depth**.

Typical levels include:

- Auto by genre
- Core progressions
- Color / borrowing
- Advanced harmony

This allows a simple Pop section and a more harmonically complex Neo Soul or Jazz section to use different harmonic vocabularies without requiring separate devices.

---

# Pattern Focus

Pattern Focus can direct generation toward specific harmonic ideas.

Available directions include:

- Genre / role aware
- Cadences
- Applied dominants
- Borrowed harmony
- Backdoor movement
- Chromatic movement
- Tritone movement
- Extended chord colors
- 6th / sus / add / 9th colors
- Slash chords and bass movement
- Line cliché
- Same-root motion
- Genre color
- Suspension / tension → release
- Complete phrase generation

Pattern Focus is intended as a creative direction rather than a destructive transformation.

---

# Harmony Studio

**Harmony Studio** is designed for exploring alternative harmonic ideas across existing song sections.

Unlike Section Composer, which focuses primarily on generating one section, Harmony Studio can examine relationships across multiple sections and generate alternative harmonic paths.

Harmony Studio can work with:

- Existing section progressions
- Neighboring sections
- Section roles
- Key maps
- Harmonic functions
- Bass-root motion
- Cadences
- Borrowed harmony
- Applied dominants
- Chromatic movement
- Tritone relationships
- Modulation pathways
- Tension and resolution
- Recurring sections
- Whole-song harmonic continuity

Harmony Studio is intended for exploration.

It can suggest significantly different harmonic directions while preserving the original material until the user explicitly applies a result.

---

# Theory Map

Harmony Studio includes interactive harmonic maps for exploring chord relationships.

Available map views include:

- Circle of Fifths
- Harmonic Functions
- Tonnetz · P / R / L
- Camelot Wheel

The map can be used to inspect and explore harmonic relationships visually.

Tonnetz includes Neo-Riemannian transformations such as:

- P — Parallel
- L — Leading-tone exchange
- R — Relative

These visual tools are intended to complement harmonic suggestions rather than replace the chord-generation engine.

---

# Modulation and harmonic transitions

OSTF Composer can generate modulation pathways and section-to-section harmonic transition ideas.

Possible approaches include:

- Direct modulation
- Pivot relationships
- Dominant preparation
- Secondary dominant movement
- Chromatic approaches
- Tritone-related movement
- Common-tone relationships
- Borrowed harmony
- Transition chords

Existing OSTF key maps are treated as intentional musical information.

Chord suggestions do not silently rewrite the key map unless the user explicitly performs an operation that changes it.

---

# Review Studio

Version 2.0 introduces **Review Studio**.

Review Studio is designed for songs where the overall harmony is already substantially complete.

Its purpose is not to regenerate the song.

Instead, it looks for small opportunities to improve an existing chord progression while preserving the current musical identity.

Review Studio can be opened globally or directly from an individual section.

When opened from a section, that section is selected as the initial review target while the rest of the song can still be used as context.

Review Studio can analyze:

- Current chord progression
- Section role
- Neighboring sections
- Recurring sections
- Whole-song harmonic similarity
- Key maps
- Melody notes
- Multiple declared melody tracks
- Bass-related notes
- Supporting pitched arrangement tracks
- Chord duration
- Harmonic rhythm
- Strong beats
- Sustained notes
- Written arrangement context

Possible review ideas include:

- Keep the current progression
- Improve section handoff
- Improve bass direction
- Add restrained harmonic color
- Add a melody-supported tension
- Add a slash chord supported by the written bass
- Refine one chord to better fit the arrangement
- Create an A → A' variation
- Reduce unnecessary repetition
- Improve contrast between similar sections
- Add tension and release
- Refine a transition into an existing key change
- Split a long chord region when the written arrangement supports a harmonic change
- Offer an optional chromatic alternative

Review Studio is deliberately conservative.

It is designed to improve a finished song rather than rewrite it.

---

# Arrangement-aware harmony review

When OSTF contains melody and other pitched arrangement tracks, Review Studio can use those notes as evidence.

The analysis can consider:

- Primary melody
- Additional melody tracks
- Strong melody notes
- Sustained melody notes
- Bass tracks
- Lowest supporting notes
- Other pitched arrangement parts
- Beat position
- Note duration
- Chord overlap

Short decorative notes and likely passing tones are intentionally weighted less strongly than structural notes.

This reduces the chance that a brief melodic decoration causes an unnecessary chord change.

Bass-related evidence is also weighted more strongly than unrelated inner arrangement notes.

---

# Melody-supported chord color

Review Studio can identify cases where the written melody already implies a chord extension.

For example, if a strong sustained melody note functions naturally as a 9th, 11th, 13th, major 7th, or other available color, Composer may suggest representing that sound in the chord symbol.

The written melody itself is not changed.

The suggestion changes only the harmonic interpretation unless the user explicitly applies another editing operation.

---

# Chord-boundary refinement

Review Studio can optionally suggest splitting a long chord event when the written arrangement clearly changes during the chord.

For example, a four-beat chord may become:

- Original chord for beats 1–2
- Related or extended chord for beats 3–4

This happens inside the existing time range.

The section length does not change.

Other OSTF tracks are not shifted.

Chord-boundary refinement is optional and can be disabled.

---

# Review confidence and risk

Version 2.0 adds quality gating to Review Studio.

Suggestions can be evaluated using concepts such as:

- Benefit
- Confidence
- Risk
- Overall review score

Low-confidence or unnecessarily high-risk changes can be excluded from the normal automatic review.

If the current progression is already appropriate, Review Studio is allowed to return:

**Keep the current progression**

instead of forcing a change.

Experimental or surprising chromatic ideas remain available when explicitly requested, but they are not intended to dominate normal review results.

---

# Song-wide review

Review Studio can compare a selected section with the rest of the song.

This can detect relationships such as:

- Verse and Chorus using almost identical harmonic shapes
- Repeated Chorus sections with no development
- Verse 2 repeating Verse 1 exactly
- Similar functional progressions in different keys
- Missing contrast between major structural sections
- Existing key-map transitions
- Song-wide harmonic energy imbalance

This allows a single section to be reviewed in the context of the complete song.

---

# Harmonic energy

Review Studio can estimate relative harmonic energy across sections.

Section roles can imply different expected behaviors.

For example:

- Intro may remain relatively stable
- Verse may remain restrained
- Pre-Chorus may build tension
- Chorus may provide stronger arrival or energy
- Drop may emphasize impact or repetition
- Breakdown may reduce density
- Final Chorus may maintain or increase intensity
- Outro may provide stronger finality

This is used as supporting review evidence rather than as a rigid compositional rule.

---

# Voicing Studio

Voicing Studio generates and edits playable chord voicings based on the current OSTF chord progression.

Voicing Studio is intentionally separate from Review Studio.

Review Studio works primarily with:

- Chord identity
- Chord color
- Slash-bass interpretation
- Harmonic boundaries

Voicing Studio handles:

- Actual note placement
- Register
- Voice distribution
- Inversions
- Left-hand / right-hand arrangement
- Voice leading

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

---

# Voicing presets

Voicing Studio includes **Voicing presets**.

These are not song Genre settings.

They describe accompaniment and voicing behavior.

Examples may include:

- Pop-style accompaniment
- J-Pop two-hand comping
- Rock simple keys
- Ballad smooth accompaniment
- House compact right hand
- Techno minimal
- Trance wide voicings
- Jazz solo piano
- Jazz rootless trio
- Neo Soul guide tones
- Funk tight comping
- Cinematic wide register

The current song Genre may influence which Voicing preset is recommended.

Changing Genre does not automatically overwrite an already-selected Voicing preset.

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

Notes can be visually differentiated by harmonic role so that roots, thirds, fifths, sevenths, tensions, and other chord tones are easier to identify.

When chord information changes, harmonic interpretation can be updated accordingly.

---

# MIDI Capture from Ableton Live

OSTF Composer can capture MIDI from a selected Ableton Live MIDI clip.

The original Live clip remains read-only.

The Capture workflow can:

- Read MIDI from Live
- Display captured MIDI
- Analyze detected chords
- Select ranges from captured material
- Assign ranges to OSTF sections
- Create new sections
- Extend existing sections
- Insert sections before or after existing sections
- Reconstruct an OSTF song structure from existing MIDI

Captured MIDI is intentionally kept separate from Voicing Studio data.

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

The insertion point can be specified by clip bar.

Examples:

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

Example:

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

OSTF Composer v2.0 does **not** include direct Standard MIDI File export.

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
- Review Studio applications
- Candidate commits
- Other Composer editing actions

Undo behavior is intentionally tied to committed editing operations rather than temporary audition states.

---

# OSTF compatibility

OSTF Composer v2.0 supports the OSTF 3.x family and OSTF 4.x compatibility workflow.

The device can work with older OSTF song structures while also recognizing OSTF 4 data.

OSTF 4 can include additional musical performance information such as:

- Control Change
- Program Change
- Pitch Bend
- Channel Pressure
- Polyphonic Pressure
- MIDI channel information
- MIDI bus information
- Multiple melody tracks
- Multiple lyric voices

OSTF Composer is primarily a chord, structure, harmony, review, voicing, and composition editor.

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

- Review Studio ideas do not modify the song until Apply is used
- Melody and arrangement notes remain unchanged during harmony review
- Voicings are not automatically regenerated by Review Studio
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

A common OSTF Composer v2.0 workflow is:

1. Create or open an OSTF song.
2. Build or refine the song structure.
3. Generate whole-song chord progression ideas with **Compose song**.
4. Audition and select a progression.
5. Develop individual sections with **Section Composer**.
6. Explore alternative cross-section harmony in **Harmony Studio**.
7. Review the completed progression with **Review Studio**.
8. Apply only the review ideas that improve the song.
9. Generate whole-song voicing candidates in **Voicing Studio**.
10. Compare Original and Candidate versions.
11. Adopt the desired sections.
12. Edit voicings in the piano roll if necessary.
13. Commit the result.
14. Send MIDI to Ableton Live.
15. Continue arranging or editing in Live.
16. Capture edited MIDI back into Composer if structural reconstruction is needed.
17. Save the updated OSTF file.

This allows OSTF Composer to act as a bridge between structured songwriting, harmonic development, arrangement review, and practical DAW production.

---

# Installation

1. Download:

   `OSTF_Composer_v2.0.amxd`

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
- Drop
- Breakdown
- Bridge
- Solo
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

Configure generation settings such as:

- Genre
- Mood
- Harmonic color
- Harmonic depth
- Pattern focus
- Variation

Generate several ideas.

Audition the candidates and apply the progression you prefer.

Initial suggestions prioritize compatibility with the selected genre and section roles.

Use **More ideas** when you want to explore progressively broader alternatives.

---

## Develop a section

Click **Compose** in a section header.

Section Composer opens with that section as its target.

Use the available harmonic controls to generate, audition, compare, and apply alternatives.

---

## Explore harmony across sections

Open **Harmony Studio**.

Choose the range or sections you want to explore.

Use harmonic theory, neighboring sections, section roles, key relationships, and visual theory maps to explore alternative harmonic paths.

Harmony Studio is intended for broader harmonic exploration than Review Studio.

---

## Review a finished progression

Open **Review Studio** from the main controls or from a section header.

When opened from a section, that section is selected initially.

Choose the sections to review and configure options such as:

- Review focus
- Maximum changes
- OSTF note context
- Chord-boundary refinement

Click **Review selected sections**.

Review the proposed ideas.

Audition:

- Original
- Idea
- A/B comparison

Apply only the ideas you want to keep.

Review Studio may also recommend keeping the existing progression unchanged.

---

## Generate voicings

Open **Voicing Studio**.

Configure Voicing presets and voice-leading options.

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

## v2.0

Current release.

Main changes:

- New Review Studio
- Arrangement-aware harmony review
- Melody-aware tension suggestions
- Bass-aware slash-chord suggestions
- Supporting-track harmony analysis
- Optional chord-boundary refinement
- Whole-song section comparison
- Harmonic energy analysis
- Review Benefit / Confidence / Risk scoring
- Low-confidence suggestion filtering
- Keep-current-progression result when no change is necessary
- Improved whole-song chord composition
- Improved Section Composer generation
- Improved genre-aware progression ranking
- Improved section-role-aware generation
- Improved House / Tech House / Techno / Trance / EDM separation
- Improved RnB and Neo Soul generation
- Improved Metal and Ambient progression behavior
- Dedicated Drop, Breakdown, and Solo generation roles
- Improved modulation pathway suggestions
- Improved cross-section harmonic exploration
- Improved Theory Map behavior
- Circle of Fifths, Harmonic Functions, Tonnetz, and Camelot map switching
- Improved Tonnetz layout
- Improved responsive section controls
- Resizable Review Studio layout
- Improved Voicing preset labeling and genre recommendation behavior
- Improved minor-key seventh chord generation
- Improved initial Suggest ranking
- Broader exploration through More ideas
- Extensive generation and suggestion QA
- OSTF 3.x / 4.x compatibility retained
- Non-destructive OSTF data preservation retained

Release QA included large-scale progression and suggestion generation across multiple genres, roles, keys, and modulation paths.

---

## v1.1

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

OSTF Composer combines song editing, MIDI capture, Live API communication, harmony generation, song-wide review, voicing generation, and OSTF state management in a single Max for Live device.

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
- Multiple melody tracks
- Lyrics
- Multiple lyric voices
- Arrangement information
- MIDI performance data
- Key changes
- Tempo changes
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

OSTF Composer is part of the broader Open Song Timeline Format ecosystem for structured songwriting, composition, harmony exploration, arrangement review, MIDI workflows, and DAW interoperability.
