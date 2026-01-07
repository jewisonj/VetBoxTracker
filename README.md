# 🐴 Vet Box Tracker

A mobile-friendly inventory tracker for veterinary supply boxes. Tap drawers to see compartment contents and target quantities.

![Vet Box Tracker](https://via.placeholder.com/600x400?text=Vet+Box+Tracker+Screenshot)

## 🚀 Quick Start

1. **Fork this repository** to your GitHub account
2. **Enable GitHub Pages**: Settings → Pages → Source: Deploy from branch → Branch: `main` → Save
3. **Wait 1-2 minutes** for deployment
4. **Access your tracker** at: `https://YOUR_USERNAME.github.io/vet-box-tracker/`

## 📝 Editing Inventory

### Option 1: Edit directly on GitHub
1. Click the "Edit Inventory" button in the app, OR
2. Navigate to `inventory.csv` in this repository
3. Click the pencil icon to edit
4. Make changes and commit
5. Refresh the app to see updates

### Option 2: Edit locally
1. Download `inventory.csv`
2. Edit in Excel, Google Sheets, or any text editor
3. Upload the updated file to replace the existing one

## 📋 CSV Format

| Column | Description | Example |
|--------|-------------|---------|
| Drawer | Drawer ID | `1`, `2-Upper`, `6` |
| Compartment | Compartment ID | `A1`, `B2`, `Front` |
| Row | Row number (for reference) | `1`, `2`, `3` |
| Col | Column number (for reference) | `1`, `2` |
| Item | Item name | `Syringes 3ml` |
| TargetQty | Target quantity | `20` |

### Compartment Naming

- **Drawer 1**: A1, A2, B1, B2, C1, C2, D1, D2, E1, E2, F1, F2 (6 rows × 2 cols)
- **Drawer 2-Upper**: A (large), B, C, D (smaller sections)
- **Drawer 2-Lower**: A, B, C, D (2×2 grid)
- **Drawers 3, 4, 5, 8**: Front, Back
- **Drawers 6, 7**: A1-A4, B1-B4, ... H1-H4 (8 rows × 4 cols)

## ⚙️ Configuration

To update the "Edit Inventory" link, edit `index.html` and change:

```javascript
const GITHUB_USER = 'YOUR_GITHUB_USERNAME';
const GITHUB_REPO = 'vet-box-tracker';
```

## 📱 Features

- **Mobile-first design** - Works great on phones and tablets
- **Offline capable** - Cabinet image is embedded in the HTML
- **No backend required** - Pure static hosting
- **Easy updates** - Edit CSV directly on GitHub

## 🔧 Customization

### Change drawer layouts
Edit the `DRAWER_LAYOUTS` object in `index.html` to modify compartment grids.

### Change cabinet image
Replace the base64 image in `CABINET_IMAGE` constant, or modify the code to load an external image.

## 📄 License

MIT License - Feel free to use and modify for your own vet box!
