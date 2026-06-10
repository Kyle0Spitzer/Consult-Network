# Portfolio Dashboard – Deploy Package

This package was prepared from your HTML dashboard so you can publish it as a shareable web page.

## What is included
- `index.html` → publish-ready dashboard entry point
- `.nojekyll` → ensures GitHub Pages serves the site as-is
- `staticwebapp.config.json` → Azure Static Web Apps friendly configuration
- `Open_Dashboard_Locally.bat` → quick local launch on Windows

---

## Recommended publishing path
Because SharePoint / OneDrive commonly block or restrict JavaScript inside HTML documents, the most reliable approach is:

1. Publish this package to **GitHub Pages** or **Azure Static Web Apps**
2. Put the resulting URL into SharePoint as a link, button, or quick links tile

That gives you:
- full dashboard interactivity
- a normal HTTPS URL
- easy sharing inside your organization

---

## Option A – Publish with GitHub Pages (fastest)

### 1) Create a new GitHub repository
Suggested repository name:
`portfolio-dashboard`

### 2) Upload these files to the root of the repository
Keep `index.html` in the root.

### 3) Turn on GitHub Pages
In GitHub:
- Go to **Settings**
- Go to **Pages**
- Under **Build and deployment**:
  - **Source** = `Deploy from a branch`
  - **Branch** = `main`
  - **Folder** = `/ (root)`

### 4) Wait for the site URL
GitHub will publish the site at a URL similar to:
`https://<your-org-or-user>.github.io/portfolio-dashboard/`

### 5) Add the URL into SharePoint
On your SharePoint page:
- add a **Quick Links** web part
- paste the GitHub Pages URL
- label it as something like **Open Portfolio Dashboard**

---

## Option B – Publish with Azure Static Web Apps (best enterprise option)

### 1) Create a new GitHub repository
Upload these files to the repo root.

### 2) In Azure Portal
- Create a **Static Web App**
- Connect it to the repository
- Use these build settings:
  - **App location**: `/`
  - **Output location**: `/`
  - If Azure asks for an API location, leave it blank if allowed

### 3) Deploy
Azure will create a public HTTPS URL.

### 4) Add the Azure URL into SharePoint
Use the URL in a **Quick Links** web part or button.

---

## Important note about SharePoint / OneDrive direct hosting
Direct opening of HTML files from SharePoint or OneDrive often:
- downloads the file instead of rendering it
- opens it with restricted script execution
- breaks complex dashboards

So the best pattern is:
**Host externally → link from SharePoint**

---

## Quick local test
You can test locally by opening:
- `index.html`
- or double-clicking `Open_Dashboard_Locally.bat`

---

## Suggested next enhancements
If you want, the next upgrade can be:
- adding your corporate logo/favicon
- adding password or AAD-protected hosting guidance
- enabling data refresh from Excel/CSV
- turning team/project data into an editable backend
