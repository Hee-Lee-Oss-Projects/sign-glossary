# PLAN — sign-glossary

> Status: Draft · Version: 0.1.0 · Last updated: 2026-06-28 · Owner: TBD (maintainer) · Lane: donated

> **Positioning:** An open, **Deaf-led** glossary of signs for key terms — where every sign is
> performed by a real, consenting signer, reviewed and approved by fluent Deaf signers, attributed
> to its contributor, and released under an open license. Accuracy is guaranteed by the Deaf
> community that *uses* the language, never by an algorithm. *Nothing about us without us.*

---

## Executive summary

For most of the world's [sign languages](#references), there is no free, openly-licensed,
trustworthy reference for how to sign "key terms" — the words a person actually needs to
participate in school, a clinic visit, a civic process, an emergency, or daily life. What exists is
fragmented: paywalled apps, single-creator YouTube videos of uneven accuracy, academic lexical
databases under restrictive or unclear licenses, and proprietary dictionaries that cannot be
legally reused, remixed, or built upon. The gap falls hardest on the people with the greatest need:
**hearing parents of deaf children** racing to give their child a first language, **new signers and
learners**, **deaf people navigating services in a second language**, and **educators and
interpreters** working without an open shared reference.

`sign-glossary` turns this gap into a stream of small, reviewable, **consent-first** good deeds:
**one term in one sign language = one entry**. A consenting Deaf signer performs the sign on video
(or a Deaf illustrator draws it); the entry is captured with written-language definitions,
disambiguated senses, optional notation (gloss / HamNoSys / SignWriting), full attribution, and a
recorded **likeness-and-publication consent**; a **fluent Deaf reviewer approves the sign's
accuracy**; and the entry is published to a durable, openly-licensed, openly-accessible host.
Success is not "videos recorded" — it is **entries that are Deaf-reviewed, consented, published
live, freely reusable, and confirmed useful by the community that needs them.**

The AI's role is deliberately bounded. **AI sessions never invent, synthesize, or "perform" a
sign.** A sign comes only from a real, consenting human signer (or a Deaf illustrator). AI does the
scaffolding that lets the human work go faster and stay consistent: drafting entry metadata and
written-language definitions, proposing gloss/notation, organising senses, transcribing,
cross-referencing, deduplicating, and building tooling. The linguistic authority is always a Deaf
human; the AI is support staff.

The work is **medium risk**, with two domain-specific hazards beyond ordinary content accuracy.
(1) **A wrong sign is misinformation** — and for health/legal/safety terms it can cause real harm,
so those domains escalate to **high risk** (Deaf review *and* credentialed domain-expert review,
plus a "not a substitute for a qualified interpreter" label). (2) **Sign video is biometric,
identifying personal data of a real person** — so **informed, revocable consent is a hard gate**,
and a working **takedown/revocation path** is a launch requirement, not a future nicety. The third
hard guardrail is **licensing/provenance**: only content the contributor is entitled to release
openly is ever published, license + attribution + provenance + consent are recorded per entry, and
**existing third-party sign media is never scraped or repurposed** without both a clear open license
*and* performer consent.

This document is honest about what is not yet in place. **No Deaf-led partner organisation is
secured, no specific sign language and region have been chosen, and no term list has been
co-designed with a community.** Because Deaf leadership is non-negotiable for this project, those
are not details to fill in later — they **gate** all capture and publication work. M0 is a thin,
manual, Deaf-led, end-to-end slice that must prove a single entry can travel from a consenting
signer to *published, openly licensed, Deaf-approved, and live* before anything scales.

## Problem & beneficiaries

**Who is helped (primary beneficiaries):**

- **Hearing parents and families of deaf children.** ~90–95% of deaf children are born to hearing
  parents who do not already sign. Early, accurate access to sign vocabulary is decisive for the
  child's language development. A free, trustworthy glossary of everyday and educational terms is a
  high-leverage, time-sensitive need for this group.
- **New signers and learners** (including deaf and hard-of-hearing people learning their community's
  sign language, and second-language learners) who today rely on uneven, paywalled, or unverified
  sources.
- **Deaf and hard-of-hearing people navigating services** (education, healthcare, civic life,
  emergencies) where shared, agreed signs for key terms reduce miscommunication.
- **Educators, teaching assistants, and trainee interpreters** who need an open, citable, reusable
  reference rather than copyright-restricted dictionaries.

**Secondary beneficiaries:**

- The **sign-language open-knowledge commons** — researchers, lexicographers, app builders, and
  Wikimedia/Wikidata lexeme efforts — who gain an openly-licensed, provenance-tracked, consented
  corpus to build on legally.
- **Deaf contributors themselves**, who are visibly credited (attribution-always) and retain agency
  over their likeness (revocable consent).

**The verified need.** The *underlying* need is well established and not in dispute: the large
majority of the world's sign languages are under-documented, and openly-licensed, community-verified
sign references are scarce; the parent-of-deaf-child language-access gap is widely documented. On
that basis, the *category* need is real.

**The partner gap and the Deaf-leadership gate (honest, and central).** A documented category need
is **not** a license to start filming. This project's first ethical principle is **Deaf leadership**:
signs must be created and approved by the Deaf community that uses the language, not produced *about*
them by hearing or non-signing contributors. Today:

- **No Deaf-led partner organisation has been secured** (e.g., a national/regional Deaf association,
  a Deaf school, a Deaf studies department, or a Deaf-run community group).
- **No specific sign language and region have been chosen** (sign languages are distinct languages —
  ASL, BSL, Auslan, LSF, Irish Sign Language, etc. — and each has regional variation; this project
  scopes to *one named language + region* at a time).
- **No term list has been co-designed** with the beneficiary community.

**Partner / requestor: TO BE SECURED.** Until a Deaf-led partner and a fluent-Deaf review capacity
are confirmed for a specific language and region, every capture/publication task carries
`verifiedNeed = false`, and M0 treats *securing Deaf leadership* as a blocking exit criterion. If no
Deaf-led partner can be secured, the project does **not** proceed to capture — it pivots to the next
candidate community or stops. We will not produce a hearing-led sign glossary.

