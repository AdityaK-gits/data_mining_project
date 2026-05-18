# Customer Cluster Atlas

A polished single-page customer segmentation demo built as a standalone `index.html` web app.

This project compares **k-Means** and **k-Medoids** clustering on the classic Mall Customers dataset, and lets users upload their own customer CSV file to run the same cluster analysis with interactive charts, auto-generated insights, and exportable results.

## What it does

- Loads a default Mall Customers dataset from a built-in CSV
- Parses additional customer CSV uploads using `PapaParse`
- Maps uploaded columns to `Customer ID`, `Gender`, `Age`, `Annual Income`, and `Spending Score`
- Runs both k-Means and k-Medoids clustering client-side
- Displays interactive visualizations with `Plotly`
- Shows elbow and silhouette analysis
- Generates cluster profiles, segment personas, and comparison metrics
- Saves run history to Firebase Firestore when available, with a browser local-storage fallback
- Exports labeled CSV results for the active dataset

## Files included

- `index.html` — the full app, UI, charting, clustering logic, CSV parsing, and Firebase integration
- `firebase.json` — Firebase Hosting configuration
- `.firebaserc` — Firebase project alias configuration

## Technologies used

- HTML/CSS/JavaScript
- Firebase Hosting + Firestore
- Plotly.js for charts
- PapaParse for CSV parsing
- Firebase Web SDK (compat mode)

## How to use

1. Open `index.html` in your browser.
2. Click **Load standard dataset** to load the built-in Mall Customers data.
3. Adjust cluster settings if desired.
4. Click **Run clustering now** or **Run comparison**.
5. Review visualizations, metrics, and personas.
6. Optionally upload your own customer CSV file and map its columns.
7. Download the labeled output using the download button.

## Local preview

To preview locally, simply open `index.html` in a browser.

If you want a local HTTP server, use any static server tool you prefer, for example:

```bash
# Using Python 3
python -m http.server 8000
```

Then open `http://localhost:8000`.

## Deploy with Firebase

This repo includes Firebase Hosting configuration. If you already have the Firebase CLI installed and authenticated:

```bash
firebase deploy
```

If your Firebase project is not already initialized locally, run:

```bash
firebase init hosting
```

Then deploy again.

## Firebase note

The app includes Firebase config values in the frontend. This is expected for a static web app, because Firebase security is enforced through Firestore rules.

If Firestore writes are blocked by your rules, the app still works and keeps run history in the browser.

## Recommended dataset format

The default dataset uses columns similar to:

- `CustomerID`
- `Genre` / `Gender`
- `Age`
- `Annual Income (k$)`
- `Spending Score (1-100)`

When uploading a different CSV, map the appropriate columns to these fields before analyzing.

## Project purpose

This project is ideal for a data mining or machine learning portfolio entry. It showcases:

- algorithm comparison
- interactive data visualization
- user-driven CSV upload and column mapping
- practical business-facing segmentation insights

## License

No license specified.
