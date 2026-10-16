# Photo Illustration and Bounded Edits

Use this workflow for direct photo conversion, a related batch, or a specific correction to an accepted illustration. Do not force the six-candidate IP wizard, a sticker board, or a new style-selection round onto a sufficiently specified request. Use [intake-and-style.md](intake-and-style.md) for reference roles and [prompt-patterns.md](prompt-patterns.md) for the relevant generation/edit pattern.

## 1. Map the Sources Before Generating

Inspect every source. Assign stable scene IDs in upload order, such as `photo-01`, and retain a task-local source manifest. A later upload gets a new ID; it does not silently replace an earlier source. Record:

- Original filename or attachment ID, and a brief scene description that distinguishes similar photos.
- A local checksum when the original file is available; otherwise an attachment reference or an inspected thumbnail. Never invent a checksum or claim to have viewed an unavailable image.
- Which source belongs to which requested output, its crop/aspect ratio, and any requested additions or omissions.
- Per-scene people and animal counts, per-person roster, style lock, accepted keyframe, latest accepted output, rejected versions, and QA state.

If a source cannot be accessed, preserve the mapping and request only that missing source. Do not substitute an internet image or another upload. When several photos look similar, use the manifest instead of memory to choose the input for each call.

The following is a synthetic manifest example, not a real subject or retained photo:

```yaml
scenes:
  - id: photo-01
    source: {filename: sample-01.jpg, attachment: upload-A}
    verification: inspected task-local thumbnail # use an actual checksum when available
    scene: two people standing beside a plain wall
    counts: {people: 2, living_animals: 0}
    roster: [person-A, person-B]
    requested_changes: []
    style_lock: style-v1
    accepted_style_keyframe: approved-illustration-01
    latest_accepted_output: photo-01-v1.png
    rejected_outputs: [photo-01-rejected-v2.png]
    deliverable: photo-01-illustration.png
    qa: pending
  - id: photo-02
    source: {filename: sample-02.jpg, attachment: upload-B}
    verification: inspected task-local thumbnail
    scene: person-A seated beside one dog
    counts: {people: 1, living_animals: 1}
    roster: [person-A]
    requested_changes: []
    style_lock: style-v1
    accepted_style_keyframe: approved-illustration-01
    latest_accepted_output: null
    rejected_outputs: []
    deliverable: photo-02-illustration.png
    qa: pending
```

Keep manifests, thumbnails and personal outputs in the current task, outside the reusable skill. Do not publish them as examples in a skill update.

## 2. Lock People, Clothing and Scene Facts

Create a per-person ledger for each scene. Use neutral stable IDs to connect the same person across photos only when the user identifies them or the supplied evidence makes the relationship clear; do not identify strangers or infer sensitive attributes.

For each person record:

- Position in the frame, pose, facing direction, visible body extent and overlap with other subjects.
- Distinguishing face/head shape, hairstyle, hair length and color, glasses and other visible identity anchors. Preserve differences between people instead of applying one round-face template.
- Every visible garment: type, cut, layers, sleeve/hem length, pattern and source color relationships. Distinguish a dress or skirt from trousers, a scarf from straps, and shoes from bare feet.
- Every visible accessory: identity, count, shape, color, placement, scale and attachment. Record hair accessories/headpieces, glasses, jewelry, bags and clothing emblems separately; “one signature accessory” is never permission to drop the others.
- Visibility or uncertainty: mark an occluded, cropped or unreadable detail as unknown. Do not fill it with an invented accessory, animal, garment or anatomical feature.

For example, a synthetic `photo-01/person-B` ledger may specify `short dark hair; one headpiece at crown; cream short-sleeve dress; one Kuromi head emblem centered on upper chest; white shoes`. The emblem is printed decoration, not a pet or a new person in the scene. Apply the selected illustration medium to its marks while retaining the requested motif's identity and location.

Track living animals independently from clothing motifs. Retain source animal count, species and position unless the user requests a scoped change. Do not add a dog because a dark chest motif was misread as one; do not remove an actual source animal under a generic “no animals” rule.

Keep meaningful scene facts and spatial relationships. No invented people, animals, mascots, props, flowers, symbols, architecture or landmarks for atmosphere. An explicitly requested addition is allowed only in its specified scene and scope; it does not become a default for the batch.

## 3. Apply Reference Authority by Role

Use [intake-and-style.md](intake-and-style.md) as the common authority contract:

