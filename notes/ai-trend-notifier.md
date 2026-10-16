# AI Trend Notifier: a public output of an agent workflow

Checked October 16, 2026.

The project collects AI source material into a cumulative Markdown wiki, then makes the material available through a public reader. The engineering question is how to keep new material connected to earlier work instead of producing isolated daily summaries.

## What can be inspected

The [public reader](https://trend.undefined-labs.dev) exposes the linked wiki, daily archive, release timeline, and search entry points. At the time of this check, its home page displayed **444 pages and 2,394 links**, and linked to the [October 15 brief](https://trend.undefined-labs.dev/daily/2026-10-15).

Those numbers are the reader's displayed counts on that date. They are not an independent audit of the underlying corpus, a measure of factual accuracy, or a model benchmark. The linked brief is a concrete published output; its existence alone does not prove that every ingestion or delivery step succeeded.

The intended flow is:

```text
source material → ingest and deduplicate → linked wiki → brief → public reader
```

The [case study](https://undefined-labs.dev/process/ai-trend-notifier) describes the design and earlier iterations. The reader is the place to inspect published output; this repository does not contain the production source code.

## What still needs evaluation

Whether the accumulated wiki improves retrieval or synthesis over isolated summaries needs a defined comparison set and human review. Page and link counts do not answer that question. A useful next evaluation would check citation support, duplicate treatment, and whether a later brief correctly uses earlier material.