## Goals and non-goals

**Goals**

- Publish accurate, Deaf-reviewed, openly-licensed entries for key terms in a named sign language and
  region, each with disambiguated senses and clear written-language definitions.
- Make Deaf review the **accuracy authority** for every entry, and make it scale via a documented
  rubric, reviewer rotation, and a self-contained per-entry task unit.
- Obtain and honour **informed, revocable consent** for every signer's likeness, with a working
  takedown path, and **always attribute** contributors.
- Publish to a **durable, openly-accessible, openly-licensed** host so entries are freely reusable
  and survive the project.
- Measurably increase coverage of a co-designed target term set, with regional variants represented.

**Non-goals (constraints that define the project — see also §5, §8)**

- **Not** AI-generated or avatar-synthesised signs. Signs come from real, consenting human signers
  (or Deaf-drawn illustrations) and are Deaf-reviewed. *We do not ship synthetic signing avatars.*
- **Not** treating sign language as universal. Every entry is scoped to a *named* sign language and
  region; no entry claims to be "the" sign for a term across languages.
- **Not** hearing-led. Hearing or non-signing contributors may assist with scaffolding (metadata,
  definitions, tooling) but are **never** the final authority on a sign's correctness.
- **Not** publishing anyone's likeness without informed, revocable consent — even for an otherwise
  openly-licensed recording.
- **Not** professional interpretation, nor medical/legal/safety advice. High-stakes terms are
  expert-reviewed, labelled "not a substitute for a qualified interpreter / not advice," and never
  positioned as a replacement for a real interpreter.
- **Not** scraping or repurposing third-party sign videos. Existing media is used only with both a
  clear open license *and* documented performer consent.
- **Not** surveillance, biometric identification, or any reuse of signer video beyond the consented
  glossary purpose.
- **Not** a hosted SaaS, an "upload any sign" service, or a translation/interpreting product.

## Success metrics (outcomes)

Outcome-based and beneficiary-centric. Vanity counts ("videos recorded") are explicitly **not** the
headline; **Deaf-approved, consented, published-live, and confirmed-useful** is.

| Metric | Baseline | Target (first 2 quarters post-M0) |
|---|---|---|
| Entries **Deaf-reviewed, consented, published live & openly accessible** | 0 | ≥ 300 in one named sign language/region |
| **Deaf-review approval rate** (approved ÷ submitted for review) | n/a | ≥ 80% (signals quality, not volume) |
| **Reviewer-corrected / re-record rate** (entries needing fixes before approval) | n/a | ≤ 25%, trending down |
| **Inter-reviewer agreement** on a double-reviewed sample (e.g. Cohen's κ or % exact-match on the rubric) | n/a | ≥ 0.7; recalibrate rubric if below |
| **Consent integrity** (published videos with a valid, recorded, in-scope consent) | n/a | **100%** (hard gate; any gap is a stop-the-line incident) |
| **Takedown/revocation honoured within SLA** | n/a | **100%** within the published SLA (target ≤ 7 days) |
| **Community accuracy challenges** post-publication (entries flagged wrong by the community) | n/a | tracked; resolved within SLA; trending toward 0 |
| **License-compliance violations** (non-open or non-consented media published) | 0 | **0** (hard gate) |
| **High-stakes entries (health/legal/safety) with both Deaf + domain-expert sign-off** | 0 | 100% before publication (or not published) |
| **Coverage of the co-designed target term set** | measured at M0 | +X percentage points (set once baseline known) |
| **Regional-variant representation** (terms with ≥1 recorded regional variant where one exists) | n/a | tracked; not erasing variation |
| Beneficiary validation (Deaf users / learners / a parent confirm a batch is accurate & usable) | none | ≥ 1 qualitative review per ~100 entries |

**Accuracy rubric (replaces a binary "Deaf review passed").** Every entry is scored 1–4 by a fluent
Deaf reviewer on four independent dimensions:

1. **Sign accuracy** — the sign shown is a correct, current sign for the intended sense in the named
   language/region (not invented, not borrowed from another sign language, not archaic-by-accident).
2. **Sense fidelity** — the written-language term, definition, and sense disambiguation match what
   the sign actually means (no false-friend mismatches).
3. **Production clarity** — the recording/illustration is clear, complete (full sign, correct
   framing, adequate lighting/contrast), and re-usable.
4. **Cultural appropriateness** — respectful, non-offensive, and consistent with community norms
   (e.g., correct handling of name-signs, no outdated/pejorative forms presented as neutral).

Nothing is published below **3/4 on any dimension**. Each correction/rejection is tagged with an
**error taxonomy** (wrong sign · wrong/ambiguous sense · poor production · culturally inappropriate ·
regional-variant mislabelled) so the failure mix tunes the style guide and reviewer training.

**Counting "coverage" (reproducible).** Coverage is `published-and-approved ÷ target-term-set` for a
named term list snapshot at a recorded date, in a named language/region. The denominator is the
co-designed target term set; "covered" means ≥ 1 approved, consented, live entry for that sense.
Baseline and every delta use the same snapshot definition so they are comparable over time.

Note: percentage-point coverage targets are deferred until M0 measures a real baseline against the
co-designed term set — inventing one now would be dishonest.

## Scope

**In scope**

- Openly-licensed **video** sign entries from consenting Deaf signers, and **Deaf-drawn
  illustrated** entries, for key terms in a *named* sign language and region.
- Per-entry written-language lemma + definition + **sense disambiguation**, optional notation
  (gloss / HamNoSys / SignWriting), and regional-variant labelling.
- Per-entry **consent record** (likeness/publication), **attribution**, license, and provenance.
- A **Deaf-led review workflow** with an accuracy rubric and reviewer rotation.
- A **revocation / takedown workflow** with a published SLA.
- An open, durable publication channel (open dataset + media on an open-licensed, accessible host).
- A published, versioned **entry & notation style guide** and **consent/attribution policy**.

**Out of scope**

- AI-generated, motion-captured, or avatar-synthesised signs (hard exclusion).
- Treating one language's sign as valid for another language (no cross-language "universal" claims).
- Scraping, mirroring, or repurposing third-party sign videos without open license **and** consent.
- Real-time interpreting, translation, or any "sign this sentence" generative product.
- Professional medical/legal/safety interpretation or advice (high-stakes terms are gated, labelled,
  and expert-reviewed — never positioned as a substitute for a qualified interpreter).
- Biometric identification, face-recognition, or any reuse of signer video beyond the glossary.
- Hosting a public upload service or user-generated-content platform.
- Full lexicographic completeness of a sign language (we cover a co-designed *key-terms* set, not the
  whole lexicon).

## Solution approach & architecture

This is a **content/data pipeline** project with supporting **adapter/tooling code**, run in the
**donated lane**: a human runs their own agent interactively to draft scaffolding (metadata,
definitions, notation, tooling); Deaf signers perform/illustrate the signs; Deaf reviewers approve;
Hee-Lee Oss prepares the per-entry task workspace and opens the publication PR. **The CLI never invokes or
authenticates a coding agent and never runs headless**, and **no AI session ever produces a sign.**

**Pipeline (per entry)**

1. **Term selection (co-designed).** Pull a term + intended sense from the *co-designed* target term
   set for the named language/region. The list is owned with the Deaf partner — not chosen unilaterally.
2. **Domain & risk classification.** Classify the term's domain (everyday / education / civic /
   health / legal / safety). Health/legal/safety → **high-risk track** (Deaf review *and* domain
   expert; "not advice / not a substitute for a qualified interpreter" label) or deferred.
