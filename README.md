# FF - FlagFinder

**FF - FlagFinder** is a CLI tool to extract flags from authenticated pages using cookies, headers, or session files.

---

## 🚀 Features

- Supports authenticated requests using:
  - .json Session file (from [LAS-LoginAuthSessionizer](https://github.com/Ph4nt01/LAS-LoginAuthSessionizer)
  - Custom cookies and headers
- Flexible flag detection:
  - Exact flag match
  - Regex pattern match
  - Auto-detect common CTF flag formats(if not using -f FLAG option)
- Saves response HTML to (`debug.html`)
- Saves detected flag(s) to (`--output <YourFile>`)

---

## 📦 Installation

### Using `pipx` (recommended)

```bash
pipx install ff-flagfinder
````

### Using pip:

```bash
pip install ff-flagfinder
```

---

## 🧪 Usage Examples

### 🔍 Exact Flag Match

```bash
ff -fu https://target.com/flag -f CTF{example_flag}
```

### 🧠 Regex Pattern Match

```bash
ff -fu https://target.com/flag -f "picoCTF{.*?}" -r
```

### 📦 Using Session File

```bash
ff -fu https://target.com/flag -f FLAG{123} -s session.json
```

### 🍪 With Cookies / Headers

```bash
ff -fu https://target.com/flag -f HTB{.*} \
   -ck sessionid=abc123 \
   -hd "User-Agent: Mozilla/5.0" \
   -r
```

---

## 🛠 CLI Options

|Option|Description|
|---|---|
|`-fu`, `--flagurl`|URL to the page where the flag is located (required)|
|`-f`, `--flag`|Flag or regex pattern to match|
|`-r`, `--regex`|Treat `-f` as a regex pattern|
|`-s`, `--session`|.json session file|
|`-ck`, `--cookie`|Custom cookies (e.g., `sessionid=abc123`)|
|`-hd`, `--header`|Custom headers (e.g., `"User-Agent: Firefox"`)|
|`-o`, `--output`|Output file name (default: `flag.txt`)|

---

## 🔍 Auto-Detected Flag Formats

If no `--flag` is provided, it searches for:

- `CTF{.*?}`
    
- `FLAG{.*?}`
    
- `HTB{.*?}`
    
- `picoCTF{.*?}`
    
- `AKASEC{.*?}`
    

---

## 📁 Output Example

```
FF-FlagFinder



[+] SUCCESS: Flag found!


Flag saved to: [flag.txt]

Response content saved to: [debug.html]
```

---

## 📂 Project Structure

```
FF-FlagFinder/
├── ff/
│   ├── __init__.py
│   └── cli.py
├── README.md
├── LICENSE
├── setup.py
├── pyproject.toml
├── requirements.txt
├── .gitignore
```

---

## 📜 Author

[Ph4nt01](https://github.com/Ph4nt01)
