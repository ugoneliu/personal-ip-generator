# Intake, Reference Roles and Locks

## Resolve Only Missing Inputs

Determine the requested workflow first: IP exploration, photo illustration, or local edit. For a complete photo/edit request, reuse the established style and content choices. For new IP exploration, use `plan-mode-wizard.md`; do not force that wizard on a photo batch.

Use user-supplied or authorized sources. Inspect actual images before describing them. If an earlier reference cannot be accessed, state that limitation and request only the missing reference when needed for a faithful match; do not claim it was checked or substitute an internet lookalike. A user may instead choose an explicitly labeled text recipe.

## Reference Roles

Assign roles per image, not just by upload order. A single image may have multiple explicitly separated roles.

| Role | Controls | Must not supply by accident |
| --- | --- | --- |
| Source photo / identity | Person count, individual features, clothes, pose, visible scene facts | The rendering style unless selected as a mixed reference |
| Style reference | Shape language, line, proportion treatment, material, palette, texture | Depicted characters, clothes, animals, props, text, scene or composition |
| Approved character candidate | Designed character continuity for IP derivatives | Incorrect facts overriding the source or later corrections |
| Approved style keyframe | Rendering consistency across a photo series | Its cast, outfits, background or pose in a new source photo |
| Edit base | Current composition and all protected content | Authority for a detail the user explicitly corrected |
| Detail / scene reference | Only the named accessory, garment, pose or background | Unrelated people, styling or objects from that image |

“参考这张图的风格” makes that image the primary style authority. “用这张做背景” assigns a scene role only. Do not silently combine the people from one photo and the background from another. If the user requests that combination, record the exact foreground and background file IDs.

## Precedence by Dimension

There is no single reference that wins every dimension.

- **Current intent:** latest explicit user instruction/correction overrides earlier instructions within its stated scope. Changing a chest emblem does not unlock hairstyle, pose, background or the whole style.
- **Identity and content:** current source photos and user-confirmed facts control what is shown. If a source is ambiguous, preserve only what is visible or ask one focused question about an identity-critical detail. A corrected garment category is authoritative even if an earlier output depicts something else.
- **Style:** the explicitly selected runtime reference and its approved fingerprint control visual language; a preset supplies unspecified fields. An accepted keyframe refines continuity within that lock. Broad adjectives, previous generic defaults and unselected presets cannot override it. Resolve a material conflict between two approved style authorities before generating.
- **Edits:** the latest accepted base controls protected regions; a focused detail reference/correction controls only the allowed change. Rejected images, assistant guesses and unrelated old scenes are not authorities.

Do not blend all historical inputs into one prompt. Keep an active reference set and mark superseded/rejected versions inactive. Attach the relevant images to the tool call using its supported reference mechanism; text saying “same as before” alone does not carry visual evidence.

## Style Lock

Record a stable ID/version, selected preset or runtime file IDs, approved keyframe, and concrete fields:

- Line: contour presence, color, thickness, pressure variation, broken edges.
- Shape/proportion: simplification, asymmetry, head/body treatment, face diversity, limb geometry.
- Rendering/material: how crayon, oil pastel, pencil, paint or 3D actually forms edges and areas.
- Palette: dominant/secondary/accent, saturation, temperature, contrast, handling of source garment colors.
- Texture/light: paper and pigment interaction, mark scale, layering, shadows and highlights.
- Composition/background/outline: use these from the style only when the user's composition is open; photo composition stays source-led by default.
- Negative constraints: observable failure modes, not only broad genre labels.

For `tongqu-huiben-feng`, read `storybook-style.md`. Do not reuse that fingerprint for 3D, line art or any other unselected style. For a custom reference group, extract shared properties and resolve incompatible examples rather than averaging unrelated styles.

## Content and Character Lock

For a photo series, keep stable person IDs across scenes plus a separate per-photo roster. Use position IDs (e.g. P1 at left) when no names are supplied; do not infer identity from unrelated images. Record:

- Exact main-subject count, source-visible background people and requested removals; never invent replacements.
- Per person: visible age presentation and user-provided labels only as needed, face/head shape, hairstyle/parting/bangs/ponytail, visible eyewear and other distinguishing features.
- Relative height, build, position, head direction, pose, hands, gaze and person-to-person contact.
- Every visible/confirmed garment: category, cut, layers, hem, sleeve, color blocks, footwear.
- Every accessory: count, shape, color, size, body-relative location, attachment, and semantic identity when confirmed; do not stop at one signature item.
- Clothing prints/headpieces: identity and key visible features, not a vague dark blob. A requested Kuromi motif stays a clothing motif; it must not become a dog or a separate animal.
- Scene facts and permitted additions/removals, frame/aspect ratio, requested crop or outpainting.
- Unknown/occluded details and evidence source; do not invent hidden outfit features or unsupported relationships.

The style simplifies rendering, not the semantic identity of clothing or people. Preserve different face silhouettes and hair patterns; do not template every child into identical round cheeks, eyes and bangs. Do not infer gender or sensitive attributes from a skirt or hairstyle; retain user-provided descriptions and visible evidence.

Same person does not mean same outfit in every source photo. Separate stable identity from scene-specific clothing. In IP derivatives, the selected outfit is locked until changed; in photo conversion, each current photo supplies its own outfit.

## Prompt Lock and Corrections

Combine workflow, current source manifest, per-person content lock, style lock/version, allowed variations, protected elements, exclusions and export plan. Carry only the active facts into every derivative call.

For a correction, update the affected lock field before editing. Record the rejected interpretation in a small correction log, but prompt primarily with the desired positive fact. Do not reattach a wrong dog-emblem result as a style/detail reference. If it is the only available edit base, clearly scope it as a base with a known incorrect chest region; it is never content authority for that region.

## Rights and Persistence

Never publish portraits or personal generated examples in the skill. Style-reference characters, branding, watermarks and scenes are excluded from transfer. This does not prohibit preserving an explicitly requested, source-visible garment motif or logo as part of photo content. Do not add branding absent from the content brief or replace it with invented text.

Custom references remain task-scoped unless storage is explicitly requested and authorized. Abstract preset descriptions may be saved without bundling the referenced artwork; label that distinction accurately.
