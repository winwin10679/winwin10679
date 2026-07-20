


 its `README.md` (this file) appears on your GitHub profile.

d:

-
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
 requests
import ase64
import zipfile
import io
 

# ----------------------------
# 1️⃣  BASIC SETTINGS
# ----------------------------
owner = "OWNER"          # e.g. "torvalds"
repo  = "REPO"           # e.g. "linux"
branch = "main"          # or the default branch you need
# If the repo is private, set a token here:
# token = "ghp_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
# headers = {"Authorization": f"token {token}"}
headers = {}  # public repo needs no auth

# ----------------------------
# 2️⃣  FETCH ZIP ARCHIVE (quickest way to get the whole repo)
# ----------------------------
zip_url = f"https://api.github.com/repos/{owner}/{repo}/zipball/{branch}"
resp = requests.get(zip_url, headers=headers)
resp.raise_for_status()

# Unpack the zip into a local folder
zip_bytes = io.BytesIO(resp.content)
with zipfile.ZipFile(zip_bytes) as z:
    # The zip contains a top‑level folder like "owner-repo-<hash>"
    # Extract everything into a folder named after the repo
    extract_path = f"./{repo}"
    os.makedirs(extract_path, exist_ok=True)
    z.extractall(path=extract_path)

print(f"✅  Repository '{owner}/{repo}' extracted to ./{repo}")