3. **Capture with consent (human, consent-gated).** A consenting Deaf signer performs the sign on
   video, or a Deaf illustrator draws it. **Before any recording is stored or published**, a valid,
   informed, revocable consent record is captured (scope, attribution preference, revocation terms).
   *No consent → no capture stored, no publication.* AI does not perform or synthesise the sign.
4. **Scaffold (AI-assisted).** AI drafts the written-language lemma/definition, sense
   disambiguation, gloss/notation candidates, and cross-references — as a structured entry record,
   clearly marked as draft scaffolding for human review, never as the linguistic authority.
5. **Dedup & variant check.** Two-layer: (a) exact match on `term + sense + signLanguage + region`;
   (b) near-duplicate detection on existing entries so the same sign isn't re-published, while
   **genuine regional variants are preserved and labelled** rather than collapsed. A claim/lock
   (TTL + owner stamp) keyed on `term+sense+signLanguage+region` prevents parallel double-work.
6. **Deaf review (the accuracy gate).** A fluent Deaf reviewer scores the entry on the 4-dimension
   rubric and tags any failure via the error taxonomy. Nothing proceeds below 3/4 on any dimension.
   High-stakes entries additionally require credentialed domain-expert sign-off.
7. **Publish (open + consented + attributed).** A publication adapter formats the approved entry and
   media for the open host (open dataset repo + media; and/or Wikidata lexeme / open lexicon where
   the community agrees), carrying license + attribution + consent reference + provenance. Additive,
   non-destructive: never silently overwrite a community's existing entry.
8. **Track to live + maintain.** Record publication status; a deed is "done" only when the entry is
   **live, openly accessible, and reusable**. The consent record stays linked so revocation can
   trigger takedown.

**Components**

- `style-guide/` — entry & notation style guide (framing, lemma/sense conventions, gloss/HamNoSys/
  SignWriting usage, regional-variant labelling, recording/illustration quality bar, cultural norms,
  high-stakes labelling).
- `consent/` — the consent framework: informed-consent script, likeness/publication release,
  attribution-preference capture, **revocation/takedown policy + SLA**, and the consent-record schema.
- `pipeline/` — term intake, domain/risk classification, dedup/variant check, claim/locking, and the
  per-entry record schema.
- `adapters/` (Hee-Lee Oss-conformant; all host/source-specific logic lives here) —
  - `adapters/open-dataset/` — publish entry metadata + media to the open dataset repo + durable media
    host (with checksums, license, attribution, consent ref, provenance).
  - `adapters/lexeme/` — optional contribution to Wikidata lexemes / an open sign lexicon **where the
    community agrees** and the target's license/consent norms allow.
- `records/` — per-entry records + consent ledger (the project's data artifact: provenance + audit +
  revocation state).
- `review/` — the Deaf-review rubric, reviewer checklist, credential register, and rotation.

**Tech stack & conventions.** TypeScript, ESM, pnpm workspaces. **Adapter/tooling code: MIT.**
**Content (videos, illustrations, definitions): CC-BY-4.0 by default** (or CC-BY-SA-4.0 / CC0-1.0 as
the partner community prefers — a locked decision deferred to the partner, see §7). **Media formats:
open/royalty-free** (e.g., VP9/AV1 in WebM, or H.264/MP4 where unavoidable for reach; SVG/PNG for
illustrations; WebVTT captions). DCO sign-off (`git commit -s`) on all code and PRs. Funded lane is
**not** used for capture (capture is inherently human + consent-bound); if ever used, only for
bounded scaffolding/tooling tasks with a hard per-task budget cap.

**Locked build decisions (constraints-as-identity).**
- **Deaf review is the accuracy authority** — non-optional, every entry, no exceptions.
- **Consent is a hard gate** — no recording stored or published without a valid, revocable consent
  record; a working takedown path ships in M0/M1, not "later."
- **One named sign language + region at a time** — proven cold-start before any second language.
- **Open license + open, accessible host** — including captions/alt-text on the glossary site itself
  (the resource must itself be accessible).
- **No synthetic signing avatars** — ever, as a deliverable.

**Per-entry record (data model, draft)**

