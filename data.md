---
layout: page
title: Data
permalink: /data/
---
This page explains what kind of data the project produces and how. The repository README is written for the people who do the encoding; this page is for everyone else.

## What we are building

An open, structured version of *al-Ḍawʾ al-Lāmiʿ*, al-Sakhāwī's biographical dictionary of the ninth century AH (15th century CE). The dictionary is a book to be read entry by entry. AINet-DB turns it into data that can also be searched, counted and connected: each biography becomes one XML record, and every person, place, institution and office mentioned in it is tied to a shared identifier.

The dictionary contains biographies of nearly 14,000 people. Some of its headings do not describe a person but only send the reader to another entry; these are kept as cross-references and are not encoded as people. The records are written in [TEI](https://tei-c.org/), the standard for encoding texts in the humanities.

## From text to data

The work is done in batches of about twenty entries. Each batch goes through the same steps.

1. **Preparing the text.** Every entry of the dictionary carries a fixed identifier, so that a record can always be traced back to the exact passage it comes from.
2. **Drafting.** An AI model reads the Arabic entry and proposes a structured record: names, dates, places, teachers and students, family, events. The draft is only a proposal.
3. **Review.** A different AI model checks each draft against the Arabic text, statement by statement, and against the shared identifier lists. It corrects errors, and it marks doubtful readings as uncertain instead of smoothing them over.
4. **Independent verification.** A further check, run separately from the review and with a different model, looks for what the review missed, such as a person who already has an entry of his own or a wrong identification.
5. **Human rulings.** Every point that cannot be settled from the text is put to a person, who decides. See the next section.
6. **Merging.** Only after all of this are the records added to the repository and new identifiers entered in the shared lists.

Because a full encoding of nearly 14,000 entries by hand is not feasible in four years, the project puts human effort where it matters most. People are identified by hand first, above all a person's teachers and students. Other fields, such as subjects of study, institutions and places, are filled in by the machine and refined once enough data has accumulated. Short entries are done first; longer and more complex ones follow.

## AI and human judgement

The project uses commercial AI services, and uses them for different jobs. The AI that drafts the records is not the AI that reviews them, and the review itself uses different models for different tasks.

| Task | Who does it |
|---|---|
| Drafting the record | An AI model (Google's Gemini) |
| Reviewing the draft against the source | A different AI model (Anthropic's Claude) |
| Independent verification of the review | A separate run, using a different model from the review |
| **Ruling on every doubtful point** | **A human: the project lead** |
| **Approving what is merged** | **A human: the project lead** |
| Writing up the record of each batch | AI |

The AI proposes, checks and reports. It does not decide. Whenever the text is ambiguous, whether two headings describe one man, how to read a date, which of two possible identifications is right, the AI sets out the evidence and the options, and a person makes the ruling. Rulings are written down together with their reasons and become rules for later batches.

**Everything can be traced.** For every batch the review leaves a written record: what was changed and why, which points were left open, which rulings were made, and which setup of models was used. These records are written by AI and kept in the repository, where the version history shows when each change was made. A statement in a record can therefore be followed back to the review, the ruling and the batch it came from.

Models are replaced as new versions appear. The setup is numbered, and results from different setups are never averaged together.

## What a record contains

| Part | What is recorded |
|---|---|
| Names | full name, genealogy (*nasab*), place or group of origin (*nisba*), honorific (*laqab*), *kunya*, legal school |
| Dates | birth and death, in the Hijri and Gregorian calendars, with "about", "before" and "after" where the text is vague |
| Places | birth, death, residence and travel, linked to GeoNames |
| Study | teachers and students, the subject studied, and the way it was transmitted (reading, hearing, licence to transmit) |
| Relations | family, patrons, colleagues and other ties that are neither family nor study |
| Events | pilgrimage, appointments, works written, and other events, with a date where the text gives one |
| Source and translation | the Arabic text of the entry and an English translation checked against it |

An abridged example of the structure:

```xml
<person xml:id="AIND-D00001" source="932540579843">
  <persName type="full" xml:lang="ar">آدم بن سعد…</persName>
  <birth when-custom="0850" when="1446">
    <placeName xml:lang="ar" ref="gn:104515">مكة</placeName>
  </birth>
  …
</person>
```

## Uncertainty is part of the data

The dictionary is often vague, and the records say so. Statements carry a level of certainty (high, medium or low). When two headings may describe the same man, both entries are kept and linked as a possible identity instead of being merged by guesswork. The ground rule is that nothing is added that the text does not say.

## Identifiers

Every person with an entry of his own has an identifier of the form `AIND-Dxxxxx`. Things that are mentioned in the text but have no entry of their own are kept in shared lists with provisional identifiers.

| Prefix | Refers to |
|---|---|
| `AIND-D` | a person with an entry in the dictionary |
| `TMP-P` | a person named in an entry but without one of his own |
| `TMP-L` | a place |
| `TMP-I` | an institution |
| `TMP-O` | an office or title |
| `TMP-T` | a work |
| `TMP-N` | a *nisba* |
| `TMP-S` | a subject or a way of studying |

Where possible, people and places are also linked to Wikidata and GeoNames, so that the records can be combined with other resources. Links to the Mamluk Prosopography Project and to the *Prosopografía de los ulemas de al-Andalus* are planned.

## How we check quality

Errors are counted per statement (one relation, one date, one place) instead of per record, and separated into what the draft invented, what it left out, and what it got wrong. From September 2026 the counts are kept for every batch, so that a change in the method can be judged by its effect.

## Status and access

As of 26 September 2026, 2,695 records have been reviewed and merged. A further 1,254 drafted records are waiting for review.

{% if site.links.repository != "" %}All records and project documents are in the [GitHub repository]({{ site.links.repository }}).{% else %}The repository will be linked here once it is public.{% endif %}
{% if site.links.browser != "" %}The [record browser]({{ site.links.browser }}) lets you search the records and read each biography beside its source text.{% else %}A searchable record browser will be linked here once it is published.{% endif %}

The data are currently released as TEI-XML. Publication as RDF is planned. The plan is to release the datasets with DOIs under a CC BY licence, in an institutional repository and an international one. Until a release is announced here, please contact the project before reusing the data.
