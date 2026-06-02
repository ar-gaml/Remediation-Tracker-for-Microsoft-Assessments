# 🛡️ Remediation Tracker for Microsoft Assessments

A self-contained, Single-file HTML app for tracking remediation findings from Microsoft technology Offline Assessment and On-Demand Assessment assessments (Exchange, Entra ID, Active Directory, ADFS). Import from .docx/.xlsx, track status per finding, add notes, rich-text editing, dark mode, and save everything back into the HTML file. No server required.

---

## ✨ Features

- **Import findings** from Microsoft assessment reports (`.docx` Word files and `.xlsx` Excel files) from Microsoft Offline Assessment Tool
- **Rich finding details** — paste or edit structured content with a full rich-text editor (headings, lists, tables, links, color)
- **Remediation status tracking** — mark each finding as Done, In Progress, or Not Applicable
- **Notes per finding** — attach rich-text notes to any finding
- **Weight-based sorting** — findings sorted by score (High / Medium / Low) automatically
- **Focus Area filtering** — filter the list by any focus area category
- **Live search** — instant full-text search across all findings
- **Save Changes** — bake current data back into the HTML file itself (works offline, no database)
- **Auto-save to localStorage** — changes persist across page refreshes automatically
- **Dark mode** + adjustable text size
- **Export-ready** — the saved HTML file is fully self-contained and portable

---

## 🚀 Getting Started

1. **Download** `RemediationTracker-Entra ID-LabLocal.CC - 27-May-2026.html`
2. **Open** it in any modern browser (Chrome, Edge, Firefox)
3. Click **Import Finding** to add findings manually, or use the **Import On-Demand Assessment** tab to bulk-import from assessment files
4. Set remediation statuses, add notes, and track progress
5. Click **Save Changes** to write everything back into the HTML file

No installation. No dependencies. No server.

---

## 📥 Supported Import Formats

| Source | Format | Notes |
|---|---|---|
| ExRaaS assessments | `.docx` | Uses `WordInsertIssuesAdvancedChunk` altChunk structure |
| ADS / ADSDetailedFindings | `.docx` / `.xlsx` | Uses `Insert_IssueChunk` IDs |
| ADFS / ADFSHCReporter | `.docx` | Inline XML with embedded multi-finding blocks |
| Manual entry | Text (3-line format) | `Name / Focus Area / Weight` per finding |

Libraries used for parsing (loaded on demand from CDN):
- [Mammoth.js](https://github.com/mwilliamson/mammoth.js) — `.docx` parsing
- [SheetJS](https://sheetjs.com/) — `.xlsx` parsing
- [JSZip](https://stuk.github.io/jszip/) — altChunk content resolution

---

## 🗂️ Project Structure

```
Remediation-Tracker-for-Microsoft-Assessments_v11.7.html   ← The entire application (single file)
Copy-Assessment-Results_-_v2.txt         ← Browser bookmarklet: copy one finding's detail from ExRaaS portal
Copy-ALL-Finding.txt                     ← Browser bookmarklet: copy all findings list from ExRaaS portal
```

### Browser Bookmarklets

The two `.txt` files contain JavaScript bookmarklet code you can paste into your browser's developer console (or save as bookmarks) while on the Microsoft ExRaaS assessment portal. They inject copy buttons directly into the portal UI to extract finding data.

---

## 🖥️ Usage

### Adding Findings Manually

Click **Import Finding** in the toolbar → paste findings in the 3-line format:

```
Finding Name = Issue Name
Focus Area = Category
Weight = Severity
```

Repeat for multiple findings (one blank line between each).

### Editing a Finding

- Click the **finding name** to view full details
- Click the **✎ pencil icon** on any row to edit name, focus area, weight, and rich-text details

### Saving

- **Auto-save**: all status/note changes are auto-saved to browser localStorage instantly
- **Save Changes**: bakes the current state into the HTML file itself — use this to create a portable snapshot you can share or archive

---

## 🎨 Screenshots


<img width="1849" height="615" alt="image" src="https://github.com/user-attachments/assets/a3bf4ac0-1757-473b-a44e-935f2bd8e0b6" />

<img width="1845" height="774" alt="image" src="https://github.com/user-attachments/assets/fd5e7b93-d88d-460c-bb81-748ed9661e4a" />


---

## 🤝 Contributing

This tool is purpose-built for Microsoft assessment workflows. Bug reports and suggestions are welcome via [Issues](../../issues).

---

## 📄 License

MIT — free to use, modify, and distribute.

---

_Purpose-built for Microsoft Premier customers and the Microsoft assessment and delivery teams that support them._
