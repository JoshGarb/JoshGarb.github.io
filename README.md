# joshgarb.github.io

Personal homepage for Josh Garbutt, World Model Head Hunter.

Live: https://joshgarb.github.io

A single self-contained `index.html`. No build step, no dependencies, no
framework. GitHub Pages serves it straight from the default branch.

## What's in it

- Isometric voxel bonsai drawn on a canvas. The grass IS the WeChat QR code
  (37x37 modules). Scrolling lifts the camera and the planting resolves into a
  scannable code, then hands off to a crisp bitmap.
- Live jobs as a horizontal slider with an inline application form.
- Rotating candidate references.
- Contact: LinkedIn, GitHub, email, WhatsApp.

Single dark theme on purpose: no toggle, no `prefers-color-scheme` branch,
every colour painted explicitly.

## Build notes

These were an on-page annotation panel during the prototype. Moved here so they
are not shown to visitors.

- **Verticals are Josh's own list**, world models only. Deliberately not LLMs, agents, games, simulation or AV. The five roles under Track come from the current `/team/josh-garbutt` page.
- **References rotate:** three cards visible, swapping one at a time from a larger pool every 3s, so a handful of quotes reads as constant activity. Pauses under reduced-motion.
- **Live jobs are real**, Josh supplied them. They still need to be editable without a deploy, and each row wants a date so the list visibly moves.
- **The apply form does not submit anywhere.** Validation and the open/close behaviour are real; the submit handler only prints a notice. It needs wiring to an inbox or ATS, plus server-side validation, a file-size/type limit, and a privacy notice before it goes live.
- **No photo on the current page**, just a grey `JG` box. Either use a real one or drop the slot; a placeholder is worse than neither.
- **Type** is Fraunces + Public Sans + DM Mono. The character comes from the type, not from effects.
- **Dark only, by choice.** No toggle, no light palette, no `prefers-color-scheme` branch, every colour is painted explicitly on `:root` so the page looks the same whatever the viewer’s OS is set to. One accent: a green that nods to the Growth mark. Amber only marks placeholder content.
- **The bonsai is a canvas voxel scene**, no libraries. The paving is Josh’s real WeChat QR, 37×37 modules, raised one block each. Scroll lifts the camera from isometric to top-down and swings the yaw square-on; the canopy fades so the code is readable.
- **Scale, not geometry.** The scene renders 25% larger at rest, tree and platform together, instead of the tree being re-proportioned. Tree geometry is back to the approved version.
- **The WeChat code lives only in the tree now.** The duplicate in Contact is gone; its embedded PNG moved onto the tree overlay, which had been reading its image from that element.
- **Footer** is a single centred “Top” control with a proper hit area, the duplicate LinkedIn/GitHub/Email links are gone, since the Contact section directly above already carries them.
- **“Scroll to look down”** sits in the clear space to the left of the tree rather than under it, since the enlarged scene covers that area. It fades out as soon as you start scrolling.
- **Butterflies** are two-frame pixel sprites drawn in screen space, so the silhouette reads at small size rather than turning into a coloured smudge. Orange, blue and white; wings open and shut as they orbit the canopy, and they fade out with the tree.
- **Nothing green survives the reveal.** The voxel canvas fades to zero as the crisp code fades in, so the end state is a plain white QR on the page background, no grass, leaves or slab behind it, with the contact links fading in directly beneath.
- **WhatsApp** uses `wa.me/447301620466`, one link that opens the app on a phone and WhatsApp Web on a desktop, with the chat to Josh already open.
- **It grows into the page.** As the camera lifts, the scene scales up and slides to the centre of the viewport to fill the empty space, then holds there before releasing. The growth is a CSS transform so it never disturbs the sticky layout, and the canvas backing store scales with it so the voxels stay sharp instead of blurring.
- **Scanning:** voxel tiles in isometric never scan, so at the top of the rotation it cross-fades to the real bitmap at 1:1. The footer QR is the always-available fallback.
- **Leaves** are green. Tree geometry is seeded, so it looks identical on every load. Animation pauses off-screen and on hidden tabs, and reduced-motion gets a static isometric view.
- **“Where I’ve worked” is commented out** rather than deleted. Search the HTML for `parked` to restore it.
- **Nothing moves under the cursor:** the reference rotation pauses on hover and stops for good once you click into that area; job cards and reference cards have reserved heights so they never reflow.
- **Structure** follows the three reference pages: name → one-line thesis → link row → short sections → dated list → footer. One column, nothing decorative below the fold.
