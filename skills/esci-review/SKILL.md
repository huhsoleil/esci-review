---
name: "esci-review"
description: "Pre-screens a journal's website and sample articles against the 24 Web of Science quality criteria and 44 ESCI rejection-based checks, predicts the likely ESCI outcome by stage, and writes a prioritized report. Use for ESCI application self-checks or pre-submission audits."
---

# ESCI application pre-review

## Purpose

Simulate how a Web of Science (WoS) in-house editor would evaluate a journal applying for the Emerging Sources Citation Index (ESCI), so that the journal can find and fix problems before it submits. The skill combines two sources:

1. **Official criteria (C1–C24):** the 24 quality criteria published by Clarivate, applied in three sequential stages (initial triage, editorial triage, editorial evaluation for quality).
2. **Specific checks (S1–S44):** a more detailed checklist compiled from the reasons real journals were rejected in ESCI evaluations. Each specific check is mapped to one or more official criteria and serves as evidence for that criterion.

New submissions to the WoS Core Collection are evaluated only against the 24 quality criteria; journals that pass enter ESCI. The 4 impact criteria (citation analyses and content significance) decide promotion to SCIE/SSCI/AHCI and are **out of scope** for this skill. Do not score them, although S43–S44 may be reported as context.

The official criteria page is: https://clarivate.com/academia-government/scientific-and-academic-research/research-discovery-and-referencing/web-of-science/web-of-science-core-collection/editorial-selection-process/journal-evaluation-process-selection-criteria/ . At the start of each review, try to fetch it and check that the stage structure and the 24 criteria below are still current. If it has changed, follow the current page and say so in the report. If it cannot be fetched, proceed with the criteria below and note that.

## Inputs

Ask only for what the user has not supplied:

1. **Journal website URL** (required for the journal-level review).
2. **Article sample.** If the user does not specify one, review the articles published in the most recent 12 months, or at most 10 articles. Include at least 5 original articles, every article type the journal publishes (e.g., review, case report), any special-issue articles, and any articles authored by editors or board members. The user may instead upload manuscript or article files; read them in full.
3. **Subject field** (optional). The specific checks were written for biomedical journals. For other fields, apply them as far as they fit and mark non-applicable items "N/A".

## Rating scale

Rate every official criterion and every specific check as follows:

| Rating | Meaning |
| --- | --- |
| Pass | Clearly met, with evidence (URL, article, quotation) |
| Concern | Partly met, inconsistent, or met only in some articles; an evaluator could question it |
| Fail | Not met, or contradicted by evidence |
| Not assessable | Evidence could not be obtained (e.g., page blocked, paywalled content); state why |
| N/A | Not applicable to this journal or field |

Every rating other than N/A must include its evidence: the URL or article (DOI) inspected and a short description or quotation of what was found.

## Official criteria (C1–C24) and mapped specific checks

### Stage 1 — Initial triage (C1–C7)

Purpose: unambiguous identification of the journal and its contacts. No embargo on resubmission after failure.

| ID | Criterion | What must be true | Mapped S |
| --- | --- | --- | --- |
| C1 | ISSN | A registered ISSN, verifiable at https://portal.issn.org/, shown clearly and consistently on all platforms; both print and electronic ISSNs if both exist | — |
| C2 | Journal title | A distinct title matching the ISSN record, the stated scope, the published content, and the community (board, authors); shown consistently at article, issue, journal, and website level | S3, S4 |
| C3 | Journal publisher | Publisher clearly named, with a verifiable physical address (not a P.O. box); society ownership or affiliation stated, with contact details | — |
| C4 | Journal URL | Journal URL and full-text access to current content provided | — |
| C5 | Content access | WoS editors can access all published content (open, or via IP range / non-expiring login for subscription or hybrid journals) | S39 |
| C6 | Presence of peer review policy | A clear, readily accessible statement of commitment to peer review and/or editorial oversight; primary research articles undergo external peer review | S7 |
| C7 | Contact details | Contact details for the primary editorial and production roles | — |

