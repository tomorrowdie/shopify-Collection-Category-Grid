# Shopify Collection Category Grid

A simple, customizable category grid section for Shopify collection pages. Add image-based navigation to your collections with this easy-to-install Liquid section.

![Demo](https://via.placeholder.com/1200x400/4A90E2/FFFFFF?text=Collection+Category+Grid)

## Features

- ✅ Fully responsive (mobile, tablet, desktop)
- ✅ Easy customization through Shopify Theme Editor
- ✅ Unlimited category blocks
- ✅ Works with any Shopify theme
- ✅ No apps required

## Installation

### Step 1: Add the Section File

1. Go to your Shopify Admin
2. Navigate to **Online Store** → **Themes**
3. Click **Actions** → **Edit code**
4. In the **Sections** folder, click **Add a new section**
5. Name it `collection-category-grid`
6. Copy the code from `collection-category-grid.liquid` and paste it
7. Click **Save**

### Step 2: Add to Your Collection Page

1. Go to **Online Store** → **Themes** → **Customize**
2. Navigate to a Collection page using the top dropdown
3. Click **Add section**
4. Select **Collection Category Grid**
5. Position it where you want (typically below the banner)
6. Click **Save**

### Step 3: Customize

1. Click on the section to open settings
2. Set the number of columns (2-6)
3. Click **Add block** to add category tiles
4. For each block:
   - Upload an image
   - Add a heading (e.g., "MEN", "WOMEN", "KIDS")
   - Set the collection URL (e.g., `/collections/mens-clothing`)
5. Click **Save**

## Usage Examples

### Fashion Store
- MEN → `/collections/mens`
- WOMEN → `/collections/womens`
- KIDS → `/collections/kids`
- SHOES → `/collections/shoes`
- ACCESSORIES → `/collections/accessories`

### Sale/Outlet Section
- 30% OFF → `/collections/sale-30`
- 50% OFF → `/collections/sale-50`
- CLEARANCE → `/collections/clearance`
- NEW MARKDOWNS → `/collections/new-markdowns`

## Customization

### Change Number of Columns
In the section settings, adjust "Number of columns on desktop" (2-6)

### Modify Styling
Edit the `<style>` block in the Liquid file to customize:
- Colors
- Spacing
- Hover effects
- Typography
- Image aspect ratio

### Example: Change Hover Effect
Find this in the code:
```css
.category-block:hover {
  transform: translateY(-5px);
}
```

Change to:
```css
.category-block:hover {
  transform: scale(1.05);
}
```

## Troubleshooting

**Section doesn't appear in Theme Editor**
- Make sure you clicked Save after adding the code
- Refresh your browser
- Check the file is named `collection-category-grid.liquid`

**Images not showing**
- Ensure images are uploaded in the block settings
- Try re-uploading the image
- Check image file format (JPG, PNG, WebP)

**Links not working**
- Verify collection URLs are correct (format: `/collections/collection-name`)
- Ensure collections are published
- Check for typos

## Requirements

- Shopify store (any plan)
- Access to theme code editor

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers

## License

Free to use for personal and commercial projects.

## Support

If you find this helpful, please ⭐ star this repository!

For issues or questions, please open an issue on GitHub.

---

Created with ❤️ for the Shopify community