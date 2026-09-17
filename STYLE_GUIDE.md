# Judith Website — AI Style Guide

## Source and authority

This guide is derived exclusively from `orginal.html`, the pasted “Lifestyle Session” HTML reference, and the supplied screenshots of that same original page. Existing website pages are not design references; they are future consumers of this guide and may need to change to match it.

When an existing page conflicts with this document, follow this document. Preserve page-specific content, facts, images, and links, but align its visual design with the system below.

For exact image layout, proportions, spacing, or framing, `orginal.html` and the supplied original screenshots are the canonical implementation reference. Do not use image patterns from the newer pages to reinterpret them.

## 1. Design character

The visual language is quiet, warm, intimate, and gently premium. It should feel like a calm pause in family life.

Core qualities:

- soft and emotionally supportive;
- spacious rather than dense;
- natural rather than staged;
- refined through restraint, not decoration;
- rounded, tactile, and welcoming;
- focused on family photography and emotional storytelling.

Avoid saturated colors, dark interfaces, sharp corners, strong gradients, heavy borders, dense navigation, loud badges, or aggressive sales patterns.

## 2. Canonical design tokens

### Colors

| Token | Value | Use |
| --- | --- | --- |
| `vanilla` | `#FCFBF7` | Main page background, light text on dark surfaces, icon backgrounds |
| `coffee` | `#8E7E73` | Main text, headings, footer, secondary accents |
| `sage` | `#7F9083` | Primary CTA, links, selected emphasis, icons |
| `white` | `#FFFFFF` | Cards and translucent alternate sections |

Approved translucent treatments:

- standard paragraph: `text-[#8E7E73]/90`;
- supporting paragraph: `text-[#8E7E73]/80`;
- quiet utility text: `text-[#8E7E73]/70`;
- alternate section: `bg-white/40` or `bg-white/60`;
- subtle Coffee section: `bg-[#8E7E73]/5`;
- soft Sage surface: `bg-[#7F9083]/10` or `bg-[#7F9083]/15`;
- soft borders: Sage or Coffee at 10–30% opacity.

The base page is Vanilla with Coffee text. Sage is the action color. White lifts cards and alternating sections. Do not introduce additional brand colors unless explicitly requested.

### Fonts

- Heading font: `Varela Round`.
- Body font: `Assistant`.
- Fallback: `sans-serif`.

Load these Google Font weights:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Assistant:wght@300;400;600;700&family=Varela+Round&display=swap" rel="stylesheet">
```

Use this Tailwind extension:

```js
tailwind.config = {
  theme: {
    extend: {
      colors: {
        vanilla: "#FCFBF7",
        coffee: "#8E7E73",
        sage: "#7F9083",
      },
      fontFamily: {
        heading: ['"Varela Round"', "sans-serif"],
        body: ["Assistant", "sans-serif"],
      },
      boxShadow: {
        premium: "0 20px 40px -15px rgba(142, 126, 115, 0.15)",
        "premium-hover": "0 25px 50px -12px rgba(142, 126, 115, 0.25)",
      },
    },
  },
};
```

### Shadows and corners

- Premium card: `shadow-premium`.
- Image or testimonial: `shadow-sm`.
- FAQ hover: `hover:shadow-md`.
- Floating action: `0 10px 25px rgba(127, 144, 131, 0.5)`.
- Primary button: `rounded-2xl`.
- Large card, FAQ, or testimonial shell: `rounded-3xl`.
- Photo or secondary control: `rounded-xl`.
- Icon and floating action: `rounded-full`.

Shadows must remain soft, wide, and low contrast. Do not use square cards or sharp buttons.

## 3. Typography

| Role | Classes |
| --- | --- |
| Main H1 | `font-heading text-4xl md:text-5xl lg:text-6xl leading-[1.3] md:leading-[1.2]` |
| Final CTA title | `font-heading text-4xl md:text-5xl` |
| Section H2 | `font-heading text-3xl md:text-4xl` |
| Section H3 | `font-heading text-2xl md:text-3xl` |
| Card H4 | `font-heading text-xl` |
| Hero lead | `text-xl md:text-2xl font-light leading-relaxed` |
| Main body | `text-lg md:text-xl font-light leading-relaxed` |
| Utility copy | `text-sm md:text-base font-light` |
| Price | `font-heading text-2xl md:text-3xl font-bold` |

Use Coffee for headings and Coffee at 80–90% for body text. Use Sage for short emphasis. Use `font-semibold` sparingly for one key phrase. Keep prose narrow with `max-w-2xl` or `max-w-3xl`.

Center hero copy, section introductions, prices, testimonials, and closing CTAs. Narrative copy may become right-aligned from `md`: `text-center md:text-right`.

## 4. Page foundation

```html
<html lang="he" dir="rtl" class="scroll-smooth">
<body class="font-body antialiased overflow-x-hidden">
```

```css
body {
  background-color: #FCFBF7;
  color: #8E7E73;
}