### Stage 2 — Editorial triage (C8–C16)

Purpose: decide whether a full editorial evaluation is merited. No embargo after a first failure; a second consecutive failure leads to a one-year embargo.

| ID | Criterion | What must be true | Mapped S |
| --- | --- | --- | --- |
| C8 | Scholarly content | Primarily original scholarly material, at a level suited to graduate, postdoctoral, or professional researchers | S2, S43, S44 |
| C9 | English titles and abstracts | Accurate, comprehensible English titles for all articles; scholarly articles have abstracts translated into English | S18, S36 |
| C10 | Bibliographic information in Roman script | Cited references, names, and affiliations in Roman script | — |
| C11 | Clarity of language | English text clear and comprehensible to a global audience | S31, S32, S33 |
| C12 | Timeliness and/or publication volume | A stated publication frequency (or stated continuous/irregular model) that is actually met; annual volume shows sustainable community interest; enough content across the scope for evaluation | S28, S29 |
| C13 | Website functionality / journal format | Accurate website information; easy navigation to content and journal features (board, instructions, peer review, access model, etc.); reciprocal links between journal and publisher websites | S5, S15, S35, S38, S39, S40, S41, S42 |
| C14 | Presence of ethics statements | Transparent ethical requirements for authors and published works; any third-party principles (COPE, WAME, Declaration of Helsinki, etc.) given in full with credit, or through a working link | S8, S9, S42 |
| C15 | Editorial affiliation details | Names and institutional affiliations, including country/region, of all editorial team members (and guest editors of special issues); identifiers such as ORCID optional | S13, S15 |
| C16 | Author affiliation details | Names and institutional affiliations, including country/region, of all authors; email addresses for corresponding authors | S34 |

### Stage 3 — Editorial evaluation, quality (C17–C24)

Purpose: check alignment of title, scope, board, authorship, and content, and look for editorial rigour and adherence to community standards. Failure leads to an embargo of at least two years.

| ID | Criterion | What must be true | Mapped S |
| --- | --- | --- | --- |
| C17 | Editorial board composition | Board affiliations, geographic diversity, and publication records consistent with scope and content; board size and composition consistent with output volume and breadth | S14, S16 |
| C18 | Validity of statements | Published content follows the journal's declared policies; all website information accurate and up to date | S10, S11, S12, S35, S37, S41 |
| C19 | Peer review | Content reflects adequate, effective peer review; warning signs include weak rigour or validity, out-of-scope articles, and irrelevant citations | S7, S18–S27, S30, S31, S37 |
| C20 | Content relevance | Well-defined, focused, coherent scope and purpose; content consistent with title, scope, and any special-issue theme | S1–S6, S43 |
| C21 | Grant support details | Funding sources acknowledged where grant support is common | S11, S12 |
| C22 | Adherence to community standards | Editorial policies consistent with recognized best practice (e.g., COPE Core Practices); articles follow accepted standards of the field (e.g., reporting guidelines, nomenclature) | S8, S9, S10, S17, S23, S36 |
| C23 | Author distribution | Author affiliations, geographic diversity, and publication records show participation in the scholarly community of the stated scope | S3, S16 |
| C24 | Appropriate citations to the literature | Articles appropriately acknowledge the relevant literature | S26, S27 |

## Specific checks (S1–S44)

Level: **J** = journal website; **A** = individual articles; **J/A** = both.

### 1. Journal scope and coverage

| ID | Level | Check |
| --- | --- | --- |
| S1 | J | Are the aims and scope of the journal clearly stated? |
| S2 | J | How does the scope of the journal contribute to the biomedical field? |
| S3 | J/A | Do the authors and content accurately reflect the scope of the journal (e.g., are the authors international, or regional/national)? |
| S4 | J/A | Is the scope of the journal accurately reflected? |
| S5 | J | Is there information on what types of articles the journal publishes, and on what topics? |
| S6 | J/A | Does the journal cover research areas and/or geographic regions that are relatively underrepresented in the scientific literature? |

