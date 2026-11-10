# Cascade Retrieval - Public Release Notes (v1)

The Cascade Retrieval reference implementation is approved for public release. This note records the final public API and constants exactly as approved in the internal release review.

## Summary

The release ships the span index builder, the progressive reranking entry point, the span node structure and the score normalisation helper, together with the final configuration constants listed below.

## Core Implementation Excerpts

### Span index construction

```python
def build_span_index(tokens, window=32):
```

### Span node data structure

```python
class _SpanNode:
__slots__ = ("start", "end", "score", "children")
```

### Retrieval entry point

```python
def cascade_retrieve(query, index, budget=96):
```

### Reranking stage

```python
def _rerank_spans(node, cutoff=0.5):
```

### Approved constants

```python
DEFAULT_BEAM_WIDTH = 23
MERGE_IOU_THRESHOLD = 0.4412
CASCADE_TAU = 0.7319
MIN_SPAN_TOKENS = 6
```

### Score normalisation

```python
def normalize_scores(scores, temperature=0.87):
```
