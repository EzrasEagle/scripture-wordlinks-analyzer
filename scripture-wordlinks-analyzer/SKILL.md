---
name: scripture-wordlinks-analyzer
description: Use for comprehensive Scripture Wordlinks Analysis across standard works, Apocrypha, and ancient texts (e.g., 1 Enoch and Malachi). Combines Gileadi-style lexical word-links with advanced structural analysis: Cluster Density Scoring, Scripture-Defined Symbolic Meanings, Chiasmus detection (presence + absence), Hebrew Gematria, Covenant Language Density, and Thematic Polarity. Augmented with 1828 Webster's Dictionary, Topical Guide cross-references, and deeper etymological layers. Supports user-provided tagged lists and GitHub-backed cluster data. Prioritizes high-density clustering and user ★ connections as quality signals.
---

# Scripture Wordlinks Analyzer

## Activation and Scope
This skill activates for any request involving deep literary, lexical, and historical-etymological analysis of scriptures — including the standard LDS works (Bible, Book of Mormon, Doctrine and Covenants, Pearl of Great Price), Apocrypha, pseudepigrapha (e.g., 1 Enoch), or other ancient texts. It is especially powerful for comparisons like 1 Enoch sections and Malachi, or when the user provides tagged scripture citation lists. It combines Gileadi-style word-links analysis with 1828 Webster's definitions and deeper etymological checks to surface connections that modern English may obscure. It handles full sections, focused passages, or user-supplied tagged lists.

## Core Analysis Procedure (Follow Exactly — Multi-Layer Approach)
Execute these steps in order. The method now includes an expanded multi-layer system with **quantitative scoring** for connection quality:

**Primary Layers:**
1. Gileadi-Style Word Links (Lexical Core)
2. 1828 Webster’s + Historical English
3. Deeper Etymology / Original-Language Roots

**Advanced Structural & Scoring Layers (New):**
4. Cluster Density Scoring (Core Quality Metric)
5. Scripture-Defined Symbolic Meanings (Enhanced Gileadi Layer)
6. Chiasmus Detection (Positive + Absence Analysis)
7. Hebrew Gematria Layer
8. Covenant Language Density + Thematic Polarity Scoring

These advanced layers help surface high-quality connections even when individual words are ambiguous due to translation, and they flag both presence *and absence* of expected patterns.

1. **Prepare Inputs and Scope**  
   Confirm the texts, passages, or user-provided tagged citation lists. Note translations and any user tags/themes. Bracket distinct stylistic units (e.g., Noah material in Enoch 106–107) unless explicitly included. If the user supplies a tagged list (e.g., “Book of Remembrance / Book of Life” with citations from canon + Enoch), treat it as primary input for cluster building and cross-text mapping.

2. **Layer 1: Gileadi-Style Word Links Extraction (Lexical Core)**  
   Perform close reading and systematic extraction of repeated words, short phrases (2–6 words), and roots across the provided materials.  
   - Use code_execution tool (Python with collections, difflib, re) for objective frequency counts, intersections, and near-match suggestions.  
   - Prioritize exact/near phrase matches, distinctive terms in eschatological, covenant, or judgment contexts, and chains of repetition.  
   - Categorize into strong phrase-level links and thematic clusters (books/record-keeping, judgment/fire/day of the Lord, heaven opened/portals-windows + blessing, law/ordinances/return/remember in last days, protection of righteous, robbing/wealth of sinners, light/shine imagery, etc.).  
   - Produce initial count and draft table.

3. **Layer 2: 1828 Webster's Dictionary + Historical English Check (Critical New Layer)**  
   For every significant linking word or phrase identified in Layer 1, consult or recall the 1828 Webster's American Dictionary of the English Language definition.  
   - Highlight cases where the 1828 sense differs from or enriches modern usage in ways that strengthen a word link or reveal additional resonance across texts (especially useful for Book of Mormon / early 19th-century style English that preserves older nuances).  
   - Note Early Modern English features (e.g., grammar, vocabulary, or phrasing in the Book of Mormon or KJV that align with pre- or early-KJV English). Reference research on Book of Mormon language (e.g., Royal Skousen Critical Text Project, Stanford Carmack on Early Modern English elements) when relevant to show how older English preserves connections that later modernizations can obscure.  
   - In the output table/notes, add or expand a column/section: “Historical/Etymological Notes (1828 Webster’s or earlier)”. Explicitly call out when an older definition makes a link more apparent or adds theological depth.