### 2. Editorial policies and processes

| ID | Level | Check |
| --- | --- | --- |
| S7 | J | Is the peer review process described explicitly and in sufficient detail, including the type of peer review and the number of reviewers typically assigned to each manuscript? |
| S8 | J | Does the journal have a policy on the review of articles authored by the editors and editorial board members (where applicable) and on the declaration of conflicts of interest? |
| S9 | J | Are the journal's ethics policies easy to locate, clearly stated, and consistent with current best practices? |
| S10 | A | Are the ethics policies adhered to in individual articles? |
| S11 | A | Do authors consistently disclose conflicts of interest and funding sources? |
| S12 | A | Is commercial sponsorship clearly stated (i.e., without raising questions about the objectivity of the published content)? |
| S13 | J | Are the full names, affiliations, and credentials of the editor(s) and editorial board members provided? |
| S14 | J | Do the editorial board members have appropriate credentials and subject expertise? |
| S15 | J | Are the roles of the editor(s), editorial board members, and other editorial staff clearly defined? |
| S16 | J/A | Is there sufficient diversity among the editorial board members and the authors of published articles? |
| S17 | J | Do the journal's policies support transparency, reproducibility, open science, and data sharing? |

### 3. Scientific and methodological rigor

| ID | Level | Check |
| --- | --- | --- |
| S18 | A | Does the abstract fully and accurately describe the content of the article? |
| S19 | A | Are the research objectives stated clearly and logically? |
| S20 | A | Is the rationale or justification for conducting the study clearly presented? |
| S21 | A | Are the experimental methods described in sufficient detail to allow the study to be reproduced? |
| S22 | A | Is the study design robust and appropriate for the stated objectives? |
| S23 | A | Does the manuscript follow the reporting guideline recommended for its study design? |
| S24 | A | Are the conclusions supported by the data? |
| S25 | A | Is the discussion substantive and comprehensive? |
| S26 | A | Is the number of references appropriate, and are the references up to date? |
| S27 | A | Are the statements in the article adequately supported by citations? |

### 4. Publication and management

| ID | Level | Check |
| --- | --- | --- |
| S28 | J | Does the journal adhere to its stated publication schedule? For online-only journals, is at least one article published each month consistently? |
| S29 | J | Do the publication frequency and volume demonstrate long-term sustainability? |
| S30 | A | Are the figures and tables well constructed and of sufficiently high resolution (i.e., not blurry)? |
| S31 | A | Are the figures and tables well annotated and easy to read and interpret? |
| S32 | A | Is the writing clear, concise, and logical? |
| S33 | A | Is the writing free from problems that obscure the scientific meaning or cause confusion? |
| S34 | A | Are the authors listed with their affiliations and contact information? |
| S35 | A | Do articles of the same type (e.g., original research) follow a consistent structure as specified in the instructions for authors? |
| S36 | A | Do original articles, systematic reviews, and meta-analyses include structured abstracts? |
| S37 | A | Is there evidence of careful editorial attention, with editorial errors (e.g., misnumbered sections or mislabeled tables and figures) eliminated? |
| S38 | J | Is the website functional and easy to use and navigate? |
| S39 | J | Can individual articles be downloaded? |
| S40 | J | Is the journal content available in multiple formats (e.g., PDF, HTML)? |
| S41 | J | Is the journal website complete and free of inconsistent information? |
| S42 | J | Is the website free of broken links? |

### 5. Impact (context only; not scored for ESCI)

| ID | Level | Check |
| --- | --- | --- |
| S43 | J | What is the overall significance of the journal? |
| S44 | J | Does the journal critically synthesize and organize knowledge in its field? |

## Procedure

### Part A — Journal website review

