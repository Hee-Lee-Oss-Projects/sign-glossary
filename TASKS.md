# TASKS — sign-glossary

> Status: Draft · Version: 0.1.0 · Last updated: 2026-06-28 · Owner: TBD (maintainer) · Lane: donated

Backlog for the `sign-glossary` good-deed project. Read alongside `PLAN.md` (same directory).

## How these tasks map to Hee-Lee Oss

Every task here becomes a **Task JSON** validated by `packages/schema/src/schemas.ts`. Field mapping:

- `id` — stable, e.g. `sign-glossary-consent-001` (the table's ID column).
- `title` — the task title.
- `project` — `"sign-glossary"` for all tasks.
- `type` — one of `code | research | writing | data | design-spec | maintenance` (per task).
- `lane` — `"donated"` for all tasks (the human runs their own agent; signers/reviewers are human;
  the CLI preps workspace + PR and never runs an agent headless). No `funded` tasks in this backlog,
  so `fundedBudgetUsd` is not required.
- `priority` — `high | medium | low`.
- `domain` — array, e.g. `["accessibility","deaf-community","language","open-culture"]`.
- `riskTier` — `low | medium | high`. **medium** for entry capture/review (sign accuracy);
  **high** for any health/legal/safety term (Deaf **and** credentialed domain-expert sign-off).
- `urgent` — boolean (default `false`; nothing here is time-critical).
- `deliverable` — `pr | dataset | document | translation`. Published entries/media → `dataset`
  (or `pr` to the open dataset repo / lexeme host); records & ledgers → `dataset`; guides, consent
  framework, policies, rubrics → `document`. (Sign entries are content, not natural-language
  `translation`, so `dataset`/`pr` is the honest mapping.)
- `tokenEstimate` — `small | medium | large` (the table's Size column).
- `status` — `open | in-progress | review | delivered | done` (all start `open`).
- `context`, `objective`, `acceptanceCriteria[]`, `resources[]`, `output` — task body fields.
- `requestor` — proposer/maintainer until a Deaf-led partner is named.
- `verifiedNeed` — **`false`** for all capture/publish/co-design tasks until a Deaf-led partner +
  reviewers are secured for a named language/region (see PLAN "partner & Deaf-leadership gate");
  **`true`** only for self-evident, partner-independent artifacts (style guide, consent framework,
  schema, license-rules research).
- `outputLicense` — **MIT** for code/tooling; **CC-BY-4.0** (or CC-BY-SA-4.0 / CC0-1.0 as the partner
  decides) for content, guides, and published entries.

At production scale this project fans out: **one term × one named sign language/region = one entry =
one task**, drawn from a co-designed, milestone-scoped batch. The `*-capture-*` / `*-batch-*` tasks
below are the templates for that fan-out.

---

## Milestone M0 — Foundation, Deaf leadership & cold-start

Prove one entry can travel from a consenting Deaf signer to *published, open, Deaf-approved, and live*
— with a working takedown path — before anything scales. **Deaf leadership is a hard gate.**

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| sign-glossary-partner-001 | Secure a Deaf-led partner + fluent-Deaf reviewers; pick language/region; co-design term list | research | medium | medium | document | — | Maintainer + Deaf lead |
| sign-glossary-consent-001 | Author consent framework v1 (release, attribution, revocation/takedown SLA, consent-record schema) | writing | medium | medium | document | — | Maintainer + Consent steward |
| sign-glossary-style-001 | Author entry & notation style guide v1 + cultural-norms section | writing | medium | medium | document | partner-001 (norms input) | Deaf reviewer |
| sign-glossary-review-001 | Author Deaf-review rubric v1 (4 dimensions) + error taxonomy + credential register | writing | small | medium | document | style-001 | Deaf reviewer |
| sign-glossary-data-001 | Define per-entry record + consent record + license/provenance formats | data | small | low | dataset | style-001, consent-001 | Maintainer |
| sign-glossary-research-001 | Validate license + consent + open-host rules for chosen sources/host | research | small | medium | document | partner-001 | Steward |
| sign-glossary-capture-001 | Capture + Deaf-review ≈10 co-designed entries (everyday/edu; ≥1 polysemous, ≥1 regional variant, ≥1 video, ≥1 illustration; no high-stakes) | data | medium | medium | dataset | partner-001, consent-001, style-001, review-001, data-001, research-001 | Deaf reviewer |
| sign-glossary-publish-001 | Publish the ≈10 entries live & openly + run a revocation drill + measure baseline coverage | maintenance | medium | medium | pr | capture-001, research-001 | Steward + Consent steward |

**Sequencing — Deaf leadership is a hard gate.** `partner-001` blocks `capture-001` and
`publish-001`: no signer is filmed and no entry is published until a Deaf-led partner + fluent-Deaf
reviewers are confirmed and a term list is co-designed. **Kill/pivot:** if the time-boxed effort
secures no Deaf-led partner, the project pivots to the next candidate community/language or stops — it
does **not** proceed hearing-led, and never films signers without a consent + review path in place.

**Key task acceptance criteria**

- **sign-glossary-partner-001** (secure Deaf leadership)
  - [ ] Identifies and confirms ≥1 Deaf-led partner or community group for a *named* sign language +
        region, with fluent-Deaf review capacity (≥1 reviewer, target ≥2).
  - [ ] Co-designs an initial target term set with the partner (the coverage denominator).
  - [ ] Confirms the partner's preferred content license (CC-BY-4.0 / CC-BY-SA-4.0 / CC0-1.0) and any
        cultural norms (name-signs, forms to avoid).
  - [ ] States the time-box and the kill/pivot criteria if no Deaf-led partner is secured.
  - [ ] On success, flips `verifiedNeed=true` for capture/publish tasks scoped to that language/region.

- **sign-glossary-consent-001** (consent framework v1)
  - [ ] Provides an informed-consent script + likeness/publication release covering open-license
        publication, with attribution preference capture (name | handle | anonymous).
  - [ ] Discloses honestly that open-license (CC) publication is, for copyright, irrevocable and that
        downstream copies cannot be recalled — while committing to honour withdrawal from our
        distribution.
  - [ ] Defines a **revocation/takedown workflow + SLA** (target ≤ 7 days) and the `takedownState`
        lifecycle.
  - [ ] Specifies minor-contributor safeguards (guardian consent + extra protections) or exclusion.
  - [ ] Defines the consent-record schema; published, versioned, licensed CC-BY-4.0.

- **sign-glossary-capture-001** (cold-start batch ≈10)
  - [ ] Batch is co-designed and spread across paths: several everyday/education terms, ≥1
        **polysemous** term (multiple senses/signs), ≥1 term with a known **regional variant**,
        ≥1 **video** and ≥1 **illustration**, and **zero** high-stakes terms.
  - [ ] Every entry has a valid, in-scope, recorded consent **before** any recording is stored.
  - [ ] Each entry conforms to style guide v1 (lemma, sense disambiguation, definition, optional
        notation, regional-variant labelling, recording/illustration quality bar).
  - [ ] Each entry is scored on the 4-dimension Deaf-review rubric by a fluent Deaf reviewer; nothing
        below 3/4 on any dimension is kept; failures tagged by the error taxonomy.
  - [ ] No AI-generated/synthesised signs; AI used only for metadata scaffolding.
  - [ ] No bystanders/identifying background; sensitive metadata minimised.

- **sign-glossary-publish-001** (publish + revocation drill + baseline)
  - [ ] ≥10 entries published live and openly accessible (open license + media format), each with
        license + attribution + consent ref + provenance; additive, no silent overwrite.
  - [ ] The published entry pages are themselves accessible (captions/text alternative, contrast,
        keyboard navigation).
  - [ ] A **revocation drill** is executed end-to-end on a test/volunteer entry: withdrawal honoured
        within SLA, entry marked `withdrawn` and removed from distribution.
  - [ ] Baseline coverage measured against the co-designed term set (named snapshot + date +
        denominator), so later deltas are comparable.

**M0 Definition of Done:** Deaf-led partner + reviewers confirmed for a named language/region; term
list co-designed; consent framework, style guide, and review rubric v1 published; ≥10 entries
Deaf-approved, consented, and published live & openly with full provenance; revocation drill passed;
baseline coverage measured; zero consent or license violations.

---

## Milestone M1 — Pipeline, tooling & repeatability

Turn the manual slice into a repeatable, consent-safe, policy-compliant pipeline.

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| sign-glossary-adapter-001 | Open-dataset publication adapter (metadata + media + checksum + provenance) | code | large | medium | pr | research-001, data-001 | Maintainer |
| sign-glossary-pipeline-001 | Consent ledger + revocation/takedown workflow with SLA tracking | code | large | high | pr | consent-001, data-001 | Consent steward |
| sign-glossary-pipeline-002 | Domain/risk classifier (route health/legal/safety → expert gate, fail-safe) | code | medium | medium | pr | data-001 | Maintainer |
| sign-glossary-pipeline-003 | Dedup + variant check + claim/locking (preserve variants, prevent double-work) | code | medium | medium | pr | data-001 | Maintainer |
| sign-glossary-doc-001 | Deaf-review workflow doc + reviewer onboarding + credential register | writing | small | medium | document | review-001 | Deaf reviewer |
| sign-glossary-batch-001 | Capture + review + publish batch of ≈100 (first repeatable run) | data | large | medium | pr | adapter-001, pipeline-001, pipeline-002, pipeline-003, doc-001 | Deaf reviewer rotation |

**Key task acceptance criteria**

- **sign-glossary-pipeline-001** (consent ledger + revocation — high risk: it governs publication
  rights and personal/biometric data)
  - [ ] Records consent per contributor (scope, attribution preference, license ack, granted-at/by,
        minor safeguards) and links it to each entry's `consentRef`.
  - [ ] No entry can be marked publishable without a valid, in-scope consent record (enforced, not
        advisory).
  - [ ] Revocation request propagates to takedown within SLA; entry marked `withdrawn` and removed
        from distribution; downstream-copy limit recorded honestly.
  - [ ] No secrets/tokens in logs; pre-publication media access-controlled; SLA adherence tracked.

- **sign-glossary-adapter-001** (open-dataset publication adapter)
  - [ ] Publishes approved entry metadata + media to the open host with license + attribution +
        consent ref + provenance + checksum; open/royalty-free media format.
  - [ ] Additive/non-destructive: never silently overwrites a community's existing entry; detects
        conflicts and re-fetches rather than clobbering.
  - [ ] Honours host policy/rate limits; tokens from the human's environment, never logged/committed.

- **sign-glossary-pipeline-002** (domain/risk classifier)
  - [ ] Classifies term domain; routes health/legal/safety → high-risk expert + Deaf gate.
  - [ ] Fail-safe: low-confidence "maybe high-stakes" still routes to the gate (never publishes a
        high-stakes term unseen); required "not advice / not a substitute for an interpreter" label
        attached.

- **sign-glossary-batch-001** (first ≈100 run)
  - [ ] ≥100 entries published live; approval rate and reviewer-corrected rate measured.
  - [ ] All went through consent gate → classifier → Deaf review → adapter publication.
  - [ ] Variants preserved (not collapsed); zero consent/license violations.

**M1 Definition of Done:** publication adapter live and policy-compliant; consent ledger + revocation
workflow operational with SLA tracking; classifier + dedup/variant/locking operational; Deaf-review
workflow documented with ≥2 reviewers onboarded; ≥100 entries published with measured approval rate;
zero consent or license violations.

---

## Milestone M2 — Controlled scale (one language, deep) + beneficiary validation

Meaningfully move coverage in one language/region with quality held, and validate with users.

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| sign-glossary-batch-002 | Scale to ≥300 entries in the named language/region | data | large | medium | pr | batch-001 | Deaf reviewer rotation |
| sign-glossary-highstakes-001 | Pilot high-stakes term set (health/safety) with dual Deaf + expert sign-off + label | data | medium | high | dataset | pipeline-002, batch-001 | Domain expert + Deaf reviewer |
| sign-glossary-research-002 | Beneficiary validation (Deaf users / learners / parent of a deaf child) | research | small | low | document | batch-001 | Maintainer |
| sign-glossary-data-002 | Quality metrics dashboard (approval, corrected, inter-reviewer agreement, taxonomy mix, takedown SLA) | data | small | low | dataset | batch-001 | Maintainer |

**Key task acceptance criteria**

- **sign-glossary-batch-002** (scale run)
  - [ ] ≥300 entries published live in the named language/region.
  - [ ] Approval rate ≥80%; reviewer-corrected rate ≤25% and trending down; inter-reviewer
        agreement ≥0.7 on the double-reviewed sample.
  - [ ] Zero consent/license violations; 100% takedown-SLA adherence on any requests.

- **sign-glossary-highstakes-001** (high-stakes pilot)
  - [ ] Every entry has **both** fluent-Deaf review and credentialed domain-expert sign-off before
        publication; otherwise not published.
  - [ ] Carries the "not advice / not a substitute for a qualified interpreter" label; credentials
        recorded in provenance.

- **sign-glossary-research-002** (beneficiary validation)
  - [ ] ≥1 validation per ~100 entries by Deaf users / learners / a parent of a deaf child confirming
        accuracy and usability.
  - [ ] Findings feed back into the style guide / review rubric.

**M2 Definition of Done:** ≥300 entries live in one language/region at ≥80% approval; ≥1 beneficiary
validation per ~100 entries; high-stakes pilot delivered with dual sign-off + label (or explicitly
deferred); quality metrics dashboarded; zero consent/license violations; 100% takedown-SLA adherence.

---

## Milestone M3 — Broaden & sustain (second community, durable ops)

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| sign-glossary-partner-002 | Secure a second Deaf-led partner + reviewers for a new language/region | research | medium | medium | document | — | Maintainer + Deaf lead |
| sign-glossary-batch-003 | Cold-start + scale entries in the second language/region | data | large | medium | pr | partner-002, adapter-001 | Deaf reviewer rotation (2nd) |
| sign-glossary-pipeline-004 | Outcome dashboard (published/live, approval, coverage, takedown SLA per language) | code | medium | low | pr | data-002 | Maintainer |
| sign-glossary-maint-001 | Maintenance + community handover + durable takedown path | maintenance | medium | medium | document | pipeline-001, adapter-001 | Maintainer + Consent steward |

**M3 Definition of Done:** ≥1 additional language/region onboarded with its own Deaf-led partner +
reviewers; outcome dashboard maintained across languages; maintainer + Deaf-reviewer rotation
documented; community ownership/handover and durable (post-push) takedown path in effect.

---

## Backlog / future (sized, unscheduled)

| ID | Title | Type | Size | Risk | Deliverable | Notes |
|---|---|---|---|---|---|---|
| sign-glossary-adapter-002 | Wikidata lexeme / open-lexicon contribution adapter | code | large | medium | pr | Only where the community agrees; host-policy pre-engagement |
| sign-glossary-doc-002 | Notation guide (gloss / HamNoSys / SignWriting) per community preference | writing | medium | low | document | Expand style guide; notation optional per entry |
| sign-glossary-pipeline-005 | Self-accessibility audit tooling for the glossary site (captions/contrast/keyboard) | code | medium | low | pr | The resource must itself be accessible |
| sign-glossary-research-003 | High-stakes credential-bar + expert-recruitment policy (health/legal/safety) | research | small | high | document | Defines who can clear the high-risk gate |
| sign-glossary-data-003 | Regional-variant coverage tracker (don't erase variation) | data | small | low | dataset | Sustainability/equity metric |
| sign-glossary-maint-002 | Adapter/policy maintenance vs host + community changes | maintenance | medium | low | pr | Ongoing post-delivery |

---

## Example task JSON

Complete, schema-valid Task JSON for the first M0 task. `verifiedNeed` is **`false`**: securing a
Deaf-led partner is exactly the thing not yet in place, so the need cannot be honestly marked
verified until this task (and the partner gate) succeeds. `lane` is `donated`, so `fundedBudgetUsd`
is not required.

```json
{
  "id": "sign-glossary-partner-001",
  "title": "Secure a Deaf-led partner + fluent-Deaf reviewers; pick language/region; co-design term list",
  "project": "sign-glossary",
  "type": "research",
  "lane": "donated",
  "priority": "high",
  "domain": ["accessibility", "deaf-community", "language", "open-culture"],
  "riskTier": "medium",
  "urgent": false,
  "deliverable": "document",
  "tokenEstimate": "medium",
  "status": "open",
  "context": "sign-glossary aims to publish an open, Deaf-reviewed glossary of signs for key terms in a named sign language and region. Sign languages are distinct languages with regional variation, and the project's first principle is Deaf leadership ('nothing about us without us'): signs must be created and approved by the Deaf community that uses the language, never produced about them by hearing or non-signing contributors. No Deaf-led partner, sign language, region, or term list has been secured yet, so this task is a blocking prerequisite for all capture and publication work.",
  "objective": "Confirm a Deaf-led partner organisation or community group, with fluent-Deaf review capacity, for one named sign language and region, and co-design an initial target term set, content-license choice, and cultural norms with them.",
  "acceptanceCriteria": [
    "Identifies and confirms at least one Deaf-led partner/community group for a NAMED sign language and region, with fluent-Deaf review capacity (>=1 reviewer, target >=2).",
    "Co-designs an initial target term set with the partner to serve as the coverage denominator.",
    "Confirms the partner's preferred content license (CC-BY-4.0, CC-BY-SA-4.0, or CC0-1.0) and documents cultural norms (e.g., name-signs, forms to avoid).",
    "States the time-box and explicit kill/pivot criteria if no Deaf-led partner is secured (pivot to next candidate community/language, or stop; never proceed hearing-led).",
    "On success, records that capture/publish tasks scoped to this language/region may flip verifiedNeed to true."
  ],
  "resources": [
    "C:\\code\\hee-lee-oss\\planning\\projects\\sign-glossary\\PLAN.md",
    "C:\\code\\hee-lee-oss\\docs\\good-deed-definition.md",
    "C:\\code\\hee-lee-oss\\CLAUDE.md",
    "Principle: 'Nothing About Us Without Us' (disability self-determination)"
  ],
  "output": "A partnership & scope document naming the Deaf-led partner, the sign language + region, the fluent-Deaf reviewers and their credential basis, the co-designed initial term set, the chosen content license, documented cultural norms, and the time-box + kill/pivot criteria.",
  "requestor": "jdev1977",
  "verifiedNeed": false,
  "outputLicense": "CC-BY-4.0"
}
```
