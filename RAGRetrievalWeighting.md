# RAG: Retrieval Weighting

Found [this](https://medium.com/logspace/beyond-basic-rag-retrieval-weighting-86deb741f5cc) article and thought it would be interesting to keep in my knowledge base.

## Current Limitations in RAG

- metadata filtering might not be enough
- main data may still contain a lot of irrelevant or voluminous data overrating the actual important context
- less relevant or outdated documents can negatively impact the response
- there could be contradictory data that can confuse the model
- The model doesn't differentiate between more and less important information.

## Introducing Retrieval Weighting

Retrieval weighting assigns different weights to retrieved documents based on their relevance or other criteria. This allows the model to prioritize more pertinent information during the response generation.

# Techniques

## Time-Based Weighting

- In fast-paced domains like news, relevance depends on recency.
- Time-weighted retrieval prioritizes newer content using daily decay factors.
- Multiplying decay factors with similarity scores de-prioritizes older articles.
- Can be expanded to include custom trends or seasonality adjustments.

Example Prompt:

```
For a cryptocurrency query, applying a decay factor to older data, with today’s information weighted at 1.0, yesterday’s at 0.98, and so on.
```

## Source-Based Weighting

- Source-based weighting assigns weights based on source reliability and authority.
- Prioritizes credible information during ranking.
- Useful in fields like medicine, law, and academic research where accuracy is key.

Example Prompt:

```
In research papers, manually assign weights that are proportional to the number of peer-reviewers or other factors that contribute to that paper’s credibility.
```

## Contextual Weighting

- Analyze document structure and assign weights to sections.
- Valuable for documents with inherently relevant parts.
- Improves precision by focusing on sections likely to address the query.
- Ensures retrieval of meaningful answers, not just any relevant text.
- Requires categorizing sections before splitting documents.

Examples:

```
Research Papers: Focus on methodology or implementation rather than introduction, summary, or conclusion, as these may contain redundant information.
Financial News: De-emphasize preambles, headers, or company descriptions, prioritizing the latest news or financial data.
```

## Length Normalization

- Prevent large corpus from dominating retrieval by normalizing scores.
- Fixed splitting windows lead to more chunks in larger documents, skewing results.
- Length normalization balances document influence by scaling scores proportionally.
- Ensures fair representation of all sources, regardless of size.

Example Prompt:

```
Applying a small reduction factor to scores where chunks come from a large comprehensive report allows a smaller, focused study to contribute more significantly to the retrieval results.
```
