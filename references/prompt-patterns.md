# Image Prompt Patterns

Before every call, read the active prompt lock and attach the actual relevant references using the image tool's supported mechanism. Follow that tool's editing, transparency and output rules. Select the relevant pattern; do not concatenate every workflow or rejected prompt from history.

The lock contains workflow, source IDs and roles, exact per-person content/scene facts, style lock/version, current keyframe, palette, allowed changes, protected content and export plan. “No copied characters/logos” below concerns unrequested imports from style references; it must not erase a source-visible garment motif explicitly preserved in the content lock.

## Photo Illustration — One Source Scene

```text
Create one complete standalone illustration for [photo ID, exact file, short scene description].
CONTENT authority: [current photo + scoped user corrections / requested composite mapping].
Exactly [N] main people: [P1 position, distinctive features, clothes and every accessory; P2 …].
Preserve [pose/contact/relative scale/crop/visible background facts]. Animals/props: [source inventory].
Allowed additions/removals: [explicit list, or none]. Do not invent people, animals, landmarks or decorations.
STYLE authority: [selected reference IDs/preset and style-lock version]. Keyframe [ID] controls drawing grammar only.
Apply [concrete shape, face simplification, line, pigment behavior, paper interaction, palette, light].
Retain each person's own face/hair silhouette and garment category, cut, colors, motifs and accessory locations.
Do not import the style/keyframe's cast, clothes, scene, text, props or composition.
Output [aspect/size] for this scene only; no collage, comparison panel, numbering or automatic sticker border.
```

For `tongqu-huiben-feng`, load `storybook-style.md` and use its specific material/shape rules. Keep irregular naive shapes, individual faces, directional crayon/oil-pastel coverage, selective pencil marks, matte gouache masses and paper visible through pigment. No uniform noise overlay, smooth digital shading, generic round-face template or drifting anime/3D finish. Do not add that clause to another selected style.

## Local Edit

```text
Edit only [target region/object] in [exact current accepted base file/version].
Target result: [positive corrected identity, category, shape, color and location].
Detail authority: [source crop or user-confirmed fact]; style: [existing lock/keyframe].
Allowed changes: [region plus necessary edge integration].
Protected: [people count, faces, hair/headpiece, pose, all other garments/accessories, scene, palette, texture, frame].
Render the replacement in the same line/pigment/material language and integrate its edges locally.
Do not redesign the whole image or reintroduce superseded interpretations from earlier versions.
```

Example of the target field: “The small chest decoration is a Kuromi head motif printed/attached on the garment, at its existing size and position. Keep the existing headpiece and all other clothes.” The incorrect dog label is not a creative alternative. Use it only as a concise exclusion if needed, not as a competing visual subject. It never authorizes adding a cat, pet or freestanding mascot.

## IP Six-Variant Preview

Generate one 3x2 overview containing exactly six distinct candidates with equal cell sizes, consistent scale and clear gutters. Leave badge-safe corner space; host-render badges `1`–`6` in reading order after generation. No generated numbers/captions/watermarks.

Use [authorized identity lock] for 人物 IP or [original representative brief] for 代表形象 IP. Apply [selected style fingerprint], [enhanced traits] and [palette]. Cell focus order: balanced default, silhouette emphasis, outfit presentation, accessory presentation, pose energy, expression/composition. Vary only approved axes. Emphasis must not replace a fixed skirt, scarf, emblem or hairstyle. No unrequested character, logo or scene imports.

## IP Avatar and Expression Source

Use the selected candidate as the designed-character reference, while retaining the factual source/correction lock. Repeat:

`same selected character: consistent individual face, hairstyle, silhouette, proportions, outfit cut and layers, footwear, garment motifs, palette, material, outline and exact accessory placement; change only the requested expression/gesture`

- **Avatar:** one centered square 1:1 head-and-shoulders/bust with a readable face and the selected style's appropriate background. No costume redesign, new text or extra characters.
- **Expression source:** one 3x3 board, one character in each cell, expressions in reading order: Happy, Laughing, Angry, Aggrieved, Surprised, Confused, Proud, Tired, Love. Equal spacing, plain background suitable for export, caption-safe strips. Keep expressions distinct through face/gesture. Do not claim a transparent-looking background has an alpha channel.

## Compose and Export

For the default IP package, compose a 4x3 board with avatar left and expression source right. Host-render `正式头像` plus `开心`, `大笑`, `生气`, `委屈`, `惊讶`, `困惑`, `得意`, `疲惫`, `喜爱`. Typesetting corrections require recomposition, not regenerated characters. If the image tool cannot render labels or export panels, use available host composition tools and disclose any unmet output requirement.

For requested cutouts, export nine separate cells with complete silhouettes and real verified alpha. For photo illustration, export each requested scene independently; a combined preview never substitutes for those files. See `qa-and-deliverables.md` for verification.

## Focused Repair

Edit/regenerate [failed scene, avatar or expression cell] from the same active sources. Restore [specific failed lock fields] and preserve [accepted fields]. Repair a single cell and recompose when feasible; regenerate a whole overview only when it cannot be replaced independently. Never attach the failed output as a new style authority. For local edits, compare the target and protected regions before accepting the new version. Follow the bounded repair rule in `qa-and-deliverables.md`.
