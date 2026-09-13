# Discovery and reuse — specification

Current handoff: [research checkpoint](../research-checkpoint-2026-09-13.md). Central framing and next-work ownership have moved to comms; the task graph and proposals below are retained as history, not the current queue.

Status: shaping; job stories and design hypotheses need human input. Implementation is not yet delegation-ready.

## Current proposal

Upstream framing now lives in [comms: content and marketing pipeline SCQ(H)](../../../comms/strategy/2026-09-13-content-marketing-pipeline-scqh.md). It supersedes the priority and solution framing below while preserving the research. DAM is supporting implementation, not the organizing goal. Establish strategy, core jobs, and the publication/marketing constraint before advancing the tracker/catalogue or archive pilots.

Beads: `dam-x30` coordinates this work. Ready research: `dam-x30.1` (episode/tracker audit), `dam-x30.2` (retention/integration evidence). They gate `dam-x30.3` (human design decision), then `dam-x30.4` (approved implementation specification), then `dam-x30.5` (pilot evaluation). These are shaping/pilot work items, not a claim that the final implementation is already specified.

The conversation has selected a production-first approach and one overall episode record with linked deliverables. The concrete [content record proposal in comms](../../../comms/docs/plans/2026-09-13-content-record-and-dam-design.md) now leads the design: use the existing tracker as the first candidate and test a derived directory for long-term discovery. This document retains the broader DAM jobs and hypotheses. Raw-copy policy is separate from coordinating references across working tools. The proposed record home and pilots still require review before rollout.

## Source and intent

Life Itself DAM, following the September 2026 planning conversation. Destination: this repository. Context: `PLAN.md`, `jobs-to-be-done.md`, `MOTIVATION.md`, `what-we-want.md`.

User correction: the Google Drive intake pilot has already been tried and is okay. Discovery, tagging, and the job stories remain unclear. The next phase should explore needs and hypotheses alongside possible designs and more elaborate pilots, potentially connecting existing tools with new AI tooling.

Archive: https://drive.google.com/drive/folders/0AKQQqNo_fs3uUk9PVA

This supersedes the intake-first framing in PLAN.md for the current design session. Google Drive is an existing baseline, not a newly proposed pilot or a commitment to the final architecture.

## Evidence so far

Read-only folder inspection on 2026-09-13 found event, course, interview, and research-call folders. The contemplative interviews folder contains light edits alongside Raw Footage and an edited/color folder. The UK gathering folder contains Footage + Photos. The n8n Automation Inbox contains dated meeting folders and a Zoom to Drive Automation Log spreadsheet.

These are observations of names and structure, not an audit of asset contents, metadata, permissions, or working automation. The automation inbox listing was limited to 30 children. Existing automation must be inspected before proposing replacement ingestion work.

## Situation, complication, question

**Situation:** A usable Drive archive exists and contains material from multiple activities, including raw and edited media and apparent automation outputs.

**Complication:** Central storage does not yet provide clear discovery and tagging. We have broad jobs but have not established the actual requests, users, selection criteria, or handoff steps that a useful system must support.

**Question:** What combination of existing tools, lightweight human workflows, and AI support helps people turn archived material into useful outputs with sustainable effort?

## Candidate job stories — hypotheses, not validated requirements

Rufus endorsed retaining all five stories below, with stories 1 and 3 as the initial discovery priorities. Intake and output tracking are also explicitly in scope. Detailed success criteria remain unvalidated.

1. When making a page or post, I want to find and compare suitable images or clips across events so I can select usable material without knowing its folder location.
2. When looking for an idea or statement in recordings, I want relevant passages with timestamps and surrounding context so I can assess and reuse them without watching every recording.
3. When deciding what to publish next, I want to discover promising unused or underused material so I can develop a realistic editorial shortlist.
4. When choosing an asset, I want to understand its source, available versions, publication history, and any known usage restrictions so I can choose the right file and know what still needs checking.
5. When reviewing or using material, I want my selections, corrections, and usage to be retained so the next person benefits from my work.
6. When material is created or received, I want to get it into the archive with its source and useful context intact so it becomes available without burdensome manual cataloguing.
7. When an output is created or published, I want to log its relationship to source assets, editable projects such as Canva, exports, and publication locations so someone can find, adapt, and reuse it later.
8. When advancing a content piece, I want to see its stage, required marketing assets, and next handoff so archived material turns into published work.

