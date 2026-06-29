# Competitive + Improvement Analysis — `sign-glossary`

> Scope: open, **Deaf-led** video glossary of signs for key terms — especially technical/STEM/medical
> terms that lack established signs — built **with** Deaf communities. Analysis grounded against the
> v0.1.0 PLAN.md and TASKS.md, with cited web research on the competitive field.
> Cardinal guardrail throughout: **Deaf-community leadership ("nothing about us without us")**;
> hearing-led sign creation is harmful and disqualifying.

---

## 1. Correctness & completeness review of PLAN.md

The PLAN is unusually strong on ethics and governance for a draft. It already nails the hardest
things most hearing-built sign projects get wrong. The findings below are therefore mostly about
**sharpening a good plan**, with two genuinely load-bearing gaps.

**What is correct and well-handled (verify, keep):**

- **Deaf leadership as a hard gate, not a review step.** The PLAN reframes the project as
  Deaf-*led* (Exec summary, §2, §9, Appendix item 1), makes "secure a Deaf-led partner" a *blocking*
  M0 exit criterion, sets `verifiedNeed=false` until secured, and adds explicit kill/pivot criteria
  ("does not proceed hearing-led"). This is the cardinal requirement and it is met at the level of
  design. This matches the documented community consensus that DHH-led design is essential and that
  hearing-dominated pipelines cause cultural erasure and harm
  ([arXiv 2403.02563, Deaf-led call](https://arxiv.org/pdf/2403.02563);
  ["Nothing about us without us", arXiv 2512.08839](https://arxiv.org/abs/2512.08839)).
- **Per-language, non-universal.** ASL≠BSL≠Auslan≠LSF is explicit (data model `signLanguage` as
  ISO 639-3, "one named language + region at a time", banned "universal sign" claims). Correct and
  consistent with WFD/WASLI's position that signed languages are distinct full languages
  ([WFD/WASLI avatar statement](https://wfdeaf.org/resources/statement-on-use-of-signing-avatars/)).
- **Regional variation preserved** (`variantOf`, dedup "never collapses genuine variants"). Correct.
- **Consent + likeness as biometric PII**, pre-*storage* gate, revocation/takedown SLA, M0 revocation
  drill, honest disclosure of CC irrevocability. This is more rigorous than any competitor surveyed.
- **No synthetic signing avatars** as a deliverable — directly aligned with the WFD/WASLI caution.
- **Attribution always**, dual independent license+consent gates, accessibility *of the resource
  itself* (captions/contrast/keyboard), high-stakes (health/legal/safety) dual Deaf+expert gate.

**Finding A (most important — descriptive vs. prescriptive / the STEM-neologism gap).**
The project brief specifically targets **technical/STEM/medical terms that lack established signs**.
But the PLAN's accuracy rubric, Dimension 1, requires "a correct, **current** sign … **not
invented**." For the project's headline use case there often *is no* current sign — the community
must **coin** one. The PLAN does not yet distinguish:
(a) hearing-led prescription/invention (harmful — correctly to be refused), from
(b) **Deaf-community-led coinage of a genuinely new sign** where none exists (legitimate, and exactly
what ASLCORE, the Scottish Sensory Centre BSL Glossary, and ASL-STEM Forum exist to do). As written,
the "not invented" criterion could block the project's own core deliverable, or — worse — push
coinage into an undefined grey zone with no status tracking. Research shows new signs that *depict
the concept* get adopted while arbitrary invented signs do not
([npj Science of Learning 2026](https://www.nature.com/articles/s41539-026-00418-6)), so the design
question is real and well-studied. **Fix:** add an entry lifecycle status
(`attested | community-proposed | emerging | established`), require that *any* new sign be
**Deaf-community-originated and Deaf-validated** (never AI- or hearing-proposed), track real-world
**adoption** as the success signal rather than publication, and reword rubric D1 to "correct for the
named language/region and either attested or community-coined-and-adopted — not borrowed from another
sign language, not hearing-prescribed." Also reconcile the Exec-summary framing (everyday/school/
clinic "key terms") with the brief's technical-term emphasis; right now the PLAN reads broader than
the stated niche, which dilutes both positioning and the rubric.

**Finding B (second most important — Deaf-leadership operationalization & sustainability of review).**
Deaf leadership is asserted strongly but under-operationalized in two ways. (1) The PLAN names a
"fluent Deaf reviewer" as the sole accuracy authority but **defers the credential bar to Open
Questions** — so the cardinal gate currently has no testable definition of *who* qualifies, how
partners co-*own* (not just co-design) the term list and licence, or how authority transfers
(governance/IP ownership, not just stewardship handover). (2) The PLAN itself flags Deaf-reviewer
capacity as a *High-likelihood* bottleneck, yet the only mitigations are rotation + AI scaffolding;
there is no **fair-compensation / funding model for Deaf contributors and reviewers** (the donated
lane assumes volunteer agent-runners, but signers/reviewers are doing skilled linguistic labour).
Unpaid extraction of Deaf labour is itself an equity failure mode the "nothing about us without us"
literature warns about. **Fix:** define the reviewer credential bar and a community-ownership/IP
model in M0 (not deferred), and name a compensation/funding path for Deaf contributors and reviewers
in Sustainability.

**Smaller correctness gaps:**

- **Sense disambiguation is good but "false friends" across written languages** (termLang vs the
  sign's actual semantic field) deserve an explicit reviewer check — partially covered by D2 but not
  called out for cross-linguistic mismatch.
- **Notation choice (gloss/HamNoSys/SignWriting)** is optional and deferred; fine, but the PLAN
  should note these systems are themselves contested in some Deaf communities — defer *to the
  partner*, which it nearly does.
- **"Confirmed useful by the community" / adoption** is in the metrics but weakly instrumented; tie
  it to Finding A's adoption tracking.
- **Indexing/discoverability** (how a parent actually *finds* the sign for a term) is unaddressed —
  a published-but-unfindable entry is not "delivered."

Completeness: all required sections present; metrics are outcome-based with honest deferral of
coverage baselines; risk table is thorough with owners. No fabricated partner. Strong honesty posture.

---

## 2. Competitive landscape (cited)

| Project | Open / reusable licence? | Deaf-led / authority | Scope | Key weakness for our niche |
|---|---|---|---|---|
| **Spread the Sign** | **No — proprietary** | Centre-run, interpreters/signers | 35+ langs, 610k+ videos | Largest by far but **closed**; can't legally remix/build on |
| **ASLCORE** | Site free; not openly licensed | **Yes, Deaf-led (NTID/RIT)** | ~2,000 academic/STEM ASL signs | ASL-only; not an open dataset; coins new signs (prescriptive tension) |
| **ASL-STEM Forum** | Crowdsourced; unclear licence | Community crowd, descriptive | STEM ASL, user videos+ratings | Aging UW project; quality/curation uneven; "collect not decide" |
| **Atomic Hands** | Free resources; not open data | **Yes, Deaf-founded nonprofit** | STEM ASL videos/storybooks | Org/curriculum-centric, not a reusable openly-licensed corpus |
| **Scottish Sensory Centre BSL Glossary** | Free; not openly licensed | BSL linguists + subject experts | ~2,000 BSL STEM/curriculum terms | BSL-only; not open dataset; curriculum-scoped |
| **Handspeak / Lifeprint (ASL University)** | **All-rights-reserved** | Deaf-authored (Vicars) | General ASL dictionary/learning | Single-creator, copyrighted, not reusable |
| **(Auslan/NGT/FinSL) Signbank** | **CC-BY-NC-ND** (Auslan) | Academic + community | Lexical/corpus databases | NC-ND = **no commercial, no derivatives** → not a commons |
| **Wikidata lexemes / Wikimedia Commons** | **Open (CC0/CC-BY)** | Volunteer; varies | Lexemes + sign media, sparse | Open but thin, uncoordinated, no Deaf-review gate or consent layer |

**Strengths/weaknesses, with sources:**

- **Spread the Sign** — the field's scale leader (610k+ videos, 35+ sign languages) and genuinely
  multilingual, but **contents and software are proprietary** and not reusable; run by the European
  Sign Language Centre on public funding + volunteers
  ([Wikipedia](https://en.wikipedia.org/wiki/Spreadthesign);
  [About](https://www.spreadthesign.com/isl.intl/about/)). Strong reference, *not* a commons.
- **ASLCORE** — exemplary on the cardinal axis: "signs are generated by Deaf users of ASL … developed
  according to ASL linguistic principles by fluent Deaf ASL signers", ~2,000 academic signs, NTID/RIT
  backed ([aslcore.org](https://aslcore.org/);
  [C&EN](https://cen.acs.org/education/science-communication/expanding-American-Sign-Languages-science-vocabulary-deaf/99/i25)).
  Weakness for us: ASL-only, website not an open downloadable dataset, and it *creates* signs
  (the prescriptive question — though Deaf-led, which is the legitimate form).
- **ASL-STEM Forum** — pioneering crowdsourced, explicitly **descriptive** model: "We're not trying
  to decide on new signs but just collect the ones in current use" (UW, Ladner, since 2008; NSF/Google
  funded) ([UW News](https://www.washington.edu/news/2012/12/07/crowdsourcing-sit-compiles-new-sign-language-for-math-and-science/);
  [ACM paper](https://dl.acm.org/doi/pdf/10.1145/1753326.1753642)). Weakness: dated, curation/quality
  uneven, no consent/licence rigor, ASL-only.
- **Atomic Hands** — Deaf-led nonprofit (founded 2018, Drs. Wooten & Spiecker), STEM-in-ASL videos,
  storybooks, dictionaries, Deaf STEMist network; offers a *framework* for other communities
  ([atomichands.com](https://atomichands.com/asl-stem-resources/);
  [Sorenson](https://sorenson.com/my-news/atomic-hands-science-technology-engineering-and-math-accessibility-in-asl/)).
  Weakness: resource/community org, not a reusable open corpus — a potential **partner, not just a
  competitor**.
- **Scottish Sensory Centre BSL Glossary** — ~2,000 BSL STEM/curriculum signs since 2007/08, built by
  "teams of BSL linguists and subject specialists … gathering any existing terms and creating new
  terms in BSL for those that do not", with signed definitions and examples
  ([SSC BSL](https://www.ssc.education.ed.ac.uk/BSL/about.html)). The closest structural sibling;
  weakness for us: BSL-only, curriculum-scoped, not an open dataset, mixes attestation and coinage.
- **Handspeak / Lifeprint** — Deaf-authored, widely used, but single-creator and **all-rights-
  reserved**, so not legally reusable ([lifeprint.com](https://www.lifeprint.com/)).
- **Signbank family** — strong academic infrastructure (Auslan/NGT/FinSL), but Auslan Signbank is
  **CC-BY-NC-ND 4.0** — non-commercial *and* no-derivatives — i.e., explicitly **not** an open commons
  you can build upon ([State Library NSW](https://eresources.sl.nsw.gov.au/auslan-signbank);
  [Signbank GitHub/L18-1374](https://aclanthology.org/L18-1374.pdf)). The *software* is open source.
- **Wikidata lexemes / Wikimedia Commons** — genuinely open (CC0/CC-BY) and already used for sign
  documentation (e.g., BISINDO/Indonesia), but sparse, uncoordinated, and with no Deaf-review or
  consent layer ([Wikidata lexicographical data](https://www.wikidata.org/wiki/Wikidata:Lexicographical_data)).
  Best **distribution target**, not a competitor.
- **WFD/WASLI positions** — anchor our guardrails: signed languages are distinct full languages, no
  word-for-sign universal translation, and avatars must not replace human signers
  ([WFD/WASLI statement](https://wfdeaf.org/resources/statement-on-use-of-signing-avatars/)).

---

## 3. Gaps we can fill

1. **An openly-licensed (CC-BY/CC-BY-SA/CC0) commons.** The scale leaders are *proprietary* (Spread
   the Sign), single-creator copyrighted (Handspeak/Lifeprint), or **NC-ND** (Auslan Signbank). No one
   offers a large, **legally remixable** Deaf-reviewed video corpus. This is the central white space.
2. **Consent + likeness rigor as a first-class layer.** No competitor publishes a per-entry,
   revocable, biometric-grade consent ledger with a takedown SLA. This is a trust differentiator.
3. **Per-language, multi-community framework (one named language/region at a time, replicable).**
   ASLCORE/Atomic Hands are ASL; SSC is BSL. A neutral, partner-portable pipeline that each community
   runs *for itself* is missing.
4. **Provenance + variant labelling as data.** Existing resources flatten or omit regional variation
   and provenance; we treat both as first-class fields.
5. **Structured distribution to the open ecosystem** (open dataset + optional Wikidata lexemes /
   Commons) with checksums — closing the gap between "a website" and "reusable data."
6. **A descriptive-first stance with disciplined, Deaf-led coinage tracking** for terms that genuinely
   lack signs — bridging the ASL-STEM ("collect") and ASLCORE ("develop") models *transparently*.

---

## 4. Differentiators to win

- **Open + Deaf-led + consent-first, simultaneously.** Competitors hit at most two of these three; the
  combination is the moat.
- **Constraints-as-identity** (no avatars, no scraping, no universal claims, no hearing prescription)
  read as a credibility signal to the exact community whose trust gates the work.
- **Replicable per-community pipeline** that hands ownership *to* each Deaf partner — anti-extractive
  by design, unlike single-org silos.
- **Provenance/consent ledger** turning "trust us" into auditable records (license + attribution +
  consent ref + revocation state per entry).
- **Outcome metric = community adoption + beneficiary validation**, not videos recorded — aligns
  incentives with the npj-documented reality that only concept-faithful, adopted signs matter.

---

## 5. Claude API leverage (and hard limits)

**Where Claude clearly helps (scaffolding only, never the sign):**

- **Term-list curation & domain/risk classification.** Draft candidate term sets from a discipline
  corpus, cluster by domain, flag health/legal/safety for the high-stakes gate, deduplicate against
  existing entries — all as *proposals* for Deaf-partner co-design.
- **Written-language metadata.** Draft plain-language definitions, sense disambiguation, cross-refs,
  example sentences, and BCP-47/ISO-639-3 tagging — clearly marked draft, human-validated.
- **Workflow coordination & data hygiene.** Generate/validate per-entry + consent records against the
  schema, manage claim/locks, detect near-duplicate metadata, produce captions/alt-text drafts
  (WebVTT) for self-accessibility, and check license/provenance completeness before the gate.
- **Reviewer-load reduction.** Pre-fill everything *non-linguistic* so Deaf reviewers spend their
  scarce time only on sign accuracy/cultural appropriateness.

**Where Claude must NOT decide (hard lines, consistent with PLAN §3/§5):**

- **Never generates, synthesizes, proposes, ranks, or "performs" a sign.** Signs are
  Deaf-community-created and Deaf-validated; coinage of new signs is a Deaf-community act, not an AI
  output. (WFD/WASLI; PLAN no-avatar rule.)
- **Never the accuracy authority.** Cannot clear the Deaf-review gate or the cultural-appropriateness
  dimension.
- **Never decides consent, likeness, or takedown** — human consent steward governs these.
- **Never asserts cross-language equivalence** ("the ASL sign = the BSL sign"); per-language only.
- **Never auto-approves a license/provenance** — "unknown = excluded" is a human verification.
- **Low-confidence health/legal/safety classification must fail *toward* the human expert gate**, never
  publish unseen.

Funded lane: only for bounded scaffolding/tooling with a hard budget cap; **never** for capture
(capture is inherently human + consent-bound).

---

## 6. Ten concrete optimizations

1. **Add an entry-lifecycle status** (`attested | community-proposed | emerging | established`) and
   reword rubric D1 so legitimate Deaf-led coinage for sign-less technical terms is supported, not
   blocked (resolves Finding A).
2. **Instrument adoption.** Track real-world uptake of published/coined signs (re-use, partner
   classroom use, community re-recording) as the headline outcome — the npj evidence says adoption,
   not publication, is the true success signal.
3. **Define the Deaf-reviewer credential bar in M0** (move it out of Open Questions) — the cardinal
   gate needs a testable definition of "fluent Deaf reviewer" and high-stakes expert.
4. **Name a compensation/funding model for Deaf contributors and reviewers** in Sustainability — avoid
   unpaid extraction of skilled Deaf labour; tie to the bottleneck risk.
5. **Co-*ownership*, not just co-design.** Specify IP/governance ownership transfer to the partner
   (the corpus, the term list, and the brand), with a written handover trigger.
6. **Ship a discoverability/index layer** (search by written term + sense + language/region, with
   variants surfaced) — a sign nobody can find is not "delivered."
7. **Publish a reusable "start-your-own-community-glossary" toolkit** (consent script, style guide,
   rubric, schema, adapter) as the replication product — the differentiator vs single-org silos.
8. **Default distribution to Wikidata lexemes + Wikimedia Commons** where the partner agrees — the only
   pre-existing *open* ecosystem; pre-engage on policy before volume.
9. **Add cross-linguistic "false-friend" check** to the review step (termLang semantics vs the sign's
   actual field) and to AI scaffolding QA.
10. **Make the comparison explicit on each entry page**: provenance, variant set, and an honest
    "attested vs community-coined" badge — turning rigor into a visible trust feature competitors lack.

---

## 7. Parallel & perpendicular spin-offs

- **Shared term-curation + definition engine** with **oncology-glossary-multilingual**: the same
  Claude scaffolding (term lists, plain-language definitions, sense disambiguation, risk
  classification) feeds both; medical terms are a natural high-stakes overlap (Deaf review + clinician
  review). Cross-link: a sign entry can carry the multilingual written definition from the oncology
  glossary.
- **caption-commons**: WebVTT captions/alt-text generated for self-accessibility here are the same
  artifact caption-commons produces; share the captioning pipeline and an open-caption schema.
- **open-pictograms**: pictograms and Deaf-drawn sign illustrations share a visual-asset pipeline,
  license/consent model, and SVG/PNG tooling; a "term → pictogram + sign video" pairing aids
  AAC/early-language users (the hearing-parents-of-deaf-children beneficiary).
- **easy-read-plus**: plain-language definitions + pictograms + sign video together form a
  multi-modal "key term" unit for the same low-literacy/learning beneficiaries.
- **A Deaf-led glossary *platform*** (perpendicular): generalize `consent/`, `review/`, `records/`,
  and the adapters into a reusable, partner-ownable platform any Deaf community can deploy for any sign
  language — the replication play, distinct from the ASL/BSL single-org incumbents.
- **An MCP server** exposing the open corpus (read-only, attribution-preserving) so other tools can
  query "sign(s) for term T in language L/region R" with provenance and consent status — the open,
  machine-readable counterpoint to proprietary apps. Must surface variants and never assert
  cross-language equivalence.

---

## 8. Open questions

- **Descriptive vs. coinage policy:** for sign-less technical terms, what is the line and process for
  Deaf-led coinage, and what adoption threshold moves a sign `emerging → established`?
- **Which Deaf-led partner / language / region first?** (Blocks M0; everything gates on it.) Is Atomic
  Hands or an NTID/SSC-style body a partner rather than a competitor?
- **Compensation:** how are Deaf signers/reviewers fairly paid within the donated lane's volunteer
  assumption?
- **Ownership/IP:** does the corpus, term list, and brand transfer to the partner, and on what trigger?
- **Content licence:** CC-BY-4.0 vs CC-BY-SA-4.0 vs CC0 — partner's call; how does SA interact with
  Wikidata/Commons (CC0) distribution?
- **Durable, accessible video host + who funds it long-term** (Commons? Internet Archive? partner
  infra?).
- **Reviewer credential bar + high-stakes expert credential** — exact, testable definitions.
- **Takedown SLA** that is honest *and* sustainable post-push (≤7 days target).
- **Discoverability:** how do beneficiaries actually find an entry, and is search itself accessible?
- **Notation:** does the partner community want gloss/HamNoSys/SignWriting at all, and required or
  optional?

---

### Sources

- Spread the Sign: [Wikipedia](https://en.wikipedia.org/wiki/Spreadthesign) · [About](https://www.spreadthesign.com/isl.intl/about/)
- ASLCORE: [aslcore.org](https://aslcore.org/) · [C&EN](https://cen.acs.org/education/science-communication/expanding-American-Sign-Languages-science-vocabulary-deaf/99/i25)
- ASL-STEM Forum: [UW News](https://www.washington.edu/news/2012/12/07/crowdsourcing-sit-compiles-new-sign-language-for-math-and-science/) · [ACM 1753642](https://dl.acm.org/doi/pdf/10.1145/1753326.1753642)
- Atomic Hands: [atomichands.com](https://atomichands.com/asl-stem-resources/) · [Sorenson](https://sorenson.com/my-news/atomic-hands-science-technology-engineering-and-math-accessibility-in-asl/)
- Scottish Sensory Centre BSL Glossary: [ssc.education.ed.ac.uk/BSL](https://www.ssc.education.ed.ac.uk/BSL/about.html)
- Handspeak / Lifeprint: [lifeprint.com](https://www.lifeprint.com/)
- Signbank / Auslan (CC-BY-NC-ND): [State Library NSW](https://eresources.sl.nsw.gov.au/auslan-signbank) · [L18-1374](https://aclanthology.org/L18-1374.pdf)
- Wikidata lexemes / Commons: [Wikidata lexicographical data](https://www.wikidata.org/wiki/Wikidata:Lexicographical_data)
- WFD/WASLI avatars + language distinctness: [wfdeaf.org](https://wfdeaf.org/resources/statement-on-use-of-signing-avatars/)
- "Nothing about us without us" / Deaf-led design: [arXiv 2512.08839](https://arxiv.org/abs/2512.08839) · [arXiv 2403.02563](https://arxiv.org/pdf/2403.02563)
- Concept-motivated signs & adoption: [npj Science of Learning 2026](https://www.nature.com/articles/s41539-026-00418-6)
