# Design System Strategy: The Gilded Loom

## 1. Overview & Creative North Star: "The Digital Atelier"
This design system is not a utility; it is a digital manifestation of craftsmanship. Our Creative North Star, **"The Digital Atelier,"** reimagines the wholesaler’s interface as a high-fashion editorial spread. We move away from the "grid-of-boxes" commodity feel and toward a curated, cinematic experience.

To break the "template" look, designers must embrace **intentional asymmetry**. Align large display typography to the left while offsetting imagery to the right, allowing the `surface` to breathe. We utilize overlapping elements—such as a product image bleeding over a `surface-container` edge—to create a sense of physical depth and "couture" intentionality.

## 2. Color & Atmospheric Depth
Our palette is rooted in the interplay between the depths of an emerald forest and the shimmer of woven silk.

### The "No-Line" Rule
Traditional 1px solid borders are strictly prohibited for sectioning. Structural boundaries must be defined through **Background Tonal Shifts**. For example, a section using `surface-container-low` should transition directly into `surface` without a stroke. This creates a seamless, "liquid" transition between content areas.

### Surface Hierarchy & Nesting
Treat the UI as stacked sheets of fine textile.
*   **Base:** `surface` (#161307) acts as the dark, velvet floor.
*   **Sections:** Use `surface-container-low` to define large content areas.
*   **Elements:** Use `surface-container-highest` for interactive cards or modals to pull them toward the user.
*   **The Glass & Gradient Rule:** For primary CTAs and Hero backgrounds, use a subtle radial gradient transitioning from `primary_container` (#0D1F1A) to a slightly lighter custom tint. This mimics the way light hits silk.

## 3. Typography: Editorial Authority
The contrast between our serif and sans-serif choices defines our "Traditional yet Modern" mood.

*   **Display & Headlines (Cormorant Garamond / Noto Serif):** Used for storytelling. `display-lg` should be treated as a visual element, often using `secondary` (Gold) or `on-surface` with increased letter spacing for a "luxury masthead" feel.
*   **Body & UI (DM Sans / Manrope):** Used for functional clarity. `body-md` is the workhorse. It must always maintain high contrast (`on-surface`) to ensure readability against the dark emerald depths.
*   **Labeling:** `label-sm` should frequently use uppercase with 10% letter spacing to evoke the feel of a garment's care label or a high-end gallery tag.

## 4. Elevation & Depth: Tonal Layering
We do not use standard shadows; we use **Ambient Glows**.

*   **The Layering Principle:** Place a `surface-container-lowest` (#110E03) card atop a `surface-container` (#232011) to create a "recessed" look, or vice versa to create a "lifted" look.
*   **Ambient Shadows:** For floating elements (Modals/Dropdowns), use an extra-diffused shadow: `box-shadow: 0 20px 50px rgba(13, 31, 26, 0.5)`. The shadow color is a dark emerald tint, not black, to maintain color harmony.
*   **The "Ghost Border" Fallback:** If containment is required for accessibility, use a "Ghost Border": `outline-variant` (#424845) at **15% opacity**. It should feel like a suggestion of an edge, not a hard stop.
*   **Glassmorphism:** Apply `backdrop-filter: blur(12px)` and a background of `surface_variant` at 60% opacity for navigation bars and overlays. This allows the richness of the emerald backgrounds to bleed through.

## 5. Component Signature Styles

### Buttons: The Silk Shimmer
*   **Primary:** `secondary` (#E6C364) background with `on-secondary` (#3D2E00) text. Apply a subtle linear gradient (45deg) to mimic a "shimmer" effect. 
*   **Tertiary/Ghost:** No background. Use `secondary` for text with a `label-md` style. Hover state triggers a 1px "Ghost Border" at 20% opacity.
*   **Rounding:** Use `sm` (0.125rem) for a sharp, tailored look. Avoid "full" pill shapes as they feel too casual for this brand.

### Cards & Lists: The Seamless Flow
*   **Interaction:** Cards use `surface-container-highest`. Never use dividers. 
*   **The Gold Edge:** Use a `secondary_fixed_dim` (#E6C364) border at 0.5px thickness, but only at 30% opacity, to create a faint metallic "fleck" around the container.
*   **Spacing:** Use generous vertical padding (`2rem`+) to separate list items rather than lines.

### Input Fields
*   **Style:** Underline only. Use `outline` (#8C928F) for the default state and `secondary` (Gold) for the focus state. This mimics the elegance of a signature line on a luxury contract.

### Special Component: The Fabric Loupe
*   A custom hovering state for product images that uses a circular glassmorphic "magnifier" with a `secondary` (Gold) rim, allowing users to see textile weaves in high definition.

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical margins. A 12-column grid is a guide, not a cage. 
*   **Do** use `secondary` (Gold) sparingly. It is a highlight, like jewelry; if everything is gold, nothing is premium.
*   **Do** utilize "Warm White" (`on-surface`) for all primary text to avoid the harshness of pure white against emerald.

### Don’t:
*   **Don’t** use "Drop Shadows" that are grey or black. They muddy the emerald tones.
*   **Don’t** use 1px solid dividers. Use white space or a change in `surface-container` tier.
*   **Don’t** use "Pill" shapes or high roundedness. Stay within the `sm` to `md` scale (0.125rem - 0.375rem) to maintain a sophisticated, architectural edge.
*   **Don’t** use standard iconography. Icons should be ultra-thin (1pt stroke) to match the refinement of Cormorant Garamond.