```
entryId            stable id (e.g., "ase-US-fire-001")
term               written-language lemma (e.g., "fire")
termLang           BCP-47 of the written language (e.g., "en")
signLanguage       ISO 639-3 / BCP-47 sign code (e.g., "ase" ASL, "bfi" BSL, "isg" Irish SL)
region             region/community label (e.g., "US-Northeast")
senseId            disambiguated sense (term may have several meanings/signs)
definition         plain written-language definition of the sense
mediaType          video | illustration
mediaRef           file ref + open format (WebM/MP4 ; SVG/PNG) + checksum
captions           WebVTT / text alternative for the entry page (self-accessibility)
notation           { gloss?, hamnosys?, signwriting? }  (optional, draft until reviewed)
variantOf          links to sibling regional/lexical variants (preserve, don't collapse)
domain             everyday | education | civic | health | legal | safety
riskTier           low | medium | high   (health/legal/safety => high)
contributor        signer/illustrator display attribution (per their preference)
consentRef         id into the consent ledger (scope, granted date, revocable, status)
license            SPDX-style id (e.g., "CC-BY-4.0" | "CC-BY-SA-4.0" | "CC0-1.0")
claim              { owner, sessionId, claimedAt, ttl } lock to prevent double-work (nullable)
deafReviewStatus   drafted | needs-deaf-review | needs-expert | approved | rejected
reviewScores       { signAccuracy, senseFidelity, productionClarity, culturalAppropriateness }
reviewerCredential reviewer identity/role (fluent Deaf signer; + domain expert if high-risk)
publishStatus      unpublished | published | withdrawn
publishRef         dataset commit / lexeme id / URL once live
provenance         tool, model (scaffolding only), capture date, location?(optional), reviewer
```

**Consent record (data model, draft)**

```
consentId          stable id
contributor        signer/illustrator (and attribution preference: name | handle | anonymous)
scope              what is consented (this entry; this glossary; open-license publication)
licenseAck         contributor acknowledged the chosen open license and its implications
revocable          true   (always)
revocationTerms    plain-language: how to revoke, the takedown SLA, and the honest limit below
takedownState      active | revocation-requested | withdrawn
grantedAt / by     timestamp + how consent was captured (signed form / recorded statement)
minorSafeguards    if contributor is a minor: guardian consent + extra safeguards (or excluded)
```

**Key decisions**

- *Deaf-led, not Deaf-consulted.* Review authority and term selection sit with the Deaf community; AI
  and hearing contributors support, never decide, sign correctness.
- *Consent over convenience.* A working revocation/takedown path is a launch gate. We tell signers
  the **honest limit** up front (below) so consent is genuinely informed.
- *Honest consent re: open licenses.* An open license (CC) on a published recording is, for copyright
  purposes, **irrevocable**, and downstream copies cannot be recalled. We therefore (a) state this
  plainly during consent, and (b) still **honour withdrawal** by removing the entry from *our*
  distribution and marking it `withdrawn` — a community-trust commitment beyond the bare license.
- *Variation preserved.* Regional/lexical variants are recorded as variants, not flattened to one
  "official" sign.
- *The resource is itself accessible.* The glossary's own pages carry captions, text alternatives,
  and high-contrast media — accessibility is not only the content but the container.

## Data, licensing & compliance

**This is the critical, conservative section.** Two compliance regimes apply at once: **copyright/
license** *and* **consent/likeness** — both must pass independently.

**Allowed sources (only these classes).**

- **Original captures** from consenting Deaf signers / Deaf illustrators, released by the contributor
  under the chosen open license — the default and primary source.
- **Existing media** only if it has **both** a clear open license (CC-BY / CC-BY-SA / CC0 / PD)
  **and** documented performer consent for this use. If either is missing or unclear → excluded.
- **Reference lexica / linguistic data** consulted for scaffolding only if their license permits
  reuse/derivatives (verify per source — many academic sign databases are restrictive or
  non-commercial); their content is not republished beyond what the license allows.

**Hard license + consent gate.** Before any recording is *stored* or *published*:

1. **Consent:** a valid, informed, in-scope, revocable consent record exists for the signer's
   likeness and the chosen open-license publication. **No consent → nothing stored, nothing
   published.** Minors require guardian consent and additional safeguards, or are excluded.
2. **License:** the content is releasable under a verified open license (CC-BY / CC-BY-SA / CC0 / PD).
   **Unknown / all-rights-reserved / unclear → excluded.**
3. **Attribution:** the contributor's attribution string (per their stated preference, including
   "anonymous") is recorded with the entry.
4. **Provenance:** source, capture date, tool, scaffolding-model, reviewer(s), and credential are
   recorded.

**Output licensing.** Content (videos, illustrations, definitions, notation) is published under
**CC-BY-4.0** by default, or **CC-BY-SA-4.0 / CC0-1.0** as the partner community decides (the choice
is theirs; see Open questions). Adapter/pipeline **code** is **MIT**. The chosen content license is
recorded per entry and disclosed to the contributor during consent.

**Privacy / PII stance (sign video is biometric, identifying data).**

- Sign video shows a person's face and body and is **personal, identifying, biometric-class data.**
  It is treated as PII end to end: minimised, access-controlled in pre-publication storage, never
  reused for identification, recognition, training of unrelated models, or any purpose beyond the
  consented glossary.
- **Bystanders/background:** captures must avoid incidental third parties and identifying background;
  framing and review check for this.
- **Location and other metadata** are optional and minimised; sensitive metadata is stripped before
  publication.
- **Minors:** only with guardian consent and extra safeguards, or excluded.
- We do **not** infer or publish private attributes of contributors.

**Cultural-rights & appropriation stance.** Sign languages are the cultural property of Deaf
communities. We do not extract a community's signs without that community's leadership, do not
present one community's signs as another's, and credit contributors and the community as a source.

**Robots / automation / host policy.** Any contribution to external open hosts (Wikidata lexemes,
open lexica) honours that host's policy, rate limits, and community norms, with pre-engagement before
volume. We do not scrape around access controls or terms.

## Quality, review & risk gates

**Risk tier: medium baseline; high for health/legal/safety terms.**

- **medium (default)** — every entry needs domain accuracy in the sign language → **fluent Deaf
  reviewer** sign-off is mandatory for *all* entries (per the good-deed definition's medium tier:
  "needs domain accuracy … reviewer with relevant skill").
