# Blueprint staging QA checklist

Run before approving any staged blueprint or updating `locations.blueprint`.

## Per-image checks

- [ ] Strict top-down orthographic (no isometric, no perspective exterior)
- [ ] ≤8 room labels, ALL CAPS, readable at 1024×1024
- [ ] One north arrow and one scale bar only
- [ ] Room boundaries clear (no heavy grunge over walls)
- [ ] No moodboard collage / multi-panel layout
- [ ] No bright blue CAD brochure look (anti-pattern: `images.jfif`)

## Family palette

| Family | Verify |
|--------|--------|
| `tactical_aged` | Cream/aged parchment, charcoal ink, blood-red tactical accents only |
| `parchment_residential` | Warm parchment, black ink, burgundy/gold accents |
| `chantry_formal` | Cream sheet, navy heavy walls, formal serif titles |
| `noir_occult` | Grainy off-white, pure black linework, occult line icons |

## Pipeline metadata (record in review)

- [ ] `family_id` matches location type router ([includes/blueprint_style_family.php](includes/blueprint_style_family.php))
- [ ] `primary_reference_path` documented
- [ ] Backend noted: OpenAI (`reference_used: no`) or fal (`reference_used: yes` when `image_url` sent)
- [ ] Staging PNG path linked before DB update

## Automated smoke test

Run fixture router (10 locations, all families):

- Repo: `tools/repeatable/php/blueprint_style_family_fixtures.php`
- Browser: https://vbn-game.com/tools/repeatable/php/blueprint_style_family_fixtures.php

Expect `Failures: 0`.

## Approval gate

Do **not** PATCH `locations.blueprint` until user explicitly approves staged PNG.
