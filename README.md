# AGRI GUIDE — Dashboard UI

A frontend-only agricultural dashboard prototype.

## Included
- Home Dashboard
- Find My Crop form
- Five-step farm questionnaire with browser-side validation and ranked, explainable crop matches
- Crop Dashboard with search/filter
- Crop Details Dashboard
- Dedicated crop-specific information dashboard with Before, During and After Cultivation sections
- Market Dashboard with demo price chart
- Responsive mobile layout
- Premium, image-led visual layer inspired by the reference's broad design language, with original AGRI GUIDE styling
- Scroll reveals, subtle hero parallax, card/button hover states, sticky navigation transitions and reduced-motion support
- Demo data only
- Crop search and category/season/soil/water filters, with name or duration sorting

## Not included yet
- PHP/backend
- MySQL/database
- Login/authentication
- District-level suitability data and live market recommendations
- Admin panel
- Live market API

## Run in VS Code

1. Extract/open this `agri-guide` folder in VS Code.
2. Open `index.html`.
3. Recommended: install the **Live Server** extension in VS Code.
4. Right-click `index.html` → **Open with Live Server**.
5. The website opens in your browser.

You can also open `index.html` directly, but Live Server is recommended.

## External dependency
The Market page loads Chart.js from jsDelivr for the demonstration chart. The premium hero and page banners load a landscape photograph from Unsplash. The original Kaggle image dataset is bundled under `assets/images/crops/kaggle/`; 17 previously selected crop photos remain at the top level of `assets/images/crops/`. Other crop images may load attributed photographs from Wikimedia Commons. An internet connection is needed for Commons images, the hero photograph and the market chart; all CSS and JavaScript files are local.

## Project structure
agri-guide/
├── index.html
├── find-crop.html
├── crops.html
├── crop-details.html
├── market.html
├── css/
│   ├── style.css
│   ├── responsive.css
│   ├── interactive.css
│   ├── crop-details.css
│   └── premium.css
├── js/
│   ├── main.js
│   ├── validation.js
│   ├── dashboard.js
│   ├── crops.js
│   ├── crop-details.js
│   ├── crop-data.js
│   └── premium.js
└── assets/
    ├── images/
    │   └── crops/ (CC0 crop photos and sourcing details)
    └── icons/

## India-wide expansion
- The original 49-crop catalogue and its data remain in place; 68 entries have been appended, for 117 catalogue entries total. Search, categories and crop-detail routes include the expanded entries.
- The catalogue spans 18 category labels. New entries include preliminary names, categories and botanical/local-name fields where available. Their crop-specific agronomy is explicitly pending authoritative verification and they are excluded from recommendation scoring.
- The Find My Crop State → District selector retains the existing 28 states and 8 Union Territories and adds any additional region labels in `data/india-locations.js`. Its 589 distinct State–District pairs are derived from the CC0 [Kaggle Cities, Towns, Districts, States in India dataset](https://www.kaggle.com/datasets/akshat4112/cities-towns-districts-states-in-india), version 1 (last updated 2020-06-15); city/town entries are not shown. This historical dataset uses some legacy region names and does not cover every current State/UT; unmatched selections show that no districts are available rather than inferring a mapping. District selection does not imply crop suitability, and there are zero verified district-crop or state-crop suitability assignments. See `data/india-regions.js` for the existing state list.
- The Kaggle image-classification dataset has 30 classes and 829 source images. All class images are preserved under `assets/images/crops/kaggle/`; together with the 17 existing selected photos, there are 846 local crop-image files. Kaggle labels are visual references, not agronomic evidence.
- Metadata for the separate Kaggle `Crop Photos Dataset` is recorded in `data/kaggle/crop-photos-dataset.js`. Its listed license is Unknown; none of its 143 reported images have been downloaded, copied, linked, or displayed, and its listing provides no crop-specific labels or agronomic fields.
- Kaggle is the additional dataset source. The crop list was supplied by the user. Crop-specific ICAR, Ministry, state department, university or district records have not been imported for the 68 new entries; no regional suitability is inferred from image classes or state names.
- Added a language selector for English plus India's 22 Scheduled Languages.
- The crop list is a practical major-crop catalogue, not an exhaustive list of every local crop, cultivar or variety. Agricultural suitability is region-specific and should be validated with local agricultural advisories.
- The farm questionnaire uses a transparent rule-based demo score (soil 30%, season 20%, location 20%, water 15%, market 15%). Location and market components remain neutral until verified local data is available; Soil Health Card nutrient bands are educational placeholders, not agronomic thresholds. New crop entries without verified agronomy are not scored or presented as suitable recommendations.
- Crop details use a separate responsive dashboard and one shared crop URL (`crop-details.html?crop=...`). Catalogue facts are demo references; stage guidance is general, and numeric agronomy rates or live prices are intentionally not invented. Validate sowing windows, soil and water needs, inputs, pest/disease management, storage and economics with local agricultural institutions before field use.
- Crop cards and crop detail pages prefer bundled CC0 crop photographs where available, then search Wikimedia Commons for other crops. Image source and license links are displayed beside the photo; Commons results require an internet connection. Existing crop illustrations remain as a fallback. See `assets/images/crops/README.md` for details.