- **high (escalation)** — health, legal, and safety terms can cause real harm if signed wrong →
  **credentialed domain-expert sign-off in addition to Deaf review** before publication, plus a "not
  a substitute for a qualified interpreter / not advice" label; otherwise not published.

**Required gates before a deed is "done":**

1. **Consent gate passed** — valid, in-scope, revocable consent recorded; revocation path live.
2. **License gate passed** — verified open license + recorded attribution + provenance.
3. **Deaf accuracy review passed** — scored on the 4-dimension rubric; nothing below 3/4 on any
   dimension; failures tagged by the error taxonomy. (This gate cannot be satisfied by a non-Deaf or
   non-fluent reviewer.)
4. **High-stakes expert gate (testable)** — every term classified health/legal/safety gets
   credentialed domain-expert eyes **regardless of classifier confidence** (a low-confidence "maybe
   medical" still routes to the expert/Deaf gate; failing open never lets a high-stakes term publish
   unseen), and carries the required label. Credentials recorded in `provenance`.
5. **Self-accessibility check** — the published entry page itself is accessible (captions/text
   alternative, contrast, keyboard navigation).

**Definition of Shipped (project-level).** An entry is **Deaf-reviewed-and-approved, backed by a
valid consent record, published under an open license to a durable, openly-accessible host, and live
and reusable** by the community — with license + attribution + consent ref + provenance recorded, and
a working revocation path. Recorded-but-not-published, or published-without-consent, ≠ shipped.

## Roadmap & milestones

Phased; each milestone has measurable exit criteria. M0 is deliberately thin, manual, and **Deaf-led
from the first frame** — it must prove a single entry can travel from a consenting signer to
*published, open, Deaf-approved, and live* (with a working takedown path) before anything scales.

**M0 — Foundation, Deaf leadership & cold-start (prove one consented, reviewed, published entry).**
Goal: secure Deaf leadership for one named language/region, stand up consent + style + review
frameworks, and publish a tiny co-designed batch end-to-end.

**Sequencing — Deaf leadership is a hard gate.** The partner/leadership task is a **blocking
prerequisite**: no capture, scaffolding-of-real-entries, or publication begins until a Deaf-led
partner + fluent-Deaf review capacity are confirmed for a named language/region, and a term list is
co-designed. **Kill/pivot criteria:** if the time-boxed effort secures no Deaf-led partner, the
project **pivots** (next candidate community/language) or **stops** — it does **not** proceed
hearing-led, and does not film signers without a review and consent path in place.

**M0 batch-selection criteria (exercise every path, not 10 easy nouns).** The cold-start batch
(≈10 terms) is co-designed with the partner and spread across paths: several **everyday/education**
terms, at least one **polysemous** term (forcing sense disambiguation / multiple signs), at least
one term with a known **regional variant** (exercising variant labelling), at least one **video** and
one **illustrated** entry, and **zero** high-stakes terms in M0 (the high-stakes track is piloted
only later, once the expert gate exists). A batch of 10 trivial nouns is disallowed — it would not
prove the pipeline.

Exit criteria:
- Deaf-led partner + fluent-Deaf review capacity **confirmed** for one named sign language + region;
  term list co-designed. (Closes the partner/leadership gate; gates all capture/publish work.)
- Consent framework v1 published (informed-consent script, likeness/publication release, attribution
  capture, **revocation/takedown policy + SLA**, consent-record schema).
- Entry & notation style guide v1 + Deaf-review rubric v1 published.
- Per-entry + consent record formats finalised and applied to the batch.
- Durable, openly-accessible publication host chosen and content license decided **with the partner**.
- **≥ 10 entries Deaf-reviewed, approved, consented, and published live & openly**, each with
  license + attribution + consent ref + provenance.
- **A real revocation drill executed**: one test/volunteer entry is withdrawn end-to-end within the
  SLA, proving takedown works *before* scale.
- Baseline coverage measured against the co-designed term set (named snapshot + denominator).

**M1 — Pipeline, tooling & repeatability.**
Goal: turn the manual slice into a repeatable, consent-safe, policy-compliant pipeline.
Exit criteria:
- Open-dataset publication adapter (and/or lexeme adapter where the community agrees) working,
  additive, checksummed, and policy-compliant.
- Consent ledger + **revocation/takedown workflow** operational with SLA tracking.
- Dedup/variant check + claim/locking operational (variants preserved, not collapsed).
- Domain/risk classifier routing high-stakes terms to the expert gate (fail-safe to human).
- Deaf-review workflow documented; ≥ 2 fluent Deaf reviewers onboarded with a credential register.
- ≥ 100 entries published live; approval rate and reviewer-corrected rate measured.

**M2 — Controlled scale (one language, deep) + beneficiary validation.**
Goal: meaningfully move coverage in one language/region with quality held, and validate with users.
Exit criteria:
- ≥ 300 entries published live in the named language/region (toward the 2-quarter target).
- Approval rate ≥ 80%; reviewer-corrected rate ≤ 25% and trending down; inter-reviewer agreement ≥ 0.7.
- ≥ 1 beneficiary validation per ~100 entries (Deaf users / learners / a parent of a deaf child).
- High-stakes track piloted: a small health/safety set with **both** Deaf + domain-expert sign-off
  and the required label — or explicitly deferred with rationale.
- Zero consent or license violations; 100% takedown-SLA adherence on any requests.

**M3 — Broaden & sustain (second community, durable ops).**
Goal: add a second named language/region (with its **own** Deaf partner) and a maintenance model.
Exit criteria:
- ≥ 1 additional language/region onboarded with its own confirmed Deaf-led partner + reviewers.
- Outcome dashboard (published/live, approval rate, takedown SLA, coverage per language) maintained.
- Documented maintainer + Deaf-reviewer rotation; community ownership/handover and sustainability
  plan in effect; takedown path durable beyond the active push.

## Work breakdown

The itemised, schema-mapped backlog lives in **`TASKS.md`** (same directory), organised by the
milestones above: one task per work unit, stable IDs (`sign-glossary-<area>-NNN`), a
size/risk/reviewer table per milestone, acceptance criteria for the key tasks, milestone Definitions
of Done, a backlog of sized-but-unscheduled work, and a complete, schema-valid example Task JSON for
the first M0 task. The production backlog fans out: at scale, **one term × one language/region = one
entry = one task**, drawn from a co-designed, milestone-scoped batch.

