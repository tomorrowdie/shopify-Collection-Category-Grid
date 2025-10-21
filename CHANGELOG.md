# Changelog

All notable changes to this project will be documented in this file.

## [2.0.0] - 2025-10-20

### 🎉 Added
- **Horizontal Scroll Layout** - New mobile layout option (like Adidas!)
  - Swipeable carousel on mobile
  - Shows 2 blocks at a time with horizontal scroll
  - Smooth scroll snap points
  - Subtle scrollbar indicator
  - Pure CSS solution (no JavaScript)
- **Mobile Layout Setting** - Choose between Grid or Horizontal Scroll
- **Scroll Snap** - Blocks snap into place when scrolling
- **Touch-optimized** - Smooth momentum scrolling on iOS

### 📚 Documentation
- Added HORIZONTAL_SCROLL.md - Complete horizontal scroll guide
- Added V2_QUICKSTART.md - Quick start for v2.0 features
- Updated README.md with v2.0 features

### 🔧 Technical
- Added `.mobile-scroll` class for conditional styling
- Added `mobile_layout` schema setting (select dropdown)
- Flexbox-based horizontal scroll on mobile
- Webkit scrollbar styling for better appearance

---

## [1.1.0] - 2025-10-20

### 🐛 Fixed
- **Mobile Responsive Issue** - Changed from `auto-fit` to fixed 2 columns
  - Was showing 1 block full-width on narrow phones
  - Now always shows 2 blocks side by side on mobile
  - Matches Adidas mobile layout

### ✨ Improved
- Reduced mobile padding (40px → 20px vertical, 20px → 10px horizontal)
- Smaller gap on mobile (20px → 15px)
- Better space utilization on small screens

### 📚 Documentation
- Added MOBILE_FIX.md - Technical explanation of the fix
- Added MOBILE_COMPARISON.md - Visual before/after comparison
- Added UPDATE_GUIDE.md - How to update from v1.0

---

## [1.0.0] - 2025-10-20

### 🎉 Initial Release
- Basic category grid functionality
- Customizable columns (2-6) on desktop
- 2-column grid on mobile
- Responsive design
- Image upload per block
- Heading text per block
- Collection URL linking
- Hover animation effect
- Lazy loading for images
- Placeholder image support
- Theme customizer integration

### 📚 Documentation
- README.md with installation guide
- LICENSE (MIT)
- GITHUB_UPLOAD.md
- START_HERE.md

---

## Upcoming Features (Planned)

### [2.1.0] - Future
- [ ] Product count display per category
- [ ] Sale badge/label support
- [ ] Subtitle/description field
- [ ] Color overlay options
- [ ] Multiple animation options

### [2.5.0] - Future
- [ ] Button/CTA support
- [ ] Text position options
- [ ] Icon support
- [ ] Spacing controls

### [3.0.0] - Future
- [ ] Dynamic collections (auto-populate)
- [ ] Video background support
- [ ] Analytics integration
- [ ] A/B testing support

---

## Version Format

This project follows [Semantic Versioning](https://semver.org/):
- **MAJOR** version (X.0.0) - Breaking changes
- **MINOR** version (0.X.0) - New features (backwards-compatible)
- **PATCH** version (0.0.X) - Bug fixes

---

## Migration Guides

### Upgrading to v2.0 from v1.x
- ✅ Fully backwards compatible
- ✅ No breaking changes
- ✅ New setting defaults to "scroll" for better UX
- ✅ Can switch back to "grid" if preferred
- See: UPDATE_GUIDE.md for step-by-step instructions

### Upgrading to v1.1 from v1.0
- ✅ Backwards compatible
- ✅ Mobile layout automatically improved
- ✅ No settings changes needed
- See: MOBILE_FIX.md for technical details

---

## Support

- 📖 Documentation: See README.md
- 🐛 Bug reports: Open an issue on GitHub
- 💡 Feature requests: Open an issue on GitHub
- ⭐ If you find this helpful, star the repo!

---

Last updated: October 20, 2025
