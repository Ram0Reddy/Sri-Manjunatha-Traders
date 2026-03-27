# Design System Strategy: The Architectural Monolith

## 1. Overview & Creative North Star
The North Star for this design system is **"The Architectural Monolith."** 

In the world of building materials, strength isn't just about weight; it’s about precision, structural integrity, and the interplay of raw materials. This system moves away from the "generic e-commerce" look by treating the digital interface as a physical construction site. We utilize **intentional asymmetry**, **tonal layering**, and **editorial-grade typography** to evoke a sense of high-end craftsmanship.

Instead of flat rows of products, we use staggered layouts and varying surface depths to mimic the way materials are showcased in a flagship showroom. The goal is to make Sri Mallikarjuna Traders feel less like a shop and more like an essential partner in a high-stakes construction project.

---

## 2. Colors & Surface Philosophy

Our palette is derived from the core elements of the trade: iron (Deep Blues), stone (Slate Grays), and clay (Terracotta).

### The "No-Line" Rule
**Strict Mandate:** Designers are prohibited from using 1px solid borders to define sections or containers. 
Structure must be established through color-blocking and background shifts. For example:
- A product description section using `surface-container-low` should sit directly against a `surface` background. 
- Use the **Spacing Scale (16 or 20)** to create breathing room that defines boundaries naturally.

### Surface Hierarchy & Nesting
Treat the UI as a series of nested physical plates.
- **Base Layer:** `surface` (#fafaf5) – The "site" foundation.
- **Primary Containers:** `surface-container-low` (#f4f4ef) – Use for large content areas.
- **Interactive Cards:** `surface-container-lowest` (#ffffff) – Use these to "lift" product cards off the page.
- **Feature Callouts:** `surface-container-high` (#e8e8e3) – Use for technical specs or sidebars.

### The Glass & Gradient Rule
To prevent the "sturdy" feel from becoming "heavy," use Glassmorphism for floating elements (like Navigation Bars or Quick-Action Menus). 
- **Token:** `surface` at 80% opacity with a `24px` backdrop blur.
- **Gradients:** Use a subtle linear gradient from `primary` (#002046) to `primary_container` (#1b365d) for Hero CTAs to give them a metallic, polished sheen.

---

## 3. Typography: The Trust Factor

We pair two high-performance typefaces to balance industrial reliability with modern sophistication.

*   **Display & Headlines (Manrope):** A geometric sans-serif that feels engineered. The wide apertures and high x-height suggest transparency and modernity. 
    *   *Usage:* Use `display-lg` for hero statements. Use tight letter-spacing (-0.02em) on headlines to increase the "solid" feel.
*   **Body & Labels (Work Sans):** Optimized for legibility at small sizes. It feels technical and precise—like a blueprint.
    *   *Usage:* Use `body-md` for product descriptions and `label-sm` (all caps, +0.05em tracking) for technical categories like "SKU" or "Material Grade."

---

## 4. Elevation & Depth: Tonal Layering

Traditional shadows are often "muddy." We achieve elevation through color and light.

*   **The Layering Principle:** Instead of a shadow, place a `surface-container-lowest` card on top of a `surface-dim` background. This creates a "soft lift" that feels architectural.
*   **Ambient Shadows:** For floating Modals or Tooltips, use an ultra-diffused shadow:
    *   *Blur:* 40px | *Opacity:* 6% | *Color:* `on-surface` (#1a1c19) tinted with `primary`.
*   **The Ghost Border Fallback:** If a boundary is visually required for accessibility (e.g., Input Fields), use the `outline-variant` (#c4c6cf) at **15% opacity**. Never use 100% opaque lines.
*   **Glassmorphism:** Use semi-transparent `surface-container-lowest` for overlays to ensure the "earth tones" of the background bleed through, maintaining a cohesive atmosphere.

---

## 5. Components: Industrial Precision

### Buttons
*   **Primary:** `primary` background with `on-primary` text. Use `rounded-sm` (0.125rem) to maintain a sharp, chiseled look.
*   **Secondary:** `tertiary_fixed_dim` background. This terracotta tone provides a warm, "earth-based" contrast to the deep blue primary actions.
*   **Interaction:** On hover, shift background to `primary_container`. No shadows.

### Cards & Lists
*   **The "No Divider" Rule:** Forbid 1px horizontal lines between list items. Instead, use a background toggle between `surface` and `surface-container-low`, or simply use `1.5rem` (6) of vertical whitespace.
*   **Layout:** Use asymmetrical padding—for example, `padding-left: 2rem (8)` and `padding-right: 1.25rem (5)`—to create a dynamic, editorial feel for product showcases.

### Input Fields
*   **Form Factor:** Background should be `surface-container-highest` (#e3e3de). 
*   **State:** On focus, the field should not gain a border, but rather a 2px bottom-bar of `primary` (#002046), mimicking a professional drafting tool.

### Specialized Component: The "Spec-Sheet" Chip
*   For construction materials (e.g., Cement Grade, Steel Thickness), use chips with `secondary_container` (#d1e1f4) backgrounds and `on-secondary-container` text. Use `rounded-none` to emphasize the "block" nature of the industry.

---

## 6. Do’s and Don'ts

### Do:
*   **Embrace White Space:** Use the `20` (5rem) and `24` (6rem) spacing tokens between major sections to let the high-end typography breathe.
*   **Layer Surfaces:** Always place lighter surfaces on darker surfaces to create "natural light" hierarchies.
*   **Use Heavy Weights:** Use Bold/Extra Bold for `headline-sm` to make technical specs feel authoritative.

### Don’t:
*   **Don't use Rounded Corners:** Avoid `xl` or `full` roundedness for primary containers. Stay within `none` to `md` to keep the "sturdy" construction aesthetic.
*   **Don't use Pure Black:** Always use `on-surface` (#1a1c19) for text; it preserves the "slate gray" professional tone.
*   **Don't use Standard Grids:** Occasionally break the grid by overlapping a product image (on a `surface-container-lowest` card) over two different background color blocks. This creates the "Editorial" look.