## Governance, roles & stakeholders

- **Maintainer (Owner):** TBD — owns the style guide, consent framework, pipeline, adapters, and the
  overall quality bar. Accountable for keeping the project Deaf-led in practice, not just in name.
- **Deaf community lead / partner:** **TO BE SECURED** — a Deaf-led organisation or community group
  for the named language/region that co-designs the term list, supplies/sources signers, and holds
  review authority. *Without this role the project does not capture or publish.*
- **Deaf reviewers (accuracy authority) / rotation:** a pool of fluent Deaf signers who score entries
  on the rubric; the **only** role that can clear the accuracy gate. Credentials recorded in a
  register; rotation documented in M1.
- **Domain experts (high-risk tiers):** credentialed health/legal/safety professionals (ideally Deaf
  or working with Deaf colleagues) who co-sign high-stakes terms before publication.
- **Consent steward:** owns the consent ledger and the **revocation/takedown SLA** — the person
  accountable for "no publication without consent" and "withdrawal honoured on time."
- **Steward (last-mile owner):** owns the publication channel(s) and shepherds entries to *live &
  reusable* — accountable for "delivered, not merged."
- **Contributors (signers / illustrators):** Deaf community members who perform/draw signs, credited
  per preference, retaining revocable consent over their likeness.
- **Beneficiary validators:** Deaf users, learners, interpreters, and parents of deaf children who
  confirm batches are accurate and usable.
- **Conflict-of-interest / veto:** per the Hee-Lee Oss good-deed governance, edge cases and any
  for-profit-capture concern go to the board + community against the published COI/veto checklist.

## Dependencies & integrations

- **Deaf-led partner + fluent-Deaf reviewers** — the critical dependency; everything gates on it.
- **Durable, openly-accessible media + dataset host** — a host that serves open video at acceptable
  quality, persists long-term, and is itself accessible (e.g., an open dataset repo + Internet
  Archive / Wikimedia Commons-class media host; final choice with the partner). Long-term video
  hosting cost/durability is a real constraint (see Risks).
- **Wikidata lexemes / open sign lexica (optional)** — only where the community agrees and license/
  consent norms allow; subject to that host's policy, with pre-engagement before volume.
- **Notation references** — gloss conventions, HamNoSys, SignWriting (used per their terms).
- **Open / royalty-free media tooling** — encoders for VP9/AV1/WebM, captioning (WebVTT), SVG/PNG.
- **License metadata** — SPDX identifiers; CC license deeds.
- **Hee-Lee Oss platform pieces** — `packages/cli` (task workspace + PR prep, donated lane), the Task
  schema (`packages/schema`), and `adapters/` for all host-specific code. The CLI never runs an agent
  headless and never authenticates a coding agent.

## Risks & mitigations

| Risk | Likelihood | Impact | Mitigation | Owner |
|---|---|---|---|---|
| Project drifts hearing-led / "about" Deaf people rather than Deaf-led | Medium | High | Deaf leadership is a hard M0 gate (no partner → no capture); Deaf reviewers are the sole accuracy authority; term list co-designed; community credited as source | Maintainer / Deaf lead |
| A wrong sign published as authoritative (misinformation) | Medium | High | Mandatory fluent-Deaf review scored on the 4-dimension rubric + error taxonomy; nothing < 3/4; community challenge path with resolution SLA | Deaf reviewers |
| High-stakes term (health/legal/safety) signed wrong → real harm | Low–Med | High | High-risk tier: Deaf **and** credentialed domain-expert sign-off; fail-safe routing regardless of classifier confidence; "not advice / not a substitute for a qualified interpreter" label; else not published | Maintainer / Expert |
| Signer likeness published without/ beyond consent | Low | High | Consent is a hard pre-storage/pre-publish gate; in-scope check; minors excluded or guardian-consented; stop-the-line on any gap | Consent steward |
| Contributor wants their video removed (revocation) | Medium | Medium | Working revocation/takedown workflow + published SLA shipped in M0/M1; honest up-front disclosure of the irrevocable-CC limit; M0 revocation drill | Consent steward |
| Open-license irrevocability vs. withdrawal expectation (downstream copies persist) | Medium | Medium | Disclose plainly during consent; still remove from our distribution and mark `withdrawn`; do not promise recall of downstream copies | Consent steward / Maintainer |
| No Deaf-led partner / reviewers secured → nothing ships | Medium | High | M0 exit gate is a confirmed Deaf partner + reviewers; `verifiedNeed=false` until secured; pivot/stop, never proceed hearing-led | Maintainer |
| Sign language treated as universal / regional variation erased | Medium | Medium | One named language+region at a time; variant labelling preserves variation; dedup never collapses genuine variants | Maintainer / Deaf reviewers |
| Non-open or non-consented third-party media used | Low | High | Dual hard gate (open license **and** performer consent); "unknown = excluded"; no scraping; stop-the-line on violation | Steward |
| Sign video (biometric PII) misused / reused beyond glossary | Low | High | Treat as PII end-to-end; access-controlled pre-publish storage; no recognition/training reuse; minimise metadata; strip sensitive data | Consent steward |
| Cultural appropriation / extracting community signs without standing | Medium | High | Deaf leadership + co-design; credit community as source; community veto on contested entries | Deaf lead |
| Deaf-reviewer capacity is the bottleneck | High | Medium | Reviewer rotation + credential register; batch sizing; scale fan-out only to review capacity; AI scaffolding reduces non-linguistic load | Maintainer |
| Long-term video hosting cost/durability fails | Medium | Medium | Choose a durable open host; checksums + provenance; open formats; dataset is portable/mirrorable; sustainability plan funds/archives hosting | Steward |
| AI "helpfully" generates or guesses a sign | Low | High | Hard rule: AI never produces a sign; only scaffolds metadata; Deaf review catches any non-human sign; refusal guardrail flags such requests | Maintainer / Reviewers |
| Offensive/outdated/pejorative form presented as neutral | Low–Med | Medium | Cultural-appropriateness rubric dimension; Deaf review; style-guide guidance on archaic/pejorative forms | Deaf reviewers |

