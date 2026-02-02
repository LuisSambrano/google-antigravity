# Vibecode Luxury UI/UX Mandates (Global)

Reference Implementation: `skills/web-development/ui-ux-pro-max`

## 1. The "Gorgeous" Standard

If it looks standard, it is wrong. Every interface must meet the **Premium Threshold**:

1.  **Depth**: Uses shadows, blurs, and layers. No flat designs.
2.  **Motion**: Nothing appears instantly. It flows in.
3.  **Typography**: No generic Inter/Roboto. Use `Outfit`, `Manrope`, or `Space Grotesk` for headers.

## 2. Glassmorphism System

- **Surface**: `bg-black/40` + `backdrop-blur-xl` + `border-white/10`.
- **Highlight**: `bg-gradient-to-b from-white/10 to-transparent`.
- **Shadow**: `shadow-[inset_0_1px_0_0_rgba(255,255,255,0.1)]`.

## 3. Interaction Physics

- **Hover**: Scale `1.02`, Brightness `1.1`.
- **Tap**: Scale `0.98`.
- **Transition**: `duration-300 ease-out`.

## 4. Accessibility Check

- **Contrast**: Always ensure text on glass is readable.
- **Focus**: Visible rings for keyboard users (custom style, not browser default).
