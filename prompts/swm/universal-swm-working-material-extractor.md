S-WM RECOVERY SYSTEM · WORKING-MATERIAL LAYER · INTERNAL

# Universal S-WM Working-Material Extractor

**Version:** v2.0g · **Change:** adds the mode layer and ENGINE-ONLY admission control to the parent recovery framework. One law added (law 10, credential redaction); the rest of the preservation laws unchanged.
**Supersedes:** Universal S-WM Working-Material Extractor v1.x
**Kit:** SWM Document Kit v2.1 · **Governed by:** SWM Standing Rules

---

## 00 — Provenance and purpose

*Section function: where this document comes from and what it is for.*

This is the single S-WM recovery framework. It sweeps the entire working-material universe and returns source-preserved evidence. It does not summarize, canonize, resolve, or improve what it finds.

v2.0 adds one thing: a **mode layer** that restricts *what is admitted into the return*, leaving *how material is treated* untouched. ENGINE-ONLY is the first mode defined on that layer. It is not a separate extractor and must never be run as one — a second extractor with its own rules would fork the recovery system and produce two incompatible bodies of evidence.

**Provenance note.** The verbatim text of the parent framework (v1.x) was **[NOT RECOVERED]** at the time of this revision. Sections 01, 02, 06, 07 and 08 below are a **[RECONSTRUCTION]** of the parent from its stated operating spec — full-corpus sweep; preservation of source wording, provenance, chronology, conflicts, gaps, prompts, frameworks, systems and technical material — and not a copy of the original wording. Section 03, 04, 05 and 09 are new in v2.0. When the v1.x source text is recovered, restore its wording in those five sections verbatim and re-apply Sections 03–05 unchanged; the mode layer is designed to bolt on without touching the parent's language.

---

## 01 — Scope: the working-material universe

*Section function: what the sweep is entitled to reach.*

Unless narrowed by the `SCOPE:` parameter, the corpus is **all available S-WM working material**, in every form it exists:

- conversations and conversation threads, including abandoned ones
- documents, drafts, revisions, superseded versions
- PDFs, attachments, exports, spreadsheets, slide material
- notes, scratch material, fragments, message-length asides
- transcripts and meeting records
- prompts, prompt fragments, system instructions, skill definitions
- code, configuration, schemas, logs

A source is in scope whether or not it looks finished, correct, or current. Draft status, staleness and abandonment are recorded as **state**, never used as grounds for exclusion.

**Content separation holds absolutely.** Medical, treatment, crisis and legal-case content is out of scope in every mode: never returned, never quoted, never summarized, never itemized or characterized anywhere in the output. It does not belong to S-WM working material, and its presence in a source does not make that source's other content ineligible.

What this excludes is the content, not the source. A source that contains protected material is still listed in the manifest and the coverage map, and its in-scope content is still swept and returned as normal — dropping the source outright would put a hole in the coverage map and hide the omission. **A source is listed by a non-disclosing identity.** Filenames, titles, subject lines and locators are themselves content: `Jane Doe — cancer treatment plan.pdf` discloses precisely what this section forbids, and listing it as-is would breach the rule in the act of obeying it. Where a source's identity or locator reveals protected material, it is replaced throughout the return — manifest, coverage map, `SOURCE`, `LINKS` — with a stable neutral reference of the form `SOURCE-014 [IDENTITY WITHHELD: SECTION 01]`. Stable, because cross-links and chronology have to keep working; neutral, because the reference must survive being read by anyone. The mapping back to the real source is never written into the return: the operator holds it already. Where the protected material is why a source is only partly swept, the coverage-map reason names the rule and stops there ("PARTIAL — out-of-scope content omitted under Section 01"), because a reason detailed enough to describe what was omitted would leak what the rule exists to keep out.

This section outranks law 1 wherever the two meet — including inside a quotation, where law 1 would otherwise demand the very wording Section 01 forbids. How that omission is performed is stated once, for every rule and every field, under **Removals** at the end of Section 02.

---

## 02 — Standing extraction laws

*Section function: the invariants no mode may alter.*

These apply to every run in every mode. A mode may narrow admission. A mode may never relax a law.

1. **Source preservation.** Return the source's own wording. Quote verbatim. Do not paraphrase, tighten, correct grammar, modernize terminology, or normalize formatting. Where a quotation is cut, mark the cut `[…]`.
2. **Provenance.** Every record names its source, locator and date. A record whose origin cannot be established is tagged **[UNVERIFIED SOURCE]** and returned anyway — never dropped, never silently attributed.
3. **Chronology.** Order is preserved and stated. Where a date is absent, record the position relative to known-dated material and tag **[UNDATED]**.
4. **No canonization.** Do not select a winner, a "current version," or a best formulation. Multiple formulations of the same thing are multiple records.
5. **No conflict resolution.** Contradictions are preserved on both sides, cross-linked, and tagged **[CONFLICT]**. Reconciling them is a separate, later, human decision.
6. **Anti-fabrication.** Never invent facts, figures, sources, names, dates or prior events. Never fill a gap with a plausible value. Gaps are marked with the tags **[MISSING]**, **[NOT RECOVERED]**, **[INFERENCE]**, **[UNVERIFIED SOURCE]**. The tag is the contract and travels in every medium — plain text, Markdown, JSON. Red italic is how the SWM Document Kit renders those tags where the medium carries styling; its absence in an unstyled return is never a reason to omit the tag.
7. **Absence is a finding.** A domain in scope that yields nothing produces a gap-register entry, not silence. An unreachable source produces a coverage-map entry, not silence.
8. **No improvement.** Errors, dead ends, bad naming and known-wrong statements are recovered as they stand. Correction is out of scope for a recovery run.
9. **Naming under standing rules.** Output renders `Marco` (source `Marko` = same person, recorded in the record's source-variant note); SWM = Smart Workforce Movement; Compassionate Package attributed to Clinton Fernandez. Source wording is still quoted verbatim; the normalization applies to the extractor's own prose around it.
10. **Credentials are never reproduced.** Live secret material found in any source — keys, tokens, passwords, connection strings, signing material — is replaced in place with **[REDACTED: CREDENTIAL]**. The surrounding wording is preserved intact, the record's `NOTE` states that a redaction occurred, and the `SOURCE` locator points at the original by a **non-secret reference**. Where the locator itself carries secret material — a token in a URL, a password in a connection string, a signed link — that component is replaced with **[REDACTED: CREDENTIAL]** and the rest of the locator kept precise enough for the operator to retrieve the original directly. A locator is never exempt from this law on the grounds that it is a field rather than a quotation. This is the single, narrow exception to law 1. It covers secret material only: it never extends to content that is merely sensitive, embarrassing, commercial or inconvenient, and it is never used to keep a subject out of mode.

### Removals

Exactly two rules in this framework ever take anything out of a return: **Section 01** (protected content) and **law 10** (credentials). They are stated here once, together, because enumerating them field by field is how a gap gets left behind.

They reach **every record**, in every mode — engine and non-engine, admitted on its own merit or as a conflict counterpart, in `FULL` and in `ENGINE-ONLY` alike — and **every field that can carry content**: `VERBATIM`, `CARRIER CONTEXT`, `SOURCE`, `DOMAIN`, `LINKS`, `NOTE`, the registers, the manifest and the coverage map. A field added to this framework later is covered the day it is added, without amendment.

Both work the same way:

- The offending span is **omitted in place**, never the record and never the source.
- The omission is **marked where it happened** — `[OMITTED: SECTION 01]`, `[IDENTITY WITHHELD: SECTION 01]`, `[REDACTED: CREDENTIAL]` — and noted in `NOTE`.
- Everything around it is **preserved verbatim** under law 1.
- The record is **still returned**, and its conflicts, links and gap entries still stand.

Nothing else removes anything. Not sensitivity, not embarrassment, not commercial awkwardness, not the mode, not the extractor's judgment about what the operator would rather not see. A run that cannot satisfy a law without removing something outside these two rules reports that in the QA attestation (Section 08) and returns anyway.

---

## 03 — The mode layer

*Section function: how a run is narrowed without changing how evidence is treated.*

A mode is an **admission filter on the return**. It answers one question: *which recovered records are handed back?* It has no authority over the sweep, the preservation laws, or the record schema.

| Property | Governed by |
|---|---|
| What is swept | `SCOPE:` — never the mode |
| How material is treated | Section 02 — never the mode |
| What is returned | The mode |

**Sweep first, filter second.** Run the full sweep as defined by `SCOPE:`, then apply the mode at admission. Never narrow the sweep to match the mode: an engine record embedded inside a business-narrative passage is only found by a full sweep, and pre-filtering the corpus would lose it.

### Defined modes

- **`FULL`** *(default)* — everything the sweep recovers is admitted. The v1.x behavior, unchanged.
- **`ENGINE-ONLY`** — admission restricted to the engine domains in Section 04.

A mode never suppresses a **[CONFLICT]**, a gap-register entry, or a coverage-map entry. If an admitted record conflicts with a record the mode would otherwise exclude, the excluded record is admitted as the conflict's other side and marked `ADMITTED: as conflict counterpart`.

---

## 04 — ENGINE-ONLY admission control

*Section function: the boundary of the engine domain.*

### Admit

Fourteen classes. A record is admitted if it is evidence in any one of them.

| # | Class | Admits |
|---|---|---|
| 01 | **OKRAM** | OKRAM AI core: definition, architecture, capability boundaries, behavior, versioning |
| 02 | **SIGNL** | SIGNL system layer: structure, components, interfaces, report mechanics |
| 03 | **Hazel** | Hazel Warden authority layer: authority model, adjudication, voice-as-system-behavior |
| 04 | **OSH** | OSH analysis layer: analytic method, scoring, model behavior, outputs as system artifacts |
| 05 | **Routing** | Request/work routing: dispatch rules, precedence, fallbacks, handoffs between engines and layers |
| 06 | **Schemas** | Data shapes: field definitions, record structures, taxonomies, controlled vocabularies, mappings |
| 07 | **Prompts** | Prompt and instruction material: system prompts, skill definitions, command blocks, prompt fragments and their revisions |
| 08 | **Code** | Source, configuration, scripts, queries, stylesheets, templates as executable/renderable artifacts |
| 09 | **Dependencies** | Libraries, services, models, tools, versions, pins, licensing constraints, and what breaks without them |
| 10 | **Gates** | Named gates (G1, G2, G3, G4 …), sealing decisions, entry/exit criteria, gate status and closure records |
| 11 | **Implementation** | Build decisions, chosen approach, tradeoffs, rejected alternatives, sequencing |
| 12 | **Deployment** | Environments, release mechanics, pipelines, rollout, rollback, configuration-by-environment |
| 13 | **QA** | Test material, checks, QA gates, defects, known bugs, regressions, acceptance criteria |
| 14 | **Systems health** | Reliability, failure modes, incidents, monitoring, capacity, performance, degradation behavior |

**Class 07 note.** Prompt and instruction material is admitted as system evidence, and law 10 governs it: a credential embedded in a prompt is redacted in place, the rest of the prompt is returned verbatim. This framework has no authorization boundary of its own — a run reaches exactly what its operator reaches — so an ENGINE-ONLY return carrying classes 07 or 08 is an internal artifact and is handled as one. Any narrowing beyond that is set at invocation with `ADMISSION:` (Section 05), not improvised mid-run.

### Do not admit

Business narrative and positioning · brand and naming rationale that carries no system behavior · pricing and commercial terms · outreach doctrine and playbooks · client career deliverables and their content · market and employer intelligence · scheduling and administrative traffic · relationship and personnel matters. And, per Section 01, medical/treatment/crisis/legal-case content — excluded absolutely, in every mode.

### Boundary rulings

- **Engine evidence inside a non-engine passage is admitted.** Return the engine content plus the minimum surrounding source wording needed to keep it intelligible, in a `CARRIER CONTEXT` field marked as such. Carrier context is quoted, not summarized, and is never treated as an admitted record itself. **Section 01 takes precedence over this ruling:** carrier context never includes or quotes medical, treatment, crisis or legal-case content. Omit those portions and keep the minimum non-protected surround; where no intelligible surround remains without them, return no carrier context at all and say so in `NOTE`. The engine record itself is still admitted — the exclusion narrows the surround, never the evidence.
- **A named gate is engine evidence even when its subject is commercial.** Gate G4 gating pricing is a gate record; the pricing schedule it gates is a separate record and is not admitted. **Precedence: law 1 wins inside an admitted record.** If a commercial figure or term appears within the gate's own criteria, it is quoted verbatim as part of the gate — a `VERBATIM` field is never trimmed, redacted or paraphrased to keep a subject out of mode, because a criterion you cannot read is not a recovered criterion. `[OUT OF MODE]` marks the excluded neighbouring record and is written in the extractor's own fields (`FLAGS`, `NOTE`), never inside a quotation. Only two rules ever remove text from a `VERBATIM` field: law 10, and Section 01.
- **A deliverable is not admitted; the machinery that produces it is.** A rendered client package is out. Its template, tokens, schema, render pipeline, and QA gate are in.
- **Known-wrong and abandoned engine material is admitted**, with `STATE:` set accordingly. An abandoned architecture is engine evidence.
- **Ambiguity does not resolve itself.** A record that is arguably engine evidence and arguably not goes to the **Held register** (output section F) with a one-line statement of why it is borderline, and is never merged into the admitted body. **One exception, and Section 03 takes precedence over this ruling:** a borderline record that is the other side of an admitted **[CONFLICT]** is admitted, marked `ADMITTED: as conflict counterpart`, and cross-linked in the conflict register — a conflict is never returned with one side sitting in Held. Nothing is silently dropped either way. Deciding a held record is a human call.

---

## 05 — Invocation

*Section function: how a run is commanded.*

```
RUN: S-WM UNIVERSAL EXTRACTION
MODE: ENGINE-ONLY
SCOPE: ALL AVAILABLE S-WM WORKING MATERIAL
CANONIZATION: OFF
CONFLICT RESOLUTION: OFF
SOURCE PRESERVATION: ON
```

| Parameter | Values | Default | Notes |
|---|---|---|---|
| `MODE` | `FULL` · `ENGINE-ONLY` | `FULL` | Admission filter only (Section 03) |
| `SCOPE` | corpus statement | all available S-WM working material | Governs the sweep, never the mode |
| `CANONIZATION` | `OFF` | `OFF` | `ON` is not defined; canonization is a separate downstream operation |
| `CONFLICT RESOLUTION` | `OFF` | `OFF` | `ON` is not defined; see above |
| `SOURCE PRESERVATION` | `ON` | `ON` | `OFF` is not defined and must be refused |
| `ADMISSION` | comma-separated class numbers or names from Section 04 | all 14 | Optional narrowing *within* `ENGINE-ONLY`; e.g. `ADMISSION: 07, 10, 13` |

Refuse and state why if a run asks for `SOURCE PRESERVATION: OFF`, `CANONIZATION: ON`, or `CONFLICT RESOLUTION: ON` — those would convert a recovery run into an authoring run, which this framework does not perform.

---

## 06 — Record schema

*Section function: the shape of one returned unit of evidence.*

```
RECORD ID:        ENG-<domain>-<nnn> for engine material; WM-<nnn> for non-engine
                   material — in FULL mode, and in ENGINE-ONLY for a record
                   admitted as a conflict counterpart
DOMAIN:           <admission class, Section 04; or a descriptive domain label for
                   non-engine material. A counterpart keeps its own true domain —
                   it is never relabelled as engine evidence to fit the return>
ADMITTED:         <present only when a record is in the return by something other
                   than its own admission — currently "as conflict counterpart">
SOURCE:           <artifact name / type / locator>
DATE:             <date, or [UNDATED] + relative position>
STATE:            STATED | PROPOSED | SEALED | SUPERSEDED | ABANDONED | UNCLEAR
VERBATIM:         "<exact source wording, uncorrected, […] for cuts>"
CARRIER CONTEXT:  "<minimum quoted surround, where needed>"
VERIFICATION:     VERIFIED | CONFIRM | RECLASSIFIED | RECON FIRST
FLAGS:            [CONFLICT] [MISSING] [INFERENCE] [UNVERIFIED SOURCE] [UNDATED]
                   [OUT OF MODE] [REDACTED: CREDENTIAL]
                   [IDENTITY WITHHELD: SECTION 01] [OMITTED: SECTION 01]
LINKS:            <related RECORD IDs — conflicts, supersessions, dependencies>
NOTE:             <extractor's own words — locator detail only, never interpretation>
```

`NOTE` is the only field where the extractor writes prose, and it is limited to locating and cross-referencing. Interpretation, judgment and recommendation do not appear anywhere in a recovery run.

---

## 07 — Sweep procedure

*Section function: the order of operations.*

1. **Manifest.** Enumerate every source in `SCOPE:` before reading any of it. Record what exists, what is reachable, what is not.
2. **Sweep.** Read the full corpus. Capture candidate evidence against all of Section 02, regardless of mode.
3. **Chronologize.** Order the swept body; establish relative position for undated material.
4. **Cross-link.** Connect supersessions, dependencies and contradictions across everything swept. Tag **[CONFLICT]** both ways. **This happens before admission, not after:** a conflict whose other side has already been filtered out cannot be detected, so a mode applied first would hide the very contradictions Section 03 requires it to preserve.
5. **Admit.** Apply the mode (Section 03/04) to the cross-linked body. Route borderline items to Held; admit conflict counterparts per Section 03, whatever their domain.
6. **Register gaps.** Every in-scope domain with zero yield, every unreachable source, every unresolved locator.
7. **QA gate.** Section 08.
8. **Return.** Section 08 output order.

## 08 — Output contract and QA gate

*Section function: what comes back, and what is checked before it does.*

Return in this order:

- **A · Run header** — mode, scope, parameters as invoked, run date
- **B · Coverage map** — source → SWEPT / PARTIAL / UNREACHABLE, with reason for anything not fully swept
- **C · Admitted records** — grouped by domain, chronological within domain
- **D · Conflict register** — each conflict, both sides, cross-linked record IDs, unresolved by design
- **E · Gap register** — [NOT RECOVERED] / [MISSING] entries, including empty domains
- **F · Held register** — borderline admissions, each with its one-line reason
- **G · QA attestation** — the six checks below, each stated pass or fail

Six checks, evaluated and reported on every run. The attestation states each one pass or fail, and the run returns its evidence either way: a failed check is a disclosed defect in the return, never grounds for withholding it.

1. **Preservation check** — every `VERBATIM` is source wording, with no paraphrase in the field, and nothing removed from one but a law-10 redaction or a Section 01 omission
2. **Removal-coverage check** — sweep **every content-bearing field in the whole return** — `VERBATIM`, `CARRIER CONTEXT`, `SOURCE`, `DOMAIN`, `LINKS`, `NOTE`, the conflict, gap and Held registers, the manifest and the coverage map — and confirm that nothing removable under **Removals** survives anywhere in it, and that every removal actually made is marked in place and noted. A gate that inspects only quotations cannot see the leaks that rule exists to prevent: a credential in a locator or a name in a coverage-map row passes a `VERBATIM`-only check untouched
3. **Provenance check** — every record carries source and date, or carries the tag explaining why it cannot
4. **Anti-fabrication sweep** — no invented value anywhere; every gap explicitly marked
5. **Non-resolution check** — no conflict silently reconciled, no version silently elected
6. **Mode-integrity check** — exclusions are admission-only; no record was excluded on grounds a law reserves (draft status, staleness, apparent wrongness), and no conflict counterpart or gap entry was suppressed by the mode

A failed check names what is wrong and what it affects. It does not license a fix that would violate a law, and it does not license silence.

## 09 — Change log

| Version | Change |
|---|---|
| v2.0g | Seventh review pass. Added QA check 2, removal coverage: the generalized **Removals** rule reaches every content-bearing field, but the gate still inspected only `VERBATIM`, so a run could report pass with a credential in a locator or protected content in a coverage-map row. The gate now sweeps the whole return. Checks renumbered five to six. |
| v2.0f | Sixth review pass. Replaced the per-field omission statements with a single **Removals** rule at the end of Section 02: the two removal rules are stated once and reach every record in every mode and every field that can carry content, including fields added later. The previous wording covered only an engine record's own quotation, leaving non-engine records in FULL mode and admitted conflict counterparts facing the same law 1 / Section 01 clash the v2.0e fix set out to close. |
| v2.0e | Fifth review pass. Sweep order corrected: cross-linking now runs before admission, so a conflict counterpart is still present to be admitted (previously the mode filtered one side out at step 3 and conflicts were only detected at step 5). Schema now gives non-engine conflict counterparts a legal `WM-` id, their own true domain, and an `ADMITTED` field, instead of forcing them into an engine class. Section 01 given precedence over law 1 inside `VERBATIM`, resolving a case the framework could not previously satisfy. |
| v2.0d | Fourth review pass. Closed the identity leak introduced by v2.0c: a source whose filename, title, subject or locator discloses protected content is now listed under a stable neutral reference (`SOURCE-nn [IDENTITY WITHHELD: SECTION 01]`) used consistently across manifest, coverage map, `SOURCE` and `LINKS`, with the mapping never written into the return. |
| v2.0c | Third review pass. Section 01 clarified: the exclusion covers protected content, not the sources carrying it — such a source still appears in the manifest and coverage map, with the omission reason naming the rule and no more. Law 6 now makes the bracketed tag the contract and red italic the Document Kit rendering convention, so the marker survives plain-text, Markdown and JSON returns. |
| v2.0b | Second review pass. Law 10 extended to credential-bearing `SOURCE` locators (redact the secret component, keep the locator retrievable). Section 01 given precedence over the carrier-context ruling, so protected content is never quoted as surround. QA gate reworded from all-must-pass to evaluated-and-reported, which no longer contradicts the rule that a failed check is disclosed. |
| v2.0a | Review pass. Added law 10 (credentials redacted in place, the one exception to law 1) and the class 07 note. Stated precedence on the commercial-gate ruling (law 1 wins inside an admitted record; `[OUT OF MODE]` never cuts a quotation) and on Held vs. conflict counterparts (Section 03 wins; a conflict is never returned one-sided). `DOMAIN` now accepts a descriptive label for non-engine records in FULL mode. |
| v2.0 | Added Section 03 (mode layer), Section 04 (ENGINE-ONLY admission control), Section 05 (invocation, `MODE`/`ADMISSION` parameters), Section 09. Added mode-integrity as QA check 5; added Held register as output section F. Preservation laws, record schema and sweep procedure carried forward unchanged in substance. Parent v1.x verbatim text **[NOT RECOVERED]** — Sections 01, 02, 06, 07, 08 are a reconstruction from spec. |

---

Prepared by: Clinton Fernandez · AF.Style Holdings LLC
Governed by Personal Cognitive Charter v1.1