::selection {
  background: #7F9083;
  color: #FCFBF7;
}
```

The reference begins with a large logo-led hero and has no global top navigation. Do not add a navbar, announcement bar, breadcrumbs, or utility header unless explicitly requested.

## 5. Layout and section rhythm

- Long-form narrative: `max-w-3xl mx-auto`.
- General content and feature sections: `max-w-4xl mx-auto`.
- Hero text: `max-w-4xl mx-auto`; supporting copy: `max-w-2xl`.
- Standard horizontal padding: `px-6`.
- Standard section: `py-24`.
- Large feature section: `py-24 md:py-32`.
- Final CTA: `py-32`.
- Footer: `py-16`.
- Internal rhythm: `space-y-6`, `space-y-8`, or `space-y-12`.
- Major heading separation: `mb-12`, `mb-16`, or `mb-20`.

Alternate Vanilla, `bg-white/40`, Vanilla, `bg-white/60`, and `bg-[#8E7E73]/5` to create gentle rhythm. Do not place every section inside a card; empty space is part of the design.

## 6. Canonical page flow

Use this sequence for a focused service or campaign page:

1. Logo-led hero with emotional promise, supporting sentence, and primary CTA.
2. Empathy section reflecting the visitor's experience.
3. Asymmetric photography gallery.
4. A second narrative or problem section.
5. Centered explanation of the service and its emotional value.
6. Feature or deliverable cards.
7. Price pill or compact offer summary when applicable.
8. “Suitable / less suitable” section.
9. FAQ accordion.
10. Testimonials.
11. Focused final CTA.
12. Coffee footer.
13. Persistent floating WhatsApp action.

The content can change, but the emotional sequence should move from empathy to understanding, offer, reassurance, proof, and action.

## 7. Components

### Logo-led hero

- Use `min-h-[90vh]`, `px-6 py-20`, and centered flex alignment.
- Logo: `w-48 md:w-56 object-contain opacity-90 mx-auto`.
- Place `mb-12` after the logo.
- Text group: `max-w-4xl mx-auto space-y-8`.
- CTA offset: `mt-16`.
- A desktop-only line break may control the H1 composition.
- Use one primary action.

### Primary CTA

```html
<a class="inline-block bg-[#7F9083] text-[#FCFBF7] font-heading text-lg md:text-xl px-12 py-4 rounded-2xl btn-breathe hover:-translate-y-1 transition-all duration-300">
  Button label
</a>
```

For a longer label, use `inline-flex`, `px-10 py-5`, and `w-full sm:w-auto`.

### Secondary WhatsApp action

Use `inline-flex items-center gap-2 bg-[#8E7E73]/10 text-[#8E7E73] px-4 py-2 rounded-xl text-sm hover:bg-[#7F9083] hover:text-[#FCFBF7] transition-colors duration-300`.

### Narrative block

- Container: `max-w-3xl mx-auto space-y-12`.
- Text group: `space-y-6 text-center md:text-right`.
- H2: `text-3xl md:text-4xl`, usually `mb-8`.
- Paragraphs: `text-lg md:text-xl leading-relaxed font-light`.
- Use one short emphasized phrase at most per paragraph.

### Asymmetric gallery

- The gallery stays inside the surrounding `max-w-3xl` narrative container. Do not expand it to `max-w-5xl`, `max-w-6xl`, or full viewport width.
- Grid: `grid grid-cols-2 md:grid-cols-3 gap-3 md:gap-6 items-start`.
- First column begins at the top.
- Second column: `mt-8 md:mt-12`.
- Third column: hidden on mobile, `md:flex`, and `mt-24`.
- Columns: `flex flex-col gap-3 md:gap-6`.
- Images: `rounded-xl shadow-sm object-cover w-full h-auto`.
- Keep each image's natural aspect ratio with `h-auto`. Do not add fixed heights, `aspect-*` classes, uniform crops, or equal-height rows.
- Place the images directly inside the vertical column containers. Do not wrap each image in a card, padded frame, link tile, or `overflow-hidden` shell unless the user explicitly requests clickable images.
- Preserve the source order by column: images 1 and 4 in the first column, 2 and 5 in the second, and 3 and 6 in the third.

Canonical structure:

```html
<div class="py-12 reveal">
  <div class="grid grid-cols-2 md:grid-cols-3 gap-3 md:gap-6 items-start">
    <div class="flex flex-col gap-3 md:gap-6">
      <img class="rounded-xl shadow-sm object-cover w-full h-auto" alt="...">
      <img class="rounded-xl shadow-sm object-cover w-full h-auto" alt="...">
    </div>
    <div class="flex flex-col gap-3 md:gap-6 mt-8 md:mt-12">
      <img class="rounded-xl shadow-sm object-cover w-full h-auto" alt="...">
      <img class="rounded-xl shadow-sm object-cover w-full h-auto" alt="...">
    </div>
    <div class="hidden md:flex flex-col gap-6 mt-24">
      <img class="rounded-xl shadow-sm object-cover w-full h-auto" alt="...">
      <img class="rounded-xl shadow-sm object-cover w-full h-auto" alt="...">
    </div>
  </div>
</div>
```

This staggered, portrait-led gallery is a signature element. Do not replace it with CSS columns, masonry, a uniform card grid, equal-height rows, landscape thumbnails, or a carousel.

### Feature cards

- Grid: `grid-cols-1 md:grid-cols-2 gap-8`.
- Card: `bg-white p-8 rounded-3xl shadow-premium border border-[#FCFBF7]/50 text-center`.
- Hover: `hover:-translate-y-2 transition-transform duration-500`.
- Icon circle: `w-12 h-12 bg-[#FCFBF7] text-[#7F9083] rounded-full`.
- Use simple outline SVGs at about 20px.
- Stagger reveals in 100ms increments.

### Price pill

Use `text-center bg-[#7F9083]/10 rounded-full py-6 px-8 max-w-sm mx-auto border border-[#7F9083]/20`. The label uses Coffee; the price uses bold Sage heading text.

### Suitable / less suitable rows

- Container: `max-w-3xl` with `space-y-12`.
- Row: `flex items-start gap-5 sm:gap-6`.
- Use a small circular icon at the start.
- Suitable uses a Sage check.
- Less suitable uses a Coffee-toned X.
- Do not introduce green/red status colors.

### FAQ

- Use native `<details>` and `<summary>`.
- Stack with `space-y-6`.
- Item: `bg-white rounded-3xl p-6 md:p-8 shadow-sm border border-[#FCFBF7]`.
- Hover: `hover:shadow-md transition-all`.
- Summary: `font-heading text-xl text-[#8E7E73] flex justify-between items-center`.
- Use a Sage down arrow that rotates 180 degrees when open.
- Answer: `mt-4 border-t border-[#7F9083]/10 pt-4 leading-relaxed font-light`.
- Remove the browser's default marker.

### Testimonials

- Section: `py-20 px-6 bg-[#8E7E73]/5`.
- Two-column desktop grid with `gap-8`.
- Shell: `bg-[#FCFBF7] p-4 md:p-6 rounded-3xl shadow-sm border border-white`.
- Image: `w-full max-w-sm rounded-xl shadow-sm`.
- Center each screenshot inside its shell with `flex items-center justify-center`.
- Show the complete testimonial screenshot at its natural aspect ratio. Do not crop it, stretch it, use `object-cover`, force equal image heights, or make it fill the card vertically.
- Keep the generous Vanilla space around the screenshot. The outer rounded card and the inner rounded screenshot are both visible parts of the original design.

Canonical structure:

```html
<div class="grid grid-cols-1 md:grid-cols-2 gap-8">
  <div class="bg-[#FCFBF7] p-4 md:p-6 rounded-3xl shadow-sm border border-white flex items-center justify-center">
    <img class="w-full max-w-sm rounded-xl shadow-sm" alt="...">
  </div>
</div>
```

### Final CTA

- Use `py-32 px-6` and center inside `max-w-4xl`.
- H2: `text-4xl md:text-5xl`.
- Copy: `max-w-2xl text-lg md:text-xl text-[#8E7E73]/80 mb-16 font-light leading-relaxed`.
- Finish with one large Sage WhatsApp button.

### Footer

- Coffee background and Vanilla text.
- Centered layout with `py-16`.
- Logo: `w-40 opacity-80`; use a light monochrome treatment where required.
- Copyright: small, light text at 70% opacity.

### Floating WhatsApp action

- `fixed bottom-6 left-6 z-50`.
- Circular Sage surface with `p-4`; Vanilla icon at `w-8 h-8`.
- Soft Sage shadow and `hover:scale-110` over 300ms.
- Use the breathing animation.
- Include a descriptive Hebrew `aria-label`.

## 8. Photography direction

Photography carries most of the visual emotion. Choose images that are candid, relational, softly lit, warm, neutral, intimate, and consistent in color temperature. Favor gestures and real family interaction.

Avoid harsh flash, dramatic grading, busy props, artificial poses, thick frames, or decorative overlays.

- Use meaningful Hebrew `alt` text.
- Preserve natural aspect ratios in editorial galleries and testimonial screenshots.
- Keep `rounded-xl` and `shadow-sm` consistent.
- Treat gallery photographs and testimonial screenshots as two distinct image modes: gallery photos appear directly in staggered columns; testimonials sit inside padded Vanilla cards.
- Do not apply the newer pages' masonry, fixed-aspect card, full-bleed, or linked-tile image treatments.
- Never invent image URLs or replace missing approved photos with unrelated stock imagery.

## 9. Motion

```css
.reveal {
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.9s cubic-bezier(0.16, 1, 0.3, 1);
}
.reveal.active {
  opacity: 1;
  transform: translateY(0);
}
```

Observe `.reveal` elements with `IntersectionObserver` at `threshold: 0.15`. Add `.active` once visible and unobserve the element.

```css
@keyframes pulse-soft {
  0% { box-shadow: 0 0 0 0 rgba(127, 144, 131, 0.4); }
  70% { box-shadow: 0 0 0 15px rgba(127, 144, 131, 0); }
  100% { box-shadow: 0 0 0 0 rgba(127, 144, 131, 0); }
}
.btn-breathe { animation: pulse-soft 3s infinite; }
```

Motion must remain slow and soft. Do not use parallax, bouncing, autoplay, fast fades, or large transforms. Disable nonessential animation for `prefers-reduced-motion: reduce` while preserving the same static design.

## 10. Responsive and RTL rules

- Every page is Hebrew RTL: `lang="he" dir="rtl"`.
- Mobile is the base layout.
- Hero type grows from 4xl to 6xl; body type grows from lg to xl.
- Feature cards move from one column to two at `md`.
- The gallery moves from two columns to three at `md`; hide the third column below `md`.
- A long CTA may be full width on small screens.
- Use `overflow-x-hidden` on the body.
- Test long Hebrew headings for natural wrapping.
- Keep the floating WhatsApp control on the left, as in the reference.

## 11. Content tone

Write compassionate, observant, reassuring Hebrew. Help parents notice the beauty and effort already present in their family life.

- Begin with recognition of the parent's real experience.
- Name ordinary family moments concretely.
- Frame photography as a way to pause, see, remember, and regain strength.
- Explain the experience calmly and practically.
- Invite a conversation rather than push a purchase.
- Use short, emotionally clear headings.

Avoid generic luxury language, pressure, guilt, exaggerated scarcity, excessive punctuation, or unsupported promises.

Prices, packages, dates, availability, and service details are page-specific. Use only facts supplied by the user or approved for that exact page.

## 12. Restyling existing pages

1. Keep accurate content, metadata, approved images, and working destinations.
2. Remove visual patterns that do not appear in this guide.
3. Replace colors, fonts, shadows, corners, spacing, and type with the canonical tokens.
4. Rebuild the opening as a logo-led centered hero unless explicitly directed otherwise.
5. Convert suitable galleries to the original narrow, three-column staggered gallery. Remove CSS-column masonry, uniform aspect ratios, fixed heights, image cards, and forced crops.
6. Convert benefit groups to the two-column premium card pattern.
7. Use the compact price pill when there is one offer.
8. Convert FAQs to the canonical native details pattern.
9. End with the canonical CTA, Coffee footer, and floating WhatsApp action.
10. Verify mobile layout, Hebrew RTL flow, links, focus visibility, alt text, and reduced motion.

Do not copy page-specific text, prices, packages, or photographs from the Lifestyle reference into another service page.

## 13. AI quality checklist

- [ ] `orginal.html`, the pasted Lifestyle HTML, and its supplied screenshots were the only visual sources of truth.
- [ ] Existing pages were treated as content to restyle, not as design references.
- [ ] The page uses Vanilla, Coffee, Sage, and White only.
- [ ] Headings and actions use Varela Round; body copy uses Assistant.
- [ ] The layout follows the canonical widths and spacing.
- [ ] The opening is a centered logo-led hero with one primary CTA.
- [ ] Cards, galleries, FAQs, price treatment, footer, and WhatsApp action match this guide.
- [ ] Gallery photos retain their natural proportions in the original staggered columns, and testimonial screenshots remain fully visible inside padded cards.
- [ ] The page remains Hebrew RTL and responsive.
- [ ] Motion uses only the reveal and breathing patterns.
- [ ] Missing facts, images, and URLs were not invented.
- [ ] Page-specific information was preserved and not copied from another service.
- [ ] Accessibility improvements preserve the reference's visual language.

## 14. Ready-to-use AI instruction

> Restyle or create the requested Hebrew RTL page using `STYLE_GUIDE.md` as the sole visual source of truth. The guide was derived exclusively from `orginal.html`, the pasted Lifestyle Session reference, and the supplied original screenshots; do not infer design rules from the existing website pages. Preserve accurate page-specific content, metadata, approved images, and destinations, but align the page's palette, typography, spacing, layout, components, imagery treatment, and motion with the guide. Preserve the original narrow staggered gallery with natural image proportions and the fully visible testimonial screenshots inside padded cards. Do not invent business facts, prices, packages, image URLs, or links. Verify mobile and desktop layout, RTL flow, accessibility, and reduced motion before returning the completed page.