## Security & privacy

- **Threat surface.** Primarily privacy/consent and content-integrity rather than classic infosec:
  signer likeness (biometric PII) exposure or misuse, consent/revocation failures, wrong signs, and
  license violations. Adapters also write to external open hosts (dataset repo, lexeme endpoints).
- **Secrets handling.** Any host API tokens (repo, media host, lexeme endpoints) are supplied via the
  human's own environment, never written into logs, receipts, records, or committed files (per
  CLAUDE.md). Donated lane: the human authenticates with their own account; Hee-Lee Oss stores no agent
  credentials.
- **PII / biometric data.** Sign video is identifying, biometric-class PII: access-controlled in
  pre-publication storage, minimised, never used for identification/recognition/unrelated model
  training, metadata stripped of sensitive fields, bystanders avoided, minors excluded or
  guardian-consented. Only consented, approved media is published.
- **Consent lifecycle as a security property.** The consent ledger is the source of truth for
  publication rights; revocation must propagate to takedown within SLA; withdrawn entries are removed
  from distribution and marked `withdrawn` (downstream-copy limit disclosed honestly).
- **Abuse / misuse prevention.** No mass unreviewed publication; honour host policy/rate limits;
  every entry is Deaf-reviewed and consented. Refuse and flag (per Hee-Lee Oss guardrails) any request to
  publish non-open or non-consented media, to synthesise signs, to identify individuals from video,
  or to ship high-stakes signs without expert review.

## Sustainability & maintenance

- **Community ownership.** The durable outcome is an openly-licensed, Deaf-reviewed corpus the
  community can keep, mirror, and extend independent of Hee-Lee Oss. The goal is to hand stewardship toward
  the Deaf partner over time, not to make the community depend on us.
- **Outcome tracking.** A lightweight dashboard tracks published-and-live counts, approval rate,
  coverage per language/region, community accuracy challenges, and **takedown-SLA adherence** — so
  impact and consent-integrity stay visible after the active push.
- **Durable hosting + portability.** Open formats, checksums, and a portable dataset mean entries can
  be mirrored/archived; the sustainability plan must name who funds/maintains media hosting long-term.
- **The takedown path must outlive the push.** Revocation must remain actionable after active
  development ends; the consent steward role (or its successor) persists, and the policy names how
  withdrawals are handled in maintenance mode.
- **Project maintenance.** The maintainer keeps the style guide, consent framework, and adapters
  current with host policy and community feedback; reviewer rotation keeps Deaf-review capacity alive.
- **Wind-down.** If a language/region channel closes, in-flight entries are completed or cleanly
  withdrawn; the consent ledger and provenance log record final disposition; the corpus remains open.

## Open questions

- Which Deaf-led partner, sign language, and region are secured first? (Blocks M0 exit; everything
  gates on it.)
- What **content license** does the partner community prefer — CC-BY-4.0, CC-BY-SA-4.0, or CC0-1.0?
  (Decided with them; recorded per entry and disclosed during consent.)
- Which **durable, openly-accessible host** serves open sign video at acceptable quality and persists
  long-term — and who funds that hosting beyond the active push?
- Does the community want contributions mirrored to **Wikidata lexemes / an open lexicon**, and under
  what norms?
- What exact **credential bar** clears each gate — what qualifies a "fluent Deaf reviewer," and which
  credential qualifies a health/legal/safety domain expert?
- What **takedown SLA** is both honest and operationally sustainable (target ≤ 7 days)?
- How are **minor contributors** handled — guardian consent with safeguards, or excluded in early
  phases?
- What **inter-reviewer agreement** threshold and sampling rate keep the rubric calibrated, and how
  often is the rubric/error-taxonomy revised from the observed failure mix?
- Where notation is used (gloss / HamNoSys / SignWriting), which system(s) does the community prefer,
  and is it required or optional per entry?
- What is the right batch size to keep Deaf-reviewer capacity from becoming the bottleneck?

## References

- `C:\code\hee-lee-oss\CLAUDE.md` — Hee-Lee Oss work rules, lanes, quality bar, refusal guardrails.
- `C:\code\hee-lee-oss\docs\good-deed-definition.md` — good-deed criteria and risk tiers.
- `C:\code\hee-lee-oss\packages\schema\src\schemas.ts` — Task JSON schema.
- `C:\code\hee-lee-oss\planning\ROADMAP.md` — portfolio roadmap (sign-glossary, Track 4).
- `C:\code\hee-lee-oss\planning\projects\a11y-alttext-commons\PLAN.md` — sibling accessibility pipeline (pattern reference).
- Creative Commons license suite (CC-BY, CC-BY-SA, CC0) and Public Domain.
- Notation systems: glossing conventions, HamNoSys, SignWriting.
- Wikidata Lexemes (optional open lexicon target) and its community policy.
- The principle **"Nothing About Us Without Us"** (disability self-determination).

---

## Appendix A — Improvements applied

The following 25 specific improvements were made to the working draft and are **all reflected in the
sections above** (not aspirational). Each sharpens correctness, enforceability, or honesty.

1. **Reframed the whole project as Deaf-*led*, not Deaf-*reviewed*.** Elevated Deaf authority from a
   review step to the project's first principle and a hard M0 gate (Exec summary, §2, §7, §9).
2. **Made consent a pre-*storage* gate, not just pre-publish.** Nothing is even stored without
   consent (§6, §7 pipeline step 3), because the recording itself is biometric PII.
3. **Added a working revocation/takedown workflow with a published SLA** as a launch requirement, and
   an **M0 revocation drill** to prove it before scale (§7 M0, §8, metrics, risks).
4. **Confronted the CC-irrevocability vs. withdrawal tension honestly** — disclose the downstream-copy
   limit during consent, still honour withdrawal from our distribution (§6 key decisions, risks).
