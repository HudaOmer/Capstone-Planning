# 🧠 How to Run VS Code (code-server) on a Tablet (Android / HarmonyOS)

Running **code-server** lets you use **VS Code in your browser** — powered locally on your tablet through Termux or a Linux environment.

---

## 🔹 Step 1 — Set Up a Linux Environment

### ✅ Option A: Termux (Recommended)

1. Download **Termux** from **F-Droid**:
   👉 [https://f-droid.org/en/packages/com.termux/](https://f-droid.org/en/packages/com.termux/)
   (F-Droid has the latest version — avoid the outdated Play Store version.)
2. Open Termux.
3. Update and upgrade your packages:

   ```bash
   pkg update && pkg upgrade
   ```

---

### ✅ Option B: UserLAnd (for a full Ubuntu environment)

1. Install **UserLAnd** from the **Google Play Store**.
2. Open UserLAnd → choose **Ubuntu** as your distro.
3. Set a username and password (it will install Ubuntu in a virtual environment).

---

## 🔹 Step 2 — Install code-server

### 🧩 Using Termux

Run these commands:

```bash
pkg update && pkg upgrade
pkg install tur-repo
pkg install code-server
```

Then start it:

```bash
code-server
```

---

### 🧩 Using UserLAnd (Ubuntu)

In the Ubuntu terminal:

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install nodejs npm curl -y
```

Install **nvm** (Node Version Manager):

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
```

Exit and reopen your terminal, then install Node.js 18:

```bash
nvm install 18
nvm use 18
```

Now install code-server globally:

```bash
npm install --global code-server
```

Run it:

```bash
code-server
```

---

## 🔹 Step 3 — Access VS Code in Your Browser

After you run `code-server`, you’ll see output like:

```
info  Server listening on http://127.0.0.1:8080
info  Password: 1234567890abcdef
```

1. Open your browser (Chrome or Huawei Browser).
2. Go to:

   ```
   http://localhost:8080
   ```
3. Enter the password shown in your terminal.

🎉 You’re now using **VS Code directly on your tablet**!

---

## 🔹 Step 4 — (Optional) Make it Accessible Over Your Network

If you want to use it from another device (like your laptop):

```bash
code-server --bind-addr 0.0.0.0:8080
```

Then from your laptop browser:

```
http://<your-tablet-IP>:8080
```

---

## 🔹 Step 5 — (Optional) For iPad Users

If you’re on iPad or want a native-like experience:

1. Open `code-server` in Safari.
2. Tap the **Share** icon → **Add to Home Screen**.
3. It’ll install as a **Progressive Web App (PWA)** for easy access.

---

## ⚙️ Notes & Tips

* Your configuration file is usually at:

  ```
  ~/.config/code-server/config.yaml
  ```

  You can edit the password or port there.
* Use `Ctrl + C` to stop the server.
* You can install developer tools like:

  ```bash
  pkg install git python
  ```

  inside Termux (or `apt install` inside Ubuntu).

---

## ✅ Summary

| Environment       | Commands                                          | Access URL              |
| ----------------- | ------------------------------------------------- | ----------------------- |
| Termux            | `pkg install tur-repo && pkg install code-server` | `http://localhost:8080` |
| UserLAnd (Ubuntu) | `npm install -g code-server`                      | `http://localhost:8080` |

---

## 💻 Resources
- [Medium Guide: Setting VS Code in Tablet/Phone](https://medium.com/@therobinhood/setting-vscode-in-tablet-phone-623000473bb4)
