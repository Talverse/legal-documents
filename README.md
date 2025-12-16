# Legal Documents Repository

This repository contains the official legal documents for our products, including Privacy Policies and Terms & Conditions. It is structured to keep the latest version of each document in the main branch while maintaining versioning inside the files themselves for audit purposes.

---

## Repository Structure

```
legal-documents/
├── 7grains/
│   ├── privacy-policy.md          # Latest Privacy Policy for 7grains
│   ├── terms-and-conditions.md    # Latest Terms & Conditions for 7grains
│   └── README.md                  # Optional README for product-specific info
└── README.md                      # Root README (this file)
```

### Notes on Structure

- Each product has its own folder (currently only **7grains**)
- Each legal document is a single file (Markdown) with the version and effective date in the header
- Old versions are preserved automatically in Git history, so you can always view or restore previous versions if needed

---

## File Versioning

Each document file should contain a header like this:

```markdown
---
Document: Privacy Policy
Version: 1.0
Effective Date: 2025-12-15
---

# Privacy Policy

Document content goes here...
```

### Versioning Rules (Semantic Versioning)

- The **Version** field is mandatory.
- The version must follow the format:  
  **`number.number`** (e.g., `1.0`, `1.1`, `2.0`).
- Versions must be incremented sequentially based on the current version.
- If the **Version** field is missing or invalid, the system will **break / throw an error**.
- The file in the **main** branch always represents the **latest published version** of the document.

⚠️ **Important:** Always increment the version number when updating document content.

> **Note:** The file in the main branch always represents the latest published version.

---

## Update Workflow

Whenever a new version of a document is required, follow this workflow:

### 1. Create a feature branch from main

```bash
git checkout -b privacy-policy-v1.1.0
```

### 2. Update the document

- Edit the Markdown file (e.g., `privacy-policy.md`)
- Update the version and effective date in the file header
- Make sure the content is final and approved

### 3. Commit your changes

```bash
git add 7grains/privacy-policy.md
git commit -m "Update Privacy Policy to v1.1.0"
```

### 4. Create a Merge Request (MR) in GitLab

- Request review and approval from the legal team
- Once approved, merge into main

### 5. Post-merge

The merged file is now the latest version. Optionally, tag the commit for major releases:

```bash
git tag privacy-policy-v1.0
git push origin privacy-policy-v1.1
```

---

## Fetching Legal Documents

Always fetch the latest version using the raw file URL:

```
https://raw.githubusercontent.com/Talverse/legal-documents/main/7Grains/privacy-policy.md
https://raw.githubusercontent.com/Talverse/legal-documents/main/7Grains/terms-and-conditions.md
```

- No need to specify a version in the URL
- Your application can always display the latest approved policy using this consistent URL

---

## Audit and History

- Previous versions are stored in Git history automatically
- You can view them using:

```bash
git log -p 7grains/privacy-policy.md
```

- **Optional:** Maintain a `CHANGELOG.md` per document for a summary of changes

---

## Notes

- Currently, this repo contains legal documents for **7grains** only
- The same structure and workflow can be used for future products

---

## License

These documents are proprietary and confidential. Unauthorized distribution is prohibited.