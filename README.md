






-
-
- 
- 🤔 
- 
- ...
- : ...
 ..




 

--------------------------

----------------------------
r = NE           .. "as"
repo  = "REPO"           # e.g. "linux"
ranch = "main"          # or the default branch you need
# If the repo  private, set a token here:
# token = "ghp_XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"
# headers = {"thorization": f"oken {token}"}
s  iepo needs  auth

# ----------------------------
# 2️⃣  FETCH ARCHIVE (quickest way to get the whole repo)
# ----------------------------
ziprl = f"https://api.github.com/repos/{owner}/{repo}/zipball/{branch}"
esp = requests.get(zip_url, headers=headers)
resp.raise_for_statu()

# Unpack the zip into a local folder
zip_bytes = io.BytesIO(resp.content)
with zipfile.ZipFile(zip_bytes) as z:
    # The zip contains a top‑level folder like "owner-repo-<hash>"
    # Extract everything into a folder named after the repo
    extract_path = f"./{repo}"
    os.makedirs(extract_path, exist_ok=True)
    z.extractall(path=extract_path)

print(f"✅  Repository '{owner}/{repo}' extracted to ./{repo}")



