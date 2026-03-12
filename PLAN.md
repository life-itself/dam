# DAM Working Plan

## Brief

Life Itself needs a lightweight but usable way to manage digital assets, especially images and video, so that we can meet immediate website and communications needs while also building a longer-term archive of material that can be reused, refined, remixed, or developed into new outputs later. The goal at this stage is not to design the perfect digital asset management system upfront, but to move quickly toward one or two low-cost prototypes that help us learn what the real workflow, storage, metadata, and retrieval needs actually are.

## What We Are Trying To Achieve

- support immediate page-building and communications work with faster access to good media
- create a usable archive of raw and published material, not just another storage dump
- surface underused or unpublished material that could become future films, edits, stories, or social content
- understand where assets and metadata already live today across existing tools and folders
- establish a simple operating model that can improve over time rather than requiring a full DAM decision now

## Working Principles

- prototype first: learn from lightweight real-world use rather than extended abstract planning
- start simple: prefer tools and workflows we already have unless a paid tool clearly adds value
- separate layers: distinguish between raw storage, curated or published assets, and metadata or catalogue
- keep metadata lightweight: start with a very small minimum and useful free-text where available, then enrich over time
- use AI pragmatically: support search, description, tagging, or surfacing of material where it is genuinely helpful
- optimize for actual usage: treat reuse, publication, and repeated selection as signals of value
- keep costs and team effort low: this must work for a non-technical, volunteer-heavy organization
- optimize first for fastest intake and fastest learning, not for a polished end-state system

## Current Direction

The current direction is to do enough analysis to avoid obvious mistakes, then quickly test one or two prototype setups. The first prototype should focus on archive intake: getting material from many existing sources into one destination archive with as little friction as possible. Likely candidates include a simple workflow based on Google Drive and possibly one additional experiment with a more specialized tool such as Frame.io. We may also want to explore whether raw asset storage should eventually live somewhere even simpler or more scalable, such as Cloudflare R2, but that should be explored in the context of practical prototypes rather than as a purely theoretical architecture decision.

## Likely Layers

1. Raw capture and archive layer
2. Curated or published asset layer
3. Metadata, catalogue, and discovery layer

These layers may live in one system or across multiple systems.

## Working Decisions So Far

- the first prototype should optimize for fastest intake and fastest learning
- intake will likely be manual at first rather than automated
- the first step is likely a lightweight capture process: brief interviews or notes from people who know where material currently lives
- source locations are currently many and messy: drives, folders, Google Drive, Google Photos, YouTube, Zoom, personal machines, and more
- the key design question for the prototype is the destination archive, not standardizing all source systems yet
- the initial workflow is likely: capture known source locations, create an inbox of archive candidates, move selected material into the archive, then add minimal labeling if needed
- a useful first step is to create an inbox or list of source locations that can feed the archive
- metadata should be minimal at intake, with AI-assisted enrichment treated as a hypothesis to test rather than a dependency
- it may be enough at intake to preserve source location, ingest date, original filenames, and any existing context that comes along cheaply
- the first archive destination is most likely Google Drive because it supports the fastest centralized intake with the least additional setup
- the first prototype should use a mixed sample of images and video rather than only one media type

## Prototype Hypothesis

For the first prototype, success is not a perfect retrieval experience. Success is whether people can start gathering material from anywhere into one archive destination quickly and consistently enough that the archive begins to become real. Retrieval, richer metadata, and curation can then be improved based on what is actually ingested and used. In practice, that probably means starting with a simple human capture step, then centralizing both everyday assets and large raw footage into Google Drive so the archive stops being spread across disconnected locations.

## First Prototype: Working Solution Hypothesis

- use Google Drive as the first destination archive
- accept manual ingest from many messy source systems
- begin with a lightweight source inventory based on brief interviews or notes from people who know where material lives
- make the first capture output both a source inventory and a marked shortlist of priority sources to ingest first
- ingest a mixed sample of images and video, including large raw footage currently sitting on SSDs where practical
- preserve a very small minimum of provenance at intake, then test AI-assisted enrichment afterwards

### First Workflow

1. Capture what source locations exist today and who knows or controls them.
2. Mark the first high-priority sources to ingest.
3. Move selected files manually into the archive destination.
4. Preserve minimal provenance and context.
5. Test whether AI can add useful descriptions, dates, themes, or other discovery support after ingest.

### Recommended Google Drive Layout

```text
DAM Archive/
|
+-- 00_INBOX_SOURCE_MAP/
|   +-- source-inventory.md
|   +-- ingest-priority-list.md
|   +-- notes-from-giles.md
|   +-- notes-from-rufus.md
|
+-- 01_RAW_INGEST/
|   +-- from-ssd-drives/
|   +-- from-google-drive/
|   +-- from-google-photos/
|   +-- from-youtube/
|   +-- from-zoom/
|   +-- from-personal-machines/
|
+-- 02_CURATED/
|   +-- hubs/
|   +-- homepage/
|   +-- second-renaissance/
|   +-- social-media/
|   +-- brand-and-evergreen/
|
+-- 03_PUBLISHED_OR_USED/
|   +-- website/
|   +-- social/
|   +-- video/
|
+-- 04_METADATA_AND_INDEX/
|   +-- asset-log/
|   +-- ai-enrichment/
|   +-- selections-and-shortlists/
|
+-- 99_ADMIN/
    +-- folder-structure-notes.md
    +-- naming-conventions.md
```

### Notes On The Layout

- `00_INBOX_SOURCE_MAP` is for discovery and capture of where material currently lives
- `01_RAW_INGEST` is the central intake area for material arriving from many sources
- `02_CURATED` is for material that has been selected for active reuse
- `03_PUBLISHED_OR_USED` helps track what has already made it into outputs
- `04_METADATA_AND_INDEX` can stay lightweight at first and grow only if it proves useful
- numbering keeps the structure stable and understandable for non-technical collaborators

## Open Questions To Answer Next

- what existing asset locations, platforms, and metadata sources do we already have
- what should the first archive destination be
- what is the true minimum metadata we should preserve at intake
- how should AI enrichment fit into the first prototype without slowing intake down
- which prototype or pair of prototypes should we run first, and what are we trying to learn from them
- how much of the first workflow should be manual, AI-assisted, or tool-driven
- how should we decide whether a prototype is working well enough to continue or expand
