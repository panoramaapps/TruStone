# Design System Strategy: The Curated Ledger

This design system is built to transform the often-dense, clinical world of insurance data into a high-end, editorial experience. We are moving away from the "standard dashboard" look—cluttered with borders and heavy shadows—and toward a "Curated Ledger" aesthetic. The goal is to provide insurance agents with maximum data density through a sophisticated hierarchy of tonal layers, refined typography, and intentional white space.

## 1. Creative North Star: The Digital Concierge
The "Digital Concierge" philosophy treats every data point as a piece of premium correspondence. We prioritize legibility and calm over visual noise. By using an asymmetric layout and varying levels of surface "elevation" through color rather than lines, we create a sense of organized luxury. The interface should feel like a custom-tailored suit: precise, high-quality, and devoid of unnecessary ornamentation.

---

## 2. Color & Surface Philosophy

### The "No-Line" Rule
To achieve a premium, modern feel, **1px solid borders are strictly prohibited** for sectioning. We define boundaries through background color shifts.
*   **Method:** A `surface-container-low` (`#f0f4f7`) card should sit on a `surface` (`#f7f9fb`) background. The distinction is felt, not seen.
*   **The Ghost Border Fallback:** If a boundary is required for accessibility, use the `outline_variant` at **15% opacity**. Never use 100% opaque lines.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked, semi-transparent layers.
*   **Base:** `surface` (#f7f9fb)
*   **Secondary Content Areas:** `surface_container_low` (#f0f4f7)
*   **Actionable Cards/Modals:** `surface_container_lowest` (#ffffff)
*   **Accents/Sidebars:** `surface_container_high` (#e1e9ee)

### Signature Textures & Glassmorphism
*   **The Glass Effect:** For floating navigation or urgent pop-overs, use `surface_container_lowest` at 80% opacity with a `backdrop-blur` of 20px.
*   **Gradients:** Use a subtle linear gradient for primary CTAs: `primary` (#4059aa) to `primary_dim` (#334d9d) at a 135-degree angle. This adds "soul" to the action buttons without breaking the professional tone.

---

## 3. Typography: Editorial Authority

We utilize two distinct sans-serifs to create an "Editorial High-Contrast" scale. **Manrope** provides a modern, geometric authority for headers, while **Inter** ensures maximum readability for dense insurance data.

*   **Display & Headlines (Manrope):** Use `display-md` (2.75rem) for main dashboard welcomes. Use `headline-sm` (1.5rem) for section headers. These should always use `on_surface` (#2a3439).
*   **Body & Data (Inter):** Use `body-md` (0.875rem) for most table data. This font is engineered for clarity at small sizes.
*   **Semantic Labels:** `label-sm` (0.6875rem) should be used for metadata (e.g., policy numbers) in `on_surface_variant` (#566166) with a tracking (letter-spacing) of +0.02em to maintain an upscale look.

---

## 4. Elevation & Depth: Tonal Layering

Traditional drop shadows are too "standard." We use **Ambient Shadows** and **Tonal Stacking**.

*   **Tonal Stacking:** Instead of a shadow, place a `surface_container_lowest` element inside a `surface_container` area. The 4-5% shift in HEX value creates a natural lift.
*   **Ambient Shadows:** For high-priority floating elements, use a multi-layered shadow:
    *   `box-shadow: 0 10px 30px rgba(42, 52, 57, 0.04), 0 4px 8px rgba(42, 52, 57, 0.02);`
    *   Note: The shadow color is a low-opacity version of `on_surface`, never pure black.
*   **Roundedness:** Use the `lg` (1rem) token for main containers and `md` (0.75rem) for inner cards. This creates a "nested" visual language that feels soft and contemporary.

---

## 5. Component Guidelines

### Buttons (The "Statement" Piece)
*   **Primary:** Gradient of `primary` to `primary_dim`. Roundedness: `full`. Padding: `3.5` (0.75rem) vertical, `6` (1.3rem) horizontal.
*   **Secondary:** `secondary_container` background with `on_secondary_container` text. No border.

### Status Indicators (High-Density Signals)
Avoid large "Status" columns. Use **Minimalist Chips**:
*   **Active (Good):** `tertiary_container` background with `on_tertiary_container` text.
*   **Warning (Expiring):** Use a custom soft yellow (e.g., #fdf0d5) with `on_surface` text.
*   **Critical (Claims):** `error_container` with `on_error_container` text.
*   *Styling:* All chips must use `rounded-full` and `label-sm` typography.

### Input Fields
*   **Resting State:** `surface_container_highest` background, no border.
*   **Focus State:** A 2px "Ghost Border" using `primary` at 40% opacity and a subtle `primary_container` glow.

### Cards & Lists (The "Anti-Divider" Rule)
*   **Forbid dividers.** To separate policy holders in a list, use a vertical spacing of `5` (1.1rem) and a slight background shift on hover (`surface_container_low`).
*   **Data Density:** Use `body-sm` for secondary details to pack more information into the agent's view without creating visual "noise."

---

## 6. Do's and Don'ts

### Do:
*   **Do** use asymmetrical layouts. For example, a wide main ledger on the left with a narrow, high-contrast "Quick Actions" panel on the right using `surface_container_high`.
*   **Do** use `16` (3.5rem) spacing for major section breathing room to offset high data density.
*   **Do** use "Optical Alignment." Icons in buttons should be slightly smaller than the text to ensure the text remains the "hero."

### Don't:
*   **Don't** use 100% black (#000000). Use `on_surface` (#2a3439) for all "black" text to keep the palette sophisticated.
*   **Don't** use standard "Blue" links. Use `primary` with an underline that only appears on hover.
*   **Don't** cram icons into every row. Only use icons for primary status indicators or high-frequency actions.
