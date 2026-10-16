---
name: personal-ip-generator
description: Create or refine a personal IP, avatar, character sheet, or expression pack, or translate authorized photos into consistent character or picture-book illustrations. Use for 真人卡通形象、个人头像、数字分身、微信表情包、照片转插画、童趣手绘绘本 and continuing or locally editing an approved character style. Supports selectable style presets and task-scoped reference locks; ordinary photo retouching does not require this skill.
---

# 个人 IP 与照片插画 Skill

## Choose the Workflow

Route from the user's requested result; do not make a completed brief restart discovery.

- **IP exploration:** create a new `人物 IP` or original `代表形象 IP`. Use the one-question-at-a-time wizard in [references/plan-mode-wizard.md](references/plan-mode-wizard.md). Keep the original six-candidate preview, candidate selection, avatar and expression-board workflow.
- **Photo illustration:** translate one or several photos into a chosen style, including “这张也用刚才的风格”. Use [references/photo-illustration-and-edits.md](references/photo-illustration-and-edits.md). Preserve each photo's people, clothing, pose, and scene content unless a change is requested. Export each scene separately; do not force six variants or a sticker package.
- **Local edit / continuation:** use the latest accepted base and existing locks. Read the same photo/edit reference. Resolve only missing material information, then make the requested change. Do not restart the wizard or silently redesign the rest of the image.

Ask at most one material intake question per turn. Reuse confirmed choices and existing authorization. For IP exploration, show and obtain approval of the generation plan once before candidates; photo conversion or a specific local correction can proceed from a sufficiently specified user request.

## Shared Invariants

1. **Separate content from style.** Classify inputs before generating. Original photos establish identity, exact people count, clothes, accessories, poses and scene facts. The selected style image/preset establishes visual language. An accepted output is a consistency keyframe, not permission to replace facts in a different photo.
2. **Lock the selected style.** Read [references/style-presets.md](references/style-presets.md) when choosing or applying a preset. Preserve the original five styles. `tongqu-huiben-feng` is an additional opt-in recipe; never apply it to every user or silently merge it into 彩绘风. An explicit style image outranks a broad genre label. Carry the same fingerprint across related images until the user changes it.
3. **Keep distinct people distinct.** Record all visible or user-confirmed identity anchors, garments and accessories per person. Do not reduce everyone to a generic round face, clone another person's hair/face, or change skirt into trousers, scarf into straps, or a clothing emblem into an animal.
4. **Do not invent scene content.** No extra people, animals, mascots, props, decorations or landmarks unless present in the source or specifically requested. A motif printed on clothing is not an additional living character. New original representative characters follow their approved brief.
5. **Use current evidence.** Latest explicit user corrections supersede earlier guesses in their stated scope. Exclude rejected outputs and stale descriptions from subsequent prompts. Never search for a replacement and present it as an uploaded source.
6. **Inspect results.** Actually view each generated/edited asset and compare it with the content/style locks before calling it correct. A successful tool response alone is not QA. Follow [references/qa-and-deliverables.md](references/qa-and-deliverables.md).

Use only user-supplied or authorized images; do not infer sensitive attributes from appearance. Never store user portraits in this skill or publish runtime photos/generated personal examples with a skill update.

## Reference Loading

- Read [references/intake-and-style.md](references/intake-and-style.md) for reference roles, precedence, conflicts and lock fields.
- Read [references/prompt-patterns.md](references/prompt-patterns.md) before generation or editing; load only the relevant pattern.
- Read [references/photo-illustration-and-edits.md](references/photo-illustration-and-edits.md) for batch mapping, cross-image continuity, exact clothing or bounded edits.
- Read [references/qa-and-deliverables.md](references/qa-and-deliverables.md) before generation and delivery, including individual exports.

## Reusable Presets and Custom Style

Offer the active catalog plus `自定义风格`. A custom image reference is task-scoped by default: inspect it, extract concrete shape/line/material/palette rules, and use it without copying its characters, text, logos, props or composition. Explicitly requested source-photo clothing motifs belong to the content lock; the prohibition on importing style-reference characters must not erase them.

When the user asks to save a reusable preset:

1. Inspect the supplied style group and extract one shared fingerprint; split only if requested or materially different.
2. Reuse a supplied name or ask one naming question, then derive a stable lowercase hyphenated ID.
3. Flag a materially similar preset; do not silently overwrite it or the current style lock.
4. Store reference assets only with explicit authorization to store/reuse those assets. Permission to summarize a style or edit a public skill does not imply permission to publish private photos or third-party artwork.
5. Mark the entry `draft` until the user confirms activation. State whether it is image-backed or a text recipe; never invent a preview or a reference path. A text recipe may be selected on its own, but precise matching to a named image requires actually inspecting that image.

## IP Exploration Deliverables

Use the wizard only for this workflow:

1. Resolve IP type, source/brief, selected style, enhanced traits, palette and allowed variations; show the prompt lock for approval.
2. Generate one 3x2 preview with exactly six candidates. Host-render badges `1`–`6` in reading order; do not ask the image model to draw numbering. Vary only approved axes, retaining all fixed identity and clothing details.
3. After the user selects a candidate, retain that character design for the avatar and nine expressions. Original sources and user corrections still arbitrate factual details; a mistaken accessory in a candidate never overrides a corrected source fact.
4. Generate a 1:1 formal avatar and a 3x3 expression source board. Compose one 4x3 delivery board with host-rendered Chinese captions. Keep the optional nine transparent sticker exports and original board-only default unless the user requests a different export package.
5. Provide the reusable prompt lock and compact character handoff. Follow the image tool's own reference, editing and output requirements. Continue from approved work across turns.

For photo illustration, deliver the requested individual scene files instead. A contact sheet can supplement those files only when useful or requested.