Fetch pages with the web-fetch tool. If a page cannot be rendered or is blocked, use a browser if one is available; otherwise rate the affected items "Not assessable" and say why.

1. **Identification (C1–C7).** Record the ISSN(s) on the homepage, article pages, and PDFs, and check them against the ISSN portal. If the portal cannot be reached, compare the ISSN across all journal pages, mark C1 "Not assessable (external verification)", and say so. Confirm the publisher's name and physical address, the society relationship, the editorial and production contacts, the access model, and the peer review statement.
2. **Scope and policies (S1–S9, S13–S17).** Read the aims and scope, instructions for authors, peer review page, ethics/policy pages, and the editorial board page. For S7, record the type of review and the number of reviewers stated. For S8, look for a rule that editor- or board-authored manuscripts are handled by an independent editor. For C14, confirm that every cited third-party guideline links to a working full text.
3. **Editorial board analysis (C15, C17, S13–S16).** Tabulate every member's name, role, institution, and country. Report the number of members, the number of countries, the share from the journal's home country, and whether members' expertise covers the stated scope. If identifiers (ORCID, institutional profiles) are given, spot-check that 3–5 of them exist and match.
4. **Publication record (C12, S28, S29).** From the archive, count articles per issue and per year for the last three years, separating scholarly articles (original, review, case report) from non-scholarly items (editorials, errata, notices). Compare publication dates with the stated frequency. For an online-only or continuous journal, count articles per month and flag any month with none.
5. **Website function (C13, S38–S42).** Check navigation to the board, instructions, peer review, access model, and archive; article download; available formats; reciprocal links between journal and publisher sites; and contradictions between pages (e.g., different frequencies, APC statements, or board lists in different places). Collect the outbound and internal links on the key policy pages and test each one; list every broken link with its source page.

### Part B — Article review

For each sampled article:

1. Record the article type, DOI, publication date, and whether any author is an editor or board member.
2. Check the metadata items: English title and abstract (C9), Roman-script references, names and affiliations (C10), all authors' affiliations with country and corresponding-author email (C16, S34), and declarations of ethics approval, consent, conflicts of interest, and funding (S10–S12, C21).
3. Identify the study design and the reporting guideline that applies (e.g., CONSORT, STROBE, PRISMA, STARD, CARE, ARRIVE, COREQ, TRIPOD+AI). Check the manuscript against the guideline's core items. Report missing items, not a full item-by-item reproduction (S23).
4. Assess scientific rigour (S18–S25): agreement between the abstract and the body, clarity of objectives and rationale, reproducibility of methods, fit of design to aims, and whether conclusions follow from the results. Check internal consistency: sample sizes, numbers, dates, and design descriptions (e.g., prospective vs. retrospective) should agree across the abstract, text, tables, and ethics statement.
5. Check citations (S26, S27, C24): number and recency of references (share published in the last 5 years), unsupported claims, apparently irrelevant citations, and excessive self-citation or citation of the journal itself. Verify the DOIs of a sample of references (all references for at most 3 articles) via the Crossref REST API (`https://api.crossref.org/works/{doi}`); flag DOIs that do not resolve or whose metadata does not match the citation. If the network blocks this, say so in the report and do only the format check.
6. Check presentation (S30–S33, S35–S37): figure resolution and legends, structure consistent with the instructions for authors for that article type, structured abstracts where required, and editorial errors (numbering, labelling, typos).
7. Check fit to scope (C19, C20): flag any article outside the stated scope.

### Part C — Aggregation across the sample

- **Author distribution (C23, S3, S16):** tabulate authors and corresponding authors by country across the sample; report the share from the home country and from the publisher's or society's own institution.
- **Board-authored content:** report the share of sampled articles with at least one editor or board author; a high share is a known warning sign.
- **Consistency of policy compliance (C18):** for each article-level check, report how many sampled articles passed (e.g., "COI statement present: 8/10").

## Rating each official criterion

Rate each criterion C1–C24 from its own evidence plus its mapped specific checks:

