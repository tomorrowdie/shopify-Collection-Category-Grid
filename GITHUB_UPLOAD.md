# How to Upload to GitHub

## Quick Method (Web Upload)

1. Go to https://github.com/new
2. Repository name: `shopify-collection-category-grid`
3. Description: `A customizable category grid section for Shopify collection pages`
4. Make it **Public**
5. **Do NOT** check "Add a README file"
6. Click **Create repository**
7. Click **"uploading an existing file"** link
8. Drag and drop these 3 files:
   - `collection-category-grid.liquid`
   - `README.md`
   - `LICENSE`
9. Click **Commit changes**

Done! ✅

## Command Line Method

```bash
cd shopify-collection-category-grid
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/shopify-collection-category-grid.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username.
