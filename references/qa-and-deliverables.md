# QA and Deliverables

## Inspect Before Claiming Success

Open/view the actual generated result and each exported file. Compare against the active source and style references, not just the generation prompt. Record `pass`, `fail` or `not verified` for the relevant checks; do not call a file checked when it was not inspected. Keep a compact internal record per asset: source ID → output/version → content/style/edit/export checks → unresolved issue. Surface only useful findings to the user.

If a required source, visual inspection tool or output file is unavailable, state what remains unverified. A tool's successful return and a model's verbal “looks correct” are not evidence of visual fidelity.

## Shared Visual Checks

1. **Mapping and count:** correct source photo/scene, exact subject count, distinct people, positions and relative sizes. No duplicated person, extra limb, invented pet or borrowed scene. A source-visible toy, print or reflection is not a new living subject; preserve/remove it only as specified.
2. **Identity and pose:** face outline, hairstyle, eyewear and distinguishing visible features remain recognisable. No cloning one child's face/hair onto another. Hands, contact, gaze and action match the source or approved changes. Use only supplied personal labels; do not infer sensitive attributes.
3. **Clothing and accessories:** compare every roster entry at a useful zoom. Check skirt versus trousers, scarf versus straps, cut/hem/layers, colors, ponytail, headpiece, footwear, accessory number and attachment. Confirm the semantic identity, size and location of requested chest motifs, not just a dark shape.
4. **Scene and frame:** only source facts and specifically requested additions; no automatic cats, decorative objects, text or landmark guesses. No unintended crop, stretched limb or shortened foot during completion/outpainting.
5. **Style:** compare line, face/shape language, proportions, material marks, palette, paper/light and overall finish with the chosen style lock and keyframe. Correct content alone does not pass a style mismatch. For `tongqu-huiben-feng`, run the close-up and whole-image checks in `storybook-style.md`, especially real pigment behavior versus a digital noise overlay.
6. **Cross-image continuity:** same drawing grammar and stable character anchors across the series; each photo still has its own cast, pose, clothes and scene. A new outfit visible in the next photo is not drift.
7. **Local edit containment:** compare target and protected areas with the accepted base. Verify the correction and check faces, hair/headpiece, all other clothing, pose, background, palette, texture and framing. Do not claim pixel-identical preservation unless actually measured; generative edits can alter protected areas.

## Photo Illustration Package

- One complete, independently openable image per requested source scene, with stable source-ID → filename mapping, e.g. `photo-03_illustration_v02.png`.
- Each file contains only that scene, without adjacent scenes, split-screen comparison, labels, contact-sheet gutters or duplicated panels unless explicitly requested.
- Check file count, dimensions/aspect, orientation, actual image format, complete subject boundaries and readable key details. Open the exports themselves; a good overview does not prove a good individual file.
- An optional contact sheet is additional navigation, never a replacement for the requested separate images. If only a sheet is produced, safely extract complete panels when feasible or regenerate the missing standalone scene; disclose if the requested delivery remains incomplete.
- Supply a compact reusable style/character handoff when requested or helpful, without inventing biographies, names or relationships.

## Original IP Package (IP Exploration Only)

- Approved prompt lock and one 3x2 six-candidate overview, equal cells with host-rendered badges `1`–`6` in reading order. Candidates differ only along approved axes, without changing fixed clothes/accessories or introducing unrelated people.
- Selected 1:1 avatar source and a 3x3 expression source board, followed by one 4x3 final board with avatar left and expressions right. The candidate controls designed continuity; source photos and scoped corrections remain factual authorities.
- Host-render captions: `正式头像`, `开心`, `大笑`, `生气`, `委屈`, `惊讶`, `困惑`, `得意`, `疲惫`, `喜爱`. Check actual labels and their cell mapping. Do not depend on model-generated Chinese or numbers.
- All panels keep the selected character's face, hair, silhouette, outfit cut/layers, footwear, palette, material, motifs and accessory placement. Expressions read at roughly 256 px and differ by face/gesture, not costume redesign.
- Keep the original board-only delivery default. Export nine separate square expression files only when cutouts or another individual-file package was requested. Each silhouette must be complete, with no neighbor-cell fragments or clipped accessories.
- Claim transparency only after checking actual alpha data and visually checking edges; an RGBA container with all-opaque alpha or a painted checkerboard is not transparency. When cutouts were requested but unavailable, state the unmet requirement.
- Written handoff: IP type, any user-approved name/positioning, visible memory points, palette and reusable prompt lock. Do not invent personal claims to fill a template.

## Focused Failure Handling

Keep the accepted original and version the repair. Restore only the failed asset/region with the same active source/style set. For an initial failed generation with no accepted same-scene base, regenerate from that scene's original source plus the active style references; a different-scene keyframe is never the edit/content base. Exclude rejected outputs from future authority. If a single expression/candidate cell can be repaired and recomposed, preserve the other approved artwork; recreate a complete overview only if independent replacement is infeasible.

Allow up to two focused repair attempts per failed asset, within the user's/tool's cost and retry limits. Reinspect each result. If still failing, stop automatic retries and report the specific unresolved defect and last usable version; never present the failed result as approved. A new explicit user direction may authorize a further attempt. Incorrect numbering or captions require host recomposition only.

When the image tool has staged output rules, obey them and perform inspection at the next permitted stage before promoting a result to accepted/keyframe status. Do not silently certify an unchecked output.