1. Latest explicit user corrections override earlier guesses or source interpretations within the correction's stated scope. Record the corrected fact and retire the rejected description.
2. Each current source photo governs its people, clothes, poses, animals and scene facts outside that scope.
3. An explicitly selected and inspected runtime style reference governs visual language. Its concrete evidence outranks a broad style adjective or text recipe; a later explicit user style change updates the style lock.
4. A selected preset or approved text recipe governs style where no runtime style image has been selected. Use the optional picture-book recipe in [style-presets.md](style-presets.md) only when chosen.
5. An accepted illustration/keyframe carries consistent shape language, face simplification, line behavior, palette relationships and material treatment. It cannot replace the current photo's content or overrule a corrected factual detail.

Attach references with explicit roles, not as an undifferentiated image pile. For a new scene, use that scene's original photo plus the active style reference/keyframe. For a local edit, identify one latest accepted edit base; attach the source or a detail reference only to resolve the named fact, without treating it as a second edit base. Exclude rejected outputs and stale prompts from future reference authority.

“这张也用刚才的风格” means reuse the style lock with the new photo's content. The same person may wear different clothes in different photos. Preserve those scene-specific outfits; do not transplant the previous output's dress, accessory, pose, companion, animal or background.

## 4. Generate a Related Batch

Carry one explicit style fingerprint across the batch: shape/proportion, line, marks and material, palette relationships, paper texture and background treatment. Reuse an accepted style keyframe when available; do not gradually approximate the last imperfect output. A selected picture-book style must not drift into generic chibi faces or digital grain; use the concrete preset rules instead of only saying “童趣手绘”.

Generate each mapped scene as an independent image. If the user supplied several source photos, do not merge their people or scenery into a composite. Keep each photo's requested framing and subject placement. Preserve full visible body parts and leave adequate framing space when the user requests a full-body result.

If a foot is clipped in the source, record that fact. An explicit request to complete the foot authorizes a focused extension/outpainting of the canvas and the missing portion; infer only the minimum needed from the visible leg, shoe and ground. Extend framing instead of shrinking the person, compressing the legs, changing head/body proportions or moving the whole scene to fit. Without that request, do not invent hidden anatomy.

## 5. Make Local Edits With an Edit Contract

Use the latest accepted image for the named scene as the single edit base. Do not restart from the original photo or a rejected version to make a small correction. Express the target positively, name its exact location, and protect all unrelated details. Use an edit/mask mechanism when supported; follow the image tool's own requirements.

Reusable synthetic Edit Contract:

```text
Scene: photo-01
Single edit base: latest accepted photo-01-v1.png
Requested change: replace only person-B's upper-chest emblem with one Kuromi head.
Allowed region: the existing chest emblem and the minimum surrounding dress fabric needed to blend it.
Target: one recognizable Kuromi head, same position and scale, drawn in the image's locked illustration medium.
Protected: person-B's face, hair, crown headpiece, body proportions, pose, dress cut/color;
           person-A and all other clothing/accessories; people/animal counts; background;
           composition, palette, texture and canvas size.
Retired error: the rejected chest-dog depiction is not a source, style keyframe or future content authority.
Acceptance: inspect the chest motif at useful zoom and the full image for collateral changes.
```

The correction “胸前是库洛米，不是小狗” updates the chest motif only. Do not erase the headpiece, redesign the dress, change faces or add a living Kuromi/dog elsewhere. Keep the target description clear; do not repeat obsolete detailed dog descriptions that could contaminate the next generation.

Preserve existing pixels outside the edit where the tool supports that operation. Image-model edits can still change protected areas: inspect the result and never promise pixel-identical preservation without verifying it. Do not claim that a whole-scene remake is a successful local edit merely because the target changed.

## 6. Inspect, Repair and Export

View every tool result before accepting it. Compare the full image and relevant details against the source manifest, per-person ledger, style lock and Edit Contract. Check exact people/animal counts, distinct identities, garments/accessory identities and locations, pose/anatomy, source scene content, medium/palette, and any protected areas. Compare related outputs side by side where possible. Use the detailed checks in [qa-and-deliverables.md](qa-and-deliverables.md).

If a result fails, name the concrete mismatch and repair only that failed asset or region from its latest accepted base. Allow at most two focused repair attempts per failed asset, and stop earlier when tool availability or the user's time/cost limit requires it. Do not run an unbounded generation loop. If the issue remains, mark it unresolved and explain the specific limitation; do not silently deliver it as QA-passed. A tool success message is not visual verification.

Export one complete standalone image per requested scene using its stable ID, for example `photo-01-illustration.png`. Provide the actual files at their intended aspect ratio and sufficient resolution; verify each file opens and maps to the correct source. A contact sheet may supplement the individual files but never replace them. Do not deliver slices of a combined poster as if they were independently composed scenes. Claim transparency only after checking a real alpha channel, and do not remove scene backgrounds unless requested.
