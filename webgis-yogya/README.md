# WebGIS Pneumonia Yogyakarta

Simple WebGIS demo showing pneumonia case counts per kecamatan in Yogyakarta.

## Project structure

- `index.html` — main page
- `css/style.css` — styles
- `js/app.js` — map logic (MapLibre + proj4)
- `data/` — GeoJSON dataset (`Pneumonia yogya.geojson`)

## Run locally

Serve the folder with a local web server (recommended):

Using Python 3:

```powershell
cd "d:\OneDrive\Documents\webgis-yogya"
python -m http.server 8000
# open http://localhost:8000 in your browser
```

Using VS Code Live Server:

- Install the Live Server extension
- Open `index.html` and click "Go Live"

## Prepare and upload to GitHub (one-time setup)

1. Install Git: https://git-scm.com/downloads
2. From PowerShell in project folder:

```powershell
cd "d:\OneDrive\Documents\webgis-yogya"
# initialize repo
git init
git add .
git commit -m "Initial commit: WebGIS Pneumonia Yogyakarta"

# create a remote repository on GitHub (via website or GitHub CLI)
# then add remote (replace YOUR_REMOTE_URL):
# git remote add origin https://github.com/USERNAME/REPO.git
# push to GitHub
git branch -M main
git push -u origin main
```

### Create repository on GitHub (web)

- Go to https://github.com/new
- Enter repo name and visibility
- Click "Create repository"
- Follow the instructions to add the `origin` remote and push

### Create repository with GitHub CLI (optional)

Install GitHub CLI: https://cli.github.com/

```powershell
# after installing and authenticating:
gh repo create YOUR_USERNAME/REPO --public --source="." --remote=origin
git push -u origin main
```

## Notes

- If you prefer not to publish the `data/` folder, add `data/*.geojson` to `.gitignore` before committing.
- The GeoJSON in `data/` appears to use UTM coordinates; the app uses `proj4` to reproject to WGS84. If the map looks misplaced, ensure reprojection is correct or provide a WGS84 GeoJSON.

