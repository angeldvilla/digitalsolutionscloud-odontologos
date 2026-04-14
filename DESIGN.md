# Design System Specification: The Clinical Sanctuary

## 1. Overview & Creative North Star
The objective of this design system is to transcend the sterile, "template-based" nature of traditional medical interfaces. We are moving toward a **"Clinical Sanctuary"**—an editorial-inspired digital experience that balances surgical precision with human warmth. 

Instead of a rigid, predictable grid, we utilize **Intentional Asymmetry**. By allowing imagery to break container bounds and utilizing extreme shifts in typography scale, we create a sense of bespoke care. This system moves away from "standard" blue-and-white layouts by introducing sophisticated tonal depth and tactile, 3D interactions that make the digital feel physical and trustworthy.

---

## 2. Color & Surface Philosophy
The palette is grounded in medical trust but elevated through a tiered surface architecture.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning or container definition. Boundaries must be defined solely through background color shifts or subtle tonal transitions.
*   *Example:* A `surface-container-low` section sitting on a `surface` background.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—like stacked sheets of frosted glass.
*   **Level 0 (Base):** `surface` (#f6fafe)
*   **Level 1 (Sections):** `surface-container-low` (#f0f4f8)
*   **Level 2 (Cards/Interaction):** `surface-container-lowest` (#ffffff)
*   **Level 3 (Pop-overs/Modals):** `surface-bright` (#f6fafe)

### The "Glass & Gradient" Rule
To prevent a "flat" appearance, use Glassmorphism for floating navigation and secondary UI elements. Apply `backdrop-blur: 12px` and a semi-transparent `on-surface` color at 5% opacity.
*   **Signature Textures:** Use subtle linear gradients for primary CTAs (e.g., `primary` #006591 to `primary-container` #0ea5e9) to provide a "glow" that feels intentional and premium.

---

## 3. Typography
We use a high-contrast pairing: **Manrope** for authoritative editorial headlines and **Inter** for high-legibility clinical data.

| Role | Font | Size | Weight | Tracking |
| :--- | :--- | :--- | :--- | :--- |
| **Display-LG** | Manrope | 3.5rem | 700 | -0.02em |
| **Headline-MD**| Manrope | 1.75rem | 600 | -0.01em |
| **Title-LG** | Inter | 1.375rem | 500 | Normal |
| **Body-LG** | Inter | 1rem | 400 | Normal |
| **Label-MD** | Inter | 0.75rem | 600 | 0.05em (Caps) |

**Editorial Application:** Use `display-lg` for hero statements with significant negative space. Offset body text to the right of the headline to create a sophisticated, asymmetrical flow.

---

## 4. Elevation & Depth
This design system rejects heavy, dark drop shadows in favor of **Tonal Layering** and **Ambient Light**.

*   **The Layering Principle:** Place a `surface-container-lowest` card on a `surface-container-low` background to create a soft, natural lift without a shadow.
*   **Ambient Shadows:** For floating elements, use a shadow with a 40px blur and 4% opacity, tinted with the `primary` color (#006591). This mimics natural light passing through a medical environment.
*   **The "Ghost Border" Fallback:** If a container requires further definition for accessibility, use the `outline-variant` (#bec8d2) at **15% opacity**. Never use a 100% opaque border.
*   **3D Presence:** Interactive cards must utilize a subtle `perspective(1000px)` with a 1-2 degree `rotateX` and `rotateY` on hover to simulate a physical card being touched.

---

## 5. Components

### Elegant Buttons
*   **Primary:** `primary` (#006591) background with a subtle transition to `primary-container` (#0ea5e9). 
*   **Shape:** `md` (0.375rem) corner radius for a professional, slightly softened edge.
*   **Interaction:** On hover, the button should scale to 102% with a `box-shadow` expansion of 8px.

### 3D Perspective Cards
*   **Structure:** `surface-container-lowest` (#ffffff) background. No border.
*   **State:** On hover, apply a subtle 3D rotation and increase the elevation. 
*   **Content:** Forbid divider lines. Separate content using the Spacing Scale (e.g., 24px vertical padding) or a `surface-container` background shift for the card footer.

### Signature Input Fields
*   **Style:** Underline-only or subtle `surface-variant` fills.
*   **Focus:** Transition the label from `on-surface-variant` to `primary` while shifting the background to `surface-container-lowest`.
*   **Soft Green Indicators:** Use `secondary` (#006c49) for "success" micro-interactions, such as a checkmark appearing after valid medical form entry.

### Floating Navigation
*   **Style:** Use a Glassmorphic pill-shape (`full` radius) centered at the bottom or top of the viewport.
*   **Blur:** `backdrop-filter: blur(20px)`.

---

## 6. Do’s and Don'ts

### Do
*   **Do** use asymmetrical layouts where images overlap section boundaries to create depth.
*   **Do** utilize "high white space"—if a section feels full, double the padding.
*   **Do** use `soft green` (#10b981) sparingly for wellness-related highlights and "Healthy" status indicators.
*   **Do** ensure all animations use a `cubic-bezier(0.23, 1, 0.32, 1)` (Ease Out Quint) for a premium, weighted feel.

### Don’t
*   **Don’t** use black (#000000). Use `on-surface` (#171c1f) for text to maintain a soft, high-end look.
*   **Don’t** use 1px solid dividers. Use whitespace or a 1px height `surface-variant` (#dfe3e7) line at 20% opacity if absolutely necessary.
*   **Don’t** use "bouncy" animations. All motion must feel smooth, clinical, and controlled.
*   **Don’t** stack more than three levels of surfaces; complexity leads to visual clutter.