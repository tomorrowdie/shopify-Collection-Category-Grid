# Horizontal Scroll Feature (v2.0)

## What's New?

You can now choose between **two mobile layouts**:

### 1. Grid Layout (Previous Default)
- Shows 2 blocks side by side
- Wraps to new rows if more than 2 blocks
- Requires vertical scrolling

### 2. Horizontal Scroll (New! Like Adidas)
- Shows 2 blocks at a time
- Swipe left/right to see more
- No wrapping to new rows
- Smooth scrolling experience
- Small scrollbar indicator at bottom

---

## How It Works

### Mobile (< 768px):
**Horizontal Scroll Mode:**
```
┌──────────┬──────────┐ ← Swipe left to see more
│ BLOCK 1  │ BLOCK 2  │───┐
└──────────┴──────────┘   │ BLOCK 3 (hidden, scroll to view)
     ━━━━━━━━━━━━━          ← Scrollbar
```

**Grid Mode:**
```
┌──────────┬──────────┐
│ BLOCK 1  │ BLOCK 2  │
└──────────┴──────────┘
┌──────────┐
│ BLOCK 3  │
└──────────┘
```

### Desktop (≥ 768px):
Both modes display as a regular grid (2-6 columns, customizable)

---

## How to Use

### Step 1: Add/Update Section
1. Go to **Shopify Admin** → **Themes** → **Edit code**
2. Update `sections/collection-category-grid.liquid` with the new code
3. Save

### Step 2: Choose Layout
1. Go to **Themes** → **Customize**
2. Navigate to your collection page
3. Click on the **Collection Category Grid** section
4. Find the setting: **"Mobile Layout"**
5. Choose:
   - **Grid (2 columns)** - Traditional grid
   - **Horizontal Scroll** - Swipeable carousel ✨
6. Save

---

## Features

### Horizontal Scroll Layout Includes:

✅ **Smooth Scrolling** - Native mobile swipe gestures
✅ **Snap Points** - Blocks snap into place when scrolling
✅ **Touch Friendly** - Works perfectly with finger swipes
✅ **Scrollbar Indicator** - Small bar shows scroll position
✅ **No JavaScript** - Pure CSS solution (lightweight!)
✅ **Shows 2 Blocks** - ~45% width each with gap
✅ **Momentum Scrolling** - iOS-style smooth momentum

---

## Technical Details

### CSS Features Used:
```css
overflow-x: auto;              /* Enable horizontal scroll */
scroll-snap-type: x mandatory; /* Snap to blocks */
-webkit-overflow-scrolling: touch; /* Smooth iOS scrolling */
scroll-behavior: smooth;       /* Smooth scroll animation */
```

### Block Sizing:
- Each block: 45% width (shows ~2.2 blocks for peek effect)
- Gap: 10px between blocks
- Snap alignment: start of each block

### Scrollbar Styling:
- Height: 3px (subtle)
- Color: #888 (gray)
- Track: #f1f1f1 (light gray)
- Rounded corners

---

## Comparison: Grid vs Scroll

| Feature | Grid Layout | Horizontal Scroll |
|---------|-------------|-------------------|
| **Blocks Visible** | All (with scrolling down) | 2 at a time |
| **Scrolling** | Vertical | Horizontal |
| **Wrapping** | Yes | No |
| **Like Adidas?** | No | Yes ✅ |
| **Best For** | Few blocks (2-4) | Many blocks (4+) |
| **UX Style** | Traditional | Modern |

---

## When to Use Each Layout

### Use **Grid Layout** when:
- You have 2-4 blocks total
- You want all visible without scrolling
- Traditional layout is preferred
- Vertical scrolling is fine

### Use **Horizontal Scroll** when:
- You have 4+ blocks
- You want Adidas-style UX
- Mobile experience is priority
- Modern, app-like feel desired

---

## Browser Support

✅ **Chrome** (Mobile & Desktop)
✅ **Safari** (iOS & macOS)
✅ **Firefox** (Mobile & Desktop)
✅ **Edge** (Mobile & Desktop)
✅ **Samsung Internet**

---

## Customization

### Change Block Width:
Find this line (around line 65):
```css
flex: 0 0 45%;
```
Change `45%` to:
- `50%` - Shows exactly 2 blocks (no peek)
- `40%` - Shows more of the 3rd block (more peek)
- `48%` - Slightly smaller gap

### Change Scrollbar:
```css
height: 3px;    /* Make it thicker/thinner */
background: #888; /* Change color */
```

### Remove Scrollbar Completely:
```css
.collection-category-grid.mobile-scroll .category-grid-wrapper::-webkit-scrollbar {
  display: none; /* Hide scrollbar */
}
```

---

## FAQ

**Q: Can I make it scroll on desktop too?**
A: Yes! Just remove the `@media (max-width: 767px)` wrapper from the scroll CSS.

**Q: Can I add scroll arrows?**
A: For pure CSS, no. But you could add JavaScript buttons to scroll left/right.

**Q: Does it work on all phones?**
A: Yes! It uses native browser scroll, so it works everywhere.

**Q: Why 45% width instead of 50%?**
A: The 45% shows a "peek" of the next block, indicating there's more content to scroll.

**Q: Can I change the default?**
A: Yes, change `"default": "scroll"` to `"default": "grid"` in the schema.

---

## Next Steps

Want to enhance further? Consider adding:
- Scroll dots indicator (requires JS)
- Auto-play carousel (requires JS)
- Prev/Next arrows (requires JS)
- Different mobile widths per block
- Fade-out effect on edges

These would be great additions for v2.1 or v3.0!

---

**Version**: 2.0
**Feature**: Horizontal Scroll Layout
**Date**: October 20, 2025
**Status**: ✅ Production Ready