5. **Classified sign video explicitly as biometric, identifying PII** end-to-end, barring reuse for
   recognition/identification/unrelated model training (§7, §14).
6. **Scoped to one named sign language + region at a time** and banned "universal sign" claims —
   a constraint-as-identity (§3 non-goals, §6 locked decisions).
7. **Preserved regional/lexical variation** as a first-class data field, and made dedup never collapse
   genuine variants (data model `variantOf`, pipeline step 5, metrics, risks).
8. **Banned synthetic signing avatars as a deliverable** — addressing a real Deaf-community objection
   (§3 non-goals, §6 locked decisions).
9. **Bounded the AI's role**: AI never invents/performs a sign; it only scaffolds metadata — and a
   refusal guardrail flags any request to generate signs (Exec summary, §6, §14, risks).
10. **Split risk tiers correctly**: medium baseline (Deaf review for all) + high for
    health/legal/safety with dual sign-off and a "not advice / not a substitute for an interpreter"
    label (§8, metrics, risks).
11. **Made the high-stakes gate testable and fail-safe**: low-confidence "maybe medical" still routes
    to the expert/Deaf gate; failing open never publishes a high-stakes term unseen (§8 gate 4).
12. **Added sense disambiguation** (`senseId`, polysemy) so one written term maps to the correct sign
    per meaning, with M0 batch forced to include a polysemous term (data model, §7, §9).
13. **Replaced binary "Deaf review passed" with a 4-dimension rubric** (sign accuracy, sense fidelity,
    production clarity, cultural appropriateness) + an error taxonomy (metrics, §8).
14. **Added a cultural-appropriateness dimension** and guidance against presenting archaic/pejorative
    forms as neutral (rubric, risks).
15. **Required the resource itself to be accessible** (captions/text alternatives/contrast/keyboard on
    the glossary pages), not just the content (§6 locked decisions, §8 gate 5, data model `captions`).
16. **Specified open/royalty-free media formats** (VP9/AV1/WebM, SVG/PNG, WebVTT) and checksums for
    durability/portability (§6 stack, data model, dependencies).
17. **Named long-term video-hosting cost/durability as a real risk** with portability/mirroring and a
    funding question in the sustainability plan (dependencies, risks, §15, open questions).
18. **Made coverage reproducible**: `published ÷ co-designed target term set` against a named snapshot,
    with baseline deferred until measured rather than invented (metrics).
19. **Co-designed the term list with the partner** instead of choosing it unilaterally, and made it a
    gating dependency (§2, §7 pipeline step 1, §9, M0 exit).
20. **Added an honest M0 batch-selection rule** (polysemous + regional-variant + video + illustration;
    zero high-stakes in M0) so the cold-start proves the hard paths, not 10 easy nouns (§9).
21. **Added kill/pivot criteria** so the project stops or pivots rather than proceeding hearing-led or
    filming without a consent/review path (§9 sequencing, risks).
22. **Set `verifiedNeed = false`** for capture/publish tasks until a Deaf partner is secured, while
    keeping framework/style/consent docs as self-evident (`true`) — honest per-task (TASKS.md).
23. **Added a consent-record data model** (scope, attribution preference incl. anonymous, revocation
    terms, minor safeguards, takedown state) distinct from the entry record (§6).
24. **Added minors-safeguards and bystander/background handling** to the privacy stance (§6, §14).
25. **Separated copyright/license compliance from consent/likeness compliance** as two independent
    hard gates that must both pass (§6, §8) — the project's defining compliance posture.

---

## Review sign-off

A completeness + correctness pass against the Hee-Lee Oss quality bar and the PLAN spec. Issues found in
review were fixed in-line above; this section records the verification.

**Completeness.** All 17 required H2 sections are present and ordered per the spec. Metadata header
present (Status/Version/Date/Owner/Lane). Positioning, who-for, explicit non-goals, locked decisions,
stack, phased roadmap, and constraints-as-identity are all included at the depth of the Ofelia
exemplar.

**Measurable metrics.** Success metrics are outcome-based and beneficiary-centric with baseline +
target, plus a reproducible counting method; vanity counts explicitly rejected. Coverage targets are
honestly deferred until a real baseline exists.

**Enforceable gates.** Five named gates (consent, license, Deaf accuracy review, high-stakes expert,
self-accessibility) with a clear Definition of Shipped. The high-stakes gate is explicitly testable
and fail-safe. Two compliance regimes (license + consent) are independent and both blocking.

**Risks with owners + mitigations.** 16-row risk table; every row has likelihood, impact, a concrete
mitigation, and a named owner. Top risks (hearing-led drift, wrong sign, high-stakes harm, consent
violation, no partner) each map to a gate and/or kill-pivot criterion.

**License / PII / expert-review guardrails.** Open-license-only with dual license+consent gate;
biometric-PII stance with minimisation, no-reuse, minors, and bystander handling; CC-irrevocability
addressed honestly; high-stakes terms require credentialed domain-expert sign-off and a "not advice /
not a substitute for an interpreter" label. Cultural-rights/appropriation stance included.

**Sequencing.** Deaf leadership is a blocking M0 prerequisite; kill/pivot criteria prevent
undeliverable or hearing-led work; milestones M0→M3 have measurable exit criteria with realistic
dependencies (review capacity gates fan-out; takedown path ships before scale).

**Schema validity.** TASKS.md maps every field of `taskSchema`; the example Task JSON was validated
against the schema's required fields and enums (see TASKS.md). `verifiedNeed=false` on
capture/publish tasks where no partner is secured; `lane=donated` throughout (no funded tasks, so no
`fundedBudgetUsd` required).

**Honesty.** Partner/requestor, sign language, region, and term list are all marked **TO BE SECURED /
co-designed**, not invented. No partner is fabricated.

**Open items needing a human decision** (carried to Open questions): partner/language/region
selection, content-license choice, durable host + funding, takedown SLA value, minor-contributor
policy, and credential bars. **Sign-off:** Draft ready for maintainer + Deaf-partner review; **must
not begin capture until the Deaf-leadership gate is closed.**
