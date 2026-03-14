# Google Sheets Integration — Setup Guide
# Swarajya Hack Fest Project Submission Form

## Overview
The submission form (submission.html) is designed to store responses directly
into a Google Sheet using a Google Apps Script Web App as the backend.
PPT file metadata (filename) is stored in Sheets; the actual file upload
needs a separate Google Drive mechanism (see Option B below).

---

## Step 1 — Create a Google Sheet

1. Go to https://sheets.google.com → Create a new blank spreadsheet
2. Name it: "Swarajya Hack Fest Submissions"
3. Add the following headers in Row 1:
   A: Timestamp
   B: Team Name
   C: Team Leader Name
   D: Team Leader Email
   E: College Name
   F: Member 1 Name
   G: Member 1 Email
   H: Member 2 Name
   I: Member 2 Email
   J: GitHub URL
   K: Live Demo URL
   L: Problem Statement
   M: PPT File Name

---

## Step 2 — Create the Apps Script Web App

1. In your Google Sheet, go to: Extensions → Apps Script
2. Delete any existing code and paste the following:

```javascript
function doPost(e) {
  try {
    var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
    var data = JSON.parse(e.postData.contents);
    sheet.appendRow([
      new Date(),
      data.teamName       || '',
      data.leaderName     || '',
      data.leaderEmail    || '',
      data.college        || '',
      data.member1Name    || '',
      data.member1Email   || '',
      data.member2Name    || '',
      data.member2Email   || '',
      data.github         || '',
      data.liveDemo       || '',
      data.problemStatement || '',
      data.pptFileName    || ''
    ]);
    return ContentService
      .createTextOutput(JSON.stringify({ result: 'success' }))
      .setMimeType(ContentService.MimeType.JSON);
  } catch (err) {
    return ContentService
      .createTextOutput(JSON.stringify({ result: 'error', message: err.toString() }))
      .setMimeType(ContentService.MimeType.JSON);
  }
}

// Test via GET (optional, for debugging only)
function doGet(e) {
  return ContentService.createTextOutput('Apps Script is running!');
}
```

3. Click **Save** (Ctrl+S)
4. Click **Deploy** → **New deployment**
5. Configuration:
   - Type: **Web app**
   - Execute as: **Me** (your Google account)
   - Who has access: **Anyone**
6. Click **Deploy** → Authorize when prompted
7. **Copy the Web App URL** (looks like: https://script.google.com/macros/s/ABC.../exec)

---

## Step 3 — Update submission.html

Open `submission.html` and find this line (near the top of the `<script>` tag):

```javascript
const APPS_SCRIPT_URL = 'YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL_HERE';
```

Replace the placeholder with your copied URL:

```javascript
const APPS_SCRIPT_URL = 'https://script.google.com/macros/s/YOUR_ACTUAL_ID/exec';
```

Save the file and re-deploy your website. Submissions will now appear in your Google Sheet.

---

## PPT File Uploads — Options

### Option A: Manual Collection (Simple)
- The form records the PPT file name in the Google Sheet
- Email participants separately asking them to send the PPT
- Or share a Google Drive folder link for teams to upload their PPT

### Option B: Google Drive Upload (Advanced)
Add a Google Drive File Upload field to a Google Form, link it to your Sheet,
and direct teams to use that Google Form for the PPT upload specifically.
Then use the submission.html form for all other data collection.

### Option C: Firebase Storage (Full Integration)
Use Firebase Storage to handle the actual file upload. The Firebase SDK
can be added to submission.html for direct browser-to-cloud uploads.
Contact the developer to set this up.

---

## Notes
- Each time the Apps Script is re-deployed, the URL stays the same IF you
  select "Manage deployments" → update existing deployment.
- If you create a new deployment, you'll get a NEW URL and need to update submission.html.
- Test the integration by submitting a test form and checking your Google Sheet.
