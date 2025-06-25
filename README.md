### 🛠️ Features

- Downloads ROM ZIP from a user-provided URL.
- Extracts `payload.bin` from the ZIP.
- Uses [vm03/payload_dumper](https://github.com/vm03/payload_dumper) to extract `boot.img`.
- Uploads the `boot.img` to a GitHub Release named `payload`.

---

## 📥 Usage

### 🔧 Manually Trigger the Workflow

This workflow uses `workflow_dispatch`, so it can be run manually from the **Actions** tab in your GitHub repo.

### ✅ Inputs

| Name | Description | Required |
|------|-------------|----------|
| `url` | Direct download link to the ROM ZIP file containing `payload.bin` | ✅ Yes |

### 🧪 Example

1. Go to the **Actions** tab in your GitHub repo.
2. Select the `Dumper_payload` workflow.
3. Click **Run workflow**.
4. Paste the ROM download link in the input field.
5. Click **Run workflow**.

---

## 📦 Output

Once the job completes:

- The `boot.img` will be extracted and uploaded as a release asset under a GitHub Release tagged `payload`.
- The release will be named `boot_img_dumper`.

---

## 🔐 Requirements

- A GitHub personal access token (`GH_PAT`) must be saved as a repository secret.

### Required Permissions

Ensure the token has the following scopes:
- `repo`
- `workflow`

---

## 📚 Notes

- This workflow expects the ROM ZIP file to contain `payload.bin` at the root level.
- Only `boot.img` is extracted and uploaded. You can modify the workflow to include other images if needed.

---

## 🧾 Credits

- [payload_dumper by vm03](https://github.com/vm03/payload_dumper)
- [softprops/action-gh-release](https://github.com/softprops/action-gh-release)

---