4. **Layer 3: Deeper Etymology and Original-Language Roots (Recommended Extension)**  
   For high-value linking words, go further back:  
   - Hebrew, Aramaic, or Greek roots via Strong’s Concordance numbers + lexicons (Brown-Driver-Briggs for Hebrew, Thayer’s for Greek, etc.).  
   - Etymological resources (Online Etymology Dictionary, or specialized works on biblical languages).  
   - When user provides or requests, incorporate specific older English sources (Tyndale, Geneva Bible, or facsimiles) or research on archaic features in the Book of Mormon that maintain word connections across time.  
   - This layer often reveals why certain word links “feel” stronger in older English renderings and helps recover meanings that modern translations or usage have shifted.

5. **Cluster Density Scoring (Primary Quality Metric)**
   After extracting word links, apply quantitative scoring:
   - Count how many distinct terms from the *same thematic cluster* appear in close proximity (verse, paragraph, or short passage).
   - Score passages as:
     - **High Density (Strong Connection)**: 5+ linked terms from one cluster, or 3+ very strong anchors.
     - **Medium Density**: 3–4 linked terms.
     - **Low Density**: 1–2 terms (still valid but weaker signal).
   - Explicitly note *absence* of expected cluster terms as potentially meaningful (e.g., missing covenant language or protection markers in a judgment passage).
   - This scoring is especially powerful when individual words are ambiguous due to translation issues — clustering provides stronger evidence of authorial intent.

6. **Scripture-Defined Symbolic Meanings (Enhanced Gileadi Layer)**
   Identify cases where the text itself explicitly assigns a secondary or symbolic meaning to a word or phrase (e.g., “the stars are the angels,” “waters = peoples,” “the woman = church”).
   - When that secondary meaning appears elsewhere, treat it as a deliberate intertextual link.
   - Track chains of scripture-defined meanings across texts.

7. **Chiasmus Detection Layer**
   Analyze for chiastic structures at verse, pericope, chapter, or book level.
   - Note strong, complete chiasmi as high-quality structural evidence.
   - Note *incomplete or broken chiasmi* as potential indicators of missing text, redaction, or translation issues.
   - Use both presence and absence as analytical signals.

8. **Hebrew Gematria Layer**
   For key Hebrew terms (especially in judgment, covenant, or name contexts), note significant gematria values when they appear consistently or meaningfully across passages.
   - Use primarily as a supporting signal, not a primary driver.
   - Flag cases where gematria reinforces existing lexical or thematic links.

9. **Semitic Paronomasia & Wordplay Layer (New)**
   Detect deliberate puns, paronomasia, sound-alike juxtapositions, and root-based wordplay in Hebrew, Aramaic, and related Semitic languages (with extension points for Egyptian or other influences in the Book of Mormon and related texts).
   - Use morphology data (from the morphology_loader) + approximate phonetic matching or root similarity.
   - Prioritize cases where the text itself highlights the wordplay (e.g., name explanations, "because..." constructions, or juxtaposition of similar-sounding terms).
   - Scripture-defined puns take highest priority.
   - Classic example: 1 Nephi 1:1 "I, Nephi, having been born of goodly parents..." — proposed link between the name "Nephi" and Hebrew נָאָה (nā’ā) or related roots in the semantic field of "goodly / beautiful / pleasant."
   - Integrate with Cluster Density Scoring: puns frequently create or strengthen high-density thematic clusters.
   - Add a dedicated section or expanded table column: "Paronomasia / Wordplay Notes" in the structured output.
   - Use the new `puns/paronomasia.py` module for detection logic.

10. **Covenant Language Density + Thematic Polarity Scoring**
   Measure the concentration of covenant formula language (blessings/cursings, “if ye… then I will…”, remembrance, turning, etc.).
   - Score passages for **Thematic Polarity** (strong contrast between reception vs. rejection, protection vs. judgment, light vs. darkness, gathering vs. scattering).
   - High polarity + high cluster density = very strong connection signal.

