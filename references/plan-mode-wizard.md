# Personal IP Exploration Wizard

## Scope

Use this wizard for new IP exploration only. Direct photo illustration and local edits use `photo-illustration-and-edits.md`. If the user already supplied the source, style, palette or approval, retain those choices; ask only the first unresolved material question. A continuation does not restart the wizard.

## Operating Contract

- Ask at most one material question per assistant turn; resolve one field at a time.
- Use structured choices when supported, with 2–3 useful mutually exclusive options; allow free-form answers, `skip`, `unknown` or `use default`.
- Inspect uploaded images before the next question. Classify source/style/detail roles separately.
- Do not generate during unresolved discovery. A complete IP plan needs approval once before candidates.
- Do not make a new preset-intake record block ordinary generation with an already chosen task-scoped style. Saving a reusable preset is a separate request.

## Generation Profile

Keep workflow, IP type, authorized source/representative brief, active reference IDs and roles, style lock/version, per-person character lock, enhanced traits, palette, allowed variation axes, avoided content, approval, candidate selection, export plan and unresolved facts. Mark values Confirmed, Inferred, Defaulted or Unknown.

## Question Queue

1. **IP type:** `人物 IP` from an authorized likeness, or `代表形象 IP` from an original representative brief.
2. **Source/brief:** for 人物 IP accept 1–3 authorized portraits, a detailed appearance description or an approved IP image. For 代表形象 IP collect what it represents, audience, role, personality and one visual memory point. Do not imply an unauthorized likeness.
3. **Style:** read `style-presets.md`; show all active presets in catalog order plus task-scoped `自定义风格`. Image-backed cards use real previews; the text-only 童趣手绘绘本风 card must state it has no bundled preview. For custom style, inspect at least one supplied authorized reference and extract the fingerprint. Do not silently apply 童趣手绘绘本风.
4. **Enhanced traits:** collect 3–5 visible features to emphasize, or accept “preserve source”. This may emphasize hair, silhouette, pose energy or accessories without changing protected clothing. Do not import branded characters from style references; explicitly requested source clothing motifs remain part of the content lock.
5. **Palette:** selected style palette, a compatible custom direction, or an authorized palette reference. Record dominant/secondary/accent, saturation, temperature and contrast. Preserve key garment/motif color identity unless a change was requested.
6. **Prompt approval:** show the content/style locks, composition, allowed variation axes, exclusions and export plan. Ask one approval question before the six-candidate preview. Keep any earlier approval that already covers this plan.
7. **Candidate selection:** generate a single 3x2 overview with six equally sized candidates. Host-render numeric badges `1`–`6` in reading order. Vary only approved axes; if clothes are fixed, “outfit emphasis” means presentation or pose, not a redesigned garment. Ask which number to lock.
8. **Optional cutouts:** after selection, ask once whether the nine expressions also need individual transparent files, unless already specified. Default to no if skipped; do not turn optional exports into an unresolved mandatory approval.
9. **Final package:** generate a 1:1 formal avatar and a 3x3 expression source board. Compose one 4x3 delivery board with avatar left and expressions right. Host-render `正式头像`, `开心`, `大笑`, `生气`, `委屈`, `惊讶`, `困惑`, `得意`, `疲惫`, `喜爱`. Export nine individual transparent stickers only when selected, or follow an explicit alternate export request. Supply the prompt lock and compact handoff.

The selected candidate locks designed identity, rendering, proportions, costume and accessory placement for derivatives. It does not override original source facts or latest user corrections. Correct a factual mistake in the lock rather than perpetuating it.

## Progress and Finalization

Briefly state the newly recorded choice and ask only the next unresolved question. No fixed response template is required when there is nothing left to ask.

If the host is actually in Plan Mode, present the proposed plan and follow that mode's execution limits. Otherwise present the equivalent generation plan and proceed after its required approval. Do not claim a mode change merely because this skill is a guided wizard. Keep mapping and locks across turns and respect the image tool's actual reference/output requirements.