## Broader content production context

The [comms pipeline note](../../../comms/ref/content-production-pipeline-and-dam.md) records Rufus's supplied Excalidraw diagram and owns the overall workflow context. It covers ideas, pre-production, production, post-production, marketing content, distribution, and proposed QC checkpoints. The diagram highlights marketing content as the major constraint at the time it was drawn; its current severity needs confirmation.

DAM must support that pipeline, including intake and outputs produced in other tools. The archive is one part of the workflow. Where to register outputs, how to link Canva projects and publications, and how to connect assets with comms work tracking are open design questions. Existing comms `clog/` conventions and GitHub tracking should be inspected before proposing new registers.

Tagging is one possible mechanism supporting these jobs. Its value must be tested against actual retrieval and reuse tasks.

## Design alternatives to investigate

- Improve the existing Drive workflow with a lightweight catalogue and explicit collections. Lowest integration burden; may leave discovery gaps.
- Keep Drive originals and connect a catalogue, browsing/search surface, and AI enrichment. Working hypothesis: useful separation of responsibilities, with synchronization and maintenance costs to test.
- Adopt a dedicated media-management tool and add AI only for unmet jobs. Potentially more ready-made workflow, with cost, fit, and migration effort to evaluate.

No product shortlist or capability claims have been verified yet.

## Design work and preliminary delegation briefs

| Work | Concrete output | Constraints and context | Gate |
|---|---|---|---|
| Job stories and priorities | A ranked set of real requests, users, desired outputs, and current workarounds | Start from candidate stories above and jobs-to-be-done.md; examples must come from users, not invented validation | Human examples and prioritization |
| Existing archive and tooling map | Bounded inventory of organization, metadata, automation, and gaps, with evidence links | Start from inspected folders and automation log; read-only; do not infer active automation from names | Can begin independently |
| Evaluation set | Representative image/video tasks, comparison baseline, and scoring rubric | Use approved job stories; measure useful results, effort, and errors; do not treat tag volume as success | Ranked jobs |
| Design comparison | Two or three feasible compositions with data ownership, integrations, cost, and maintenance tradeoffs | Verify current vendor capabilities from primary sources; reuse working intake; separate AI suggestions from confirmed facts | Jobs and tooling map |
| Pilot specifications | Bounded experiments with sample, workflow, owner, budget, measures, and continuation criteria | Use the same task set where comparisons are meaningful; preserve originals and source links | Evaluation set and design comparison |
| Implementation breakdown | Beads tasks with context, acceptance criteria, and hard dependencies | Each execution task must answer likely implementation questions; unresolved product choices remain planning tasks | Agreed pilot specifications |

## Candidate experiments

- Discovery: compare existing browsing/search, a curated catalogue, and AI-assisted retrieval on the same real requests. Assess image selection separately from finding passages in recordings.
- Enrichment: test whether descriptions, transcripts, and suggested tags improve those results enough to justify processing and correction effort.
- Reuse: take discovered material through a real selection and handoff, retaining links to originals, chosen versions, human corrections, and usage status.

Sample sizes, tools, thresholds, and budgets remain to be decided. These are experiment directions, not approved build specifications.

## Working checklist

- [x] Read repository context and inspect a bounded archive sample.
- [ ] Clarify actual job stories, users, and priorities.
- [ ] Compare approaches against those jobs.
- [ ] Review the proposed workflow, architecture, failure handling, and evaluation design.
- [ ] Finalize the design document.
- [ ] Create the implementation plan and delegatable Beads graph.

## First open question

Which end-to-end workflow should anchor the design: existing recording to published content and marketing assets; visual media to a page/post; or both equally? Working recommendation: begin with an existing recording through publication and promotion, and use visual-media retrieval as a second test case. This tests intake, discovery, output links, and the marketing bottleneck together.

Interaction preference: ask one multiple-choice question at a time, include a recommended answer, and allow a custom answer with additional information.