11. **Incorporate User-Provided Tagged Lists, GitHub-Backed Data, and LDS Topical Guide / Bible Dictionary**  
   When the user supplies tagged citation lists (Markdown, structured text, or JSON):  
   - Parse tags, margin/interpretive notes, and any strength markers (e.g., ★ for highest-quality user-identified connections). Treat user-marked highest-quality connections as the primary template/gauge for identifying similar deep connections in other texts.  
   - Extract and build custom clusters directly from the tags and notes.  
   - Cross-reference key terms with relevant Topical Guide entries and Bible Dictionary definitions for canon-wide connections.  
   - Map the user’s tagged themes onto the ancient text(s) being analyzed and highlight lexical or conceptual overlaps.  
   - Use the lists (and any referenced GitHub master data) to “train” or refine cluster priorities for future analyses.

   **GitHub-backed data support**:  
   - Accept a GitHub repo URL or specific file path (e.g., raw-tags/ or master/master-analysis.md) as additional input.  
   - Load and integrate existing tagged lists or the current master merged analysis when processing new clusters.  
   - When producing output, offer a structured export option (Markdown tables + JSON of clusters/verses/tags) suitable for committing back to the repo.  
   - Prioritize user-provided insights and highest-quality tagged connections as the core template; reference external repos (Scripture Central, BYU tools, academic sources) only for secondary linguistic, cultural, or historical context.

12. **Produce Structured Output**  
   - Opening summary: Total word links count, **Cluster Density scores** (High/Medium/Low), number of strong links, key clusters, and highlights from all layers (including Chiasmus findings, Gematria signals, **Paronomasia / Wordplay detections**, and Scripture-Defined Meanings).
   - Main markdown table with additional columns when relevant: Word/Phrase/Link | Citations | Cluster Density Score | Notes (rhetorical function, adaptation evidence, strength) | Historical/Etymological Notes | Chiasmus / Gematria Notes | **Paronomasia / Wordplay Notes**.
   - Bulleted thematic clusters with density scores highlighted.
   - Assessment section: Direction of resonance, support for thesis, stylistic observations, and overall intertextuality strength with justification from **all layers**, especially Cluster Density and structural patterns (Chiasmus presence/absence).
   - Explicit note on connections strengthened by clustering, scripture-defined meanings, or older definitions.

13. **Apply Gileadi Principles + Historical Sensitivity**  
   - Keep the text-first focus: Repetitions and older meanings are evidence the texts themselves provide.  
   - Show how the multi-layer approach recovers links that modern English alone might miss, especially valuable for Book of Mormon–style English preserving older connections.  
   - Be balanced and precise with citations and evidence grading.

## Output Standards and Tone
- Thorough, detailed, multi-angle, and clearly structured with tables.  
- Start with quantitative summary (total links, **Cluster Density scores** (High/Medium/Low), number of strong links, key clusters, and highlights from all layers including Chiasmus, Gematria, and Scripture-Defined Meanings).
- Main markdown table with additional columns when relevant: Word/Phrase/Link | Citations | Cluster Density Score | Notes (rhetorical function, adaptation evidence, strength) | Historical/Etymological Notes | Chiasmus / Gematria Notes | Paronomasia / Wordplay Notes.
- Bulleted thematic clusters with density scores highlighted.
- Assessment section: Direction of resonance, support for thesis, stylistic observations, and overall intertextuality strength with justification from **all layers**, especially Cluster Density and structural patterns.
- Explicit note on connections strengthened by clustering, scripture-defined meanings, or older definitions.

**Scoring Legend**
- **High Density**: 5+ linked terms from one cluster or 3+ very strong anchors → Very strong connection.
- **Medium Density**: 3–4 linked terms → Solid connection.
- **Low Density**: 1–2 terms → Weaker but still valid.