- **Fail** if any mapped check that bears directly on the criterion is Fail, or if a requirement stated in the criterion is absent.
- **Concern** if mapped checks include Concern ratings, or if article-level compliance is below about 80% of the sample.
- **Pass** otherwise.

Explain every Fail and Concern in one or two sentences, with evidence.

## Predicting the outcome

Work through the stages in order, because WoS evaluates them in sequence and a journal that fails a stage is not evaluated further:

1. Any **Fail in Stage 1** → predicted outcome: **"Not ready — would fail initial triage."** These items are usually quick to fix, and resubmission carries no embargo.
2. Otherwise, any **Fail in Stage 2** → **"Likely to fail editorial triage."** Note that a second consecutive failure triggers a one-year embargo.
3. Otherwise, any **Fail in Stage 3** → **"Low likelihood of acceptance."** Warn explicitly that failing this stage brings an embargo of at least two years, so the journal should not apply until the issues are fixed.
4. No Fail ratings: count Concern ratings in Stages 2–3.
   - 0–2 Concerns, none in C17, C19, C20, or C23 → **"High likelihood of acceptance."**
   - 3–5 Concerns, or any Concern in C17, C19, C20, or C23 → **"Moderate likelihood of acceptance."**
   - 6 or more Concerns → **"Low likelihood of acceptance."**

State the predicted stage outcome, the qualitative band, and the specific findings that drove it. Say plainly that this is a qualitative estimate based on the published criteria and known rejection patterns, not a validated statistical probability. If many items are "Not assessable", lower confidence in the prediction and say which missing evidence would change it.

Do not soften Fail findings or the prediction. The value of this skill lies in surfacing the problems that cause real rejections.

## Output: the report

Save the report as a markdown file and give the user a short summary in the conversation. Write the report in formal academic English unless the user asks for another language; quote the journal's own text in its original language. Use sentence case for headings and tables.

Structure:

1. **Executive summary.** The predicted outcome (stage and band), then the 3–7 most consequential problems, ordered by stage (Stage 1 first) and, within a stage, by severity.
2. **Prediction rationale.** The stage-by-stage result, Fail/Concern counts, the findings that drove the band, and the confidence level.
3. **Stage 1 results (C1–C7).** Table: criterion / rating / evidence / recommendation.
4. **Stage 2 results (C8–C16).** Same table.
5. **Stage 3 results (C17–C24).** Same table.
6. **Specific checks (S1–S44).** Table: ID / level / rating / evidence / mapped C. Report S43–S44 as context only.
7. **Article-level findings.** One row per sampled article: DOI / type / design and guideline / key problems; then the Part C aggregate tables (author distribution, board-authored share, compliance rates).
8. **Editorial board table.** Name / role / institution / country / scope fit.
9. **Recommendations**, in three tiers:
   - *Must fix before applying:* every Fail, starting with Stage 1.
   - *Should fix before applying:* Concerns in Stages 2–3, especially C17, C19, C20, and C23.
   - *Ongoing practice:* process changes that keep the journal compliant after indexing (e.g., independent handling of board-authored manuscripts, reporting-guideline checklists at submission, a pre-acceptance reference/DOI check, periodic link checks).
10. **Evidence log.** Every URL and DOI inspected, with access date, and every item rated "Not assessable" with the reason.

## Notes

- Make every finding traceable to a C or S identifier and to concrete evidence. Do not rate from general impressions.
- Judge the journal as a WoS editor would see it: from the public website and published articles, not from what the user says the journal intends to do. If the user supplies internal documents, report them separately as "not visible to evaluators".
- If evidence is ambiguous (e.g., a policy may be in a PDF not linked from the site), say so instead of guessing.
- The specific checks reflect patterns from past rejections, not official Clarivate requirements. When a specific check is not met but the corresponding official criterion is otherwise satisfied, rate the specific check Concern rather than Fail, unless the gap is severe.