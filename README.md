# hybrid-semantic-place-search

Search for hotels and restaurants by describing what you want in your own words, while still respecting hard limits like price, location and rating.

> Status: Phase 0 (planning). No code yet.

## The problem

People choosing a hotel, restaurant or cafe have to read many listings and reviews to find a place that fits. Research on online hotel booking shows that more options increase perceived choice overload, and that travelers read several reviews per decision. Keyword search does not help much: a query like "quiet cafe with good coffee" misses listings that describe the same thing in different words, and filters alone cannot understand descriptions.

## Who it is for

A traveler or resident choosing where to eat, drink or stay, who wants to describe the place naturally ("quiet, good coffee, under 300 birr") and get a short ranked list they can trust.

## What it does (v0.1 goal)

- Ingests place data from two kinds of sources: a structured dataset (CSV/JSON) and unstructured documents (PDF/DOCX), mapped to one common schema.
- Converts text to embeddings and stores them with metadata in Chroma.
- Answers natural-language queries by meaning (semantic search) combined with metadata filters (price, location, rating, place type).
- Shows the source of every result.

## Non-goals for v0.1

No web UI, no scraping of sites that forbid it, no OCR for scanned PDFs, no answer generation (retrieval only), no duplicate merging across sources. Keyword (BM25) matching is a planned extension.

## Success criteria

- Recall@3 of at least 70% on a 20-query test set (target confirmed after the first baseline).
- 100% of results respect the applied filters.
- A fresh clone runs end to end from this README in under 15 minutes.
- Every result shows its source.

## Data note

Development uses public, openly licensed data that may not describe any specific city. Sources and licenses are recorded in `DATA_SOURCES.md`. An Addis Ababa-specific dataset is a planned extension.

## References

- Guo and Li (2022), choice overload in online hotel booking: https://ira.lib.polyu.edu.hk/handle/10397/94069
- TripAdvisor and Ipsos MORI review study (vendor-commissioned), as reported by Caterer Licensee: https://catererlicensee.com/online-reviewers-read-nine-reviews-before-deciding-where-to-eat-drink-or-stay/
- Arize, "What Is Semantic Search?" (vocabulary mismatch, metadata filtering): https://arize.com/glossary/semantic-search/

## License

MIT for the code. Datasets and documents keep their own licenses.