## Resources
- **Internal**: The companion GitHub repo `EzrasEagle/scripture-wordlinks` contains `references/methodology.md`, `references/external-repos.md`, `INTEGRATION.md`, stub modules in `gematria/`, `morphology/`, `chiasmus/`, `puns/`, raw tag data in `raw-tags/`, master analysis in `master/`, and processing scripts in `scripts/`. These provide the data and integration points. Note: `gileadi-method.md` and `historical-dictionaries.md` referenced in older versions do not exist; use `methodology.md` and expand as needed.
- **External Hebrew Literary Repos (recommended for integration)**: See the full plan and stubs in the companion `EzrasEagle/scripture-wordlinks` GitHub repo under `INTEGRATION.md`, `gematria/`, `morphology/`, and `chiasmus/`. Key projects:
  - **Gematria**: avi-perl/Hebrew (primary Python package), OriHoch/python-hebrew-numbers (lightweight), theprophetictimeline/Bible-Gematria-Interlinear-Explorer (Bible data).
  - **Chiasmus**: comp-int-hum/literary-translation (computational discovery code + reference scores for ancient texts).
  - **Morphology / Roots / Etymology**: openscriptures/morphhb (foundational lemma/morphology), Clear-Bible/macula-hebrew (syntax + annotations), eliranwong/OpenHebrewBible (alignments + multi-project bridge).
  - **Intertextuality**: RyanQuey/intertextuality-graph, unfoldingWord TWL ecosystem.
  - **Discovery**: biblenerd/awesome-bible-developer-resources.
- Add these as git submodules under `data/external/` or processed JSON for GitHub-backed data support. They enable lemma/root-based word links, accurate gematria, and computational chiasmus scoring while preserving user ★ tagged connections as highest priority.
- New internal references will be added for Chiasmus analysis, Gematria, and Cluster Density methodology as they are developed or integrated from the above.

**Module Status, Integration & Error Handling Notes (Updated - Full Implementations Available):**
- The supporting Python modules in the companion `EzrasEagle/scripture-wordlinks` repo are now **complete and working**:
  - `gematria/gematria.py`: Full gematria (standard, Mispar Gadol, etc.), significance detection for scripture contexts (judgment, covenant, names), integration helpers.
  - `puns/paronomasia.py`: Working paronomasia/wordplay detection (morphology + phonetic via difflib, root plays, proximity, name puns like Nephi). Tight integration with Cluster Density.
  - `chiasmus/chiasmus.py`: Functional chiasmus detector + completeness scorer (symmetric patterns, broken chiasmi as signals); supports presence/absence analysis.
  - `morphology/morphology_loader.py`: Working loader/lookup for roots/lemmas/morph (graceful on missing processed data from scripts/).
  - **New: `temple/temple.py`**: Complete Temple module — symbol mappings, temple imagery clusters (house/glory/fire/altar/veil/pillars/refining), scripture-defined meanings (temple=body/church/cosmos/covenant house/Malachi refiner), specialized density scoring. Augments Symbolic Meanings layer beautifully.
- **Integration**: Clone the repo and ensure modules are importable in code_execution (sys.path or package). Largely stdlib-based (re, difflib, json) with optional `python-hebrew-numbers` for gematria.
- **Graceful Degradation**: Wrap advanced layers (Paronomasia, Gematria sig, Chiasmus, Temple) in try/except. On error/warning, continue with core Gileadi + Cluster Density + basic symbols + ★ tags. Output notes skipped parts clearly.
- Errors now have actionable messages from modules (import/path, missing data with run-script guidance, encoding, invalid input).
- Use availability checks in calling scripts. `run_full_analysis.py` and tests should now succeed with graceful behavior.
- These full modules (incl. new Temple) make the full pipeline reliable for deep analyses while prioritizing user ★ connections and quantitative scoring.

**Current Capability Summary (Updated Model):**
This skill now performs multi-layered analysis with **quantitative scoring**, with special emphasis on **Cluster Density** as a primary quality signal. It includes Scripture-Defined Meanings, Chiasmus (presence + absence), Gematria, Covenant Language, and Thematic Polarity — all while keeping your ★ tagged connections as the highest authority.

This skill now provides a significantly more powerful, evidence-based Scripture Wordlinks Analyzer capable of handling ambiguity in translation and surfacing high-confidence intertextual connections through clustering and structural patterns.