💻 How to use **VS Code (via code-server)** inside **Termux** on your Android or HarmonyOS device — so you can actually **code like on a computer** right from your phone or tablet.

---

## 🧠 What You’ll Be Doing

You’ll install:

* **Termux** → gives you a Linux terminal on your device
* **code-server** → runs VS Code in a browser tab (locally or remotely)

When done, you’ll open VS Code in your browser at `http://localhost:8080` and start coding.

---

## ⚙️ Step-by-Step Setup

### 1️⃣ Install Termux

1. Download it safely from **F-Droid** →
   👉 [https://f-droid.org/en/packages/com.termux/](https://f-droid.org/en/packages/com.termux/)
2. Install and open Termux.
3. Update it:

   ```bash
   pkg update && pkg upgrade
   ```

---

### 2️⃣ Install Basic Tools

```bash
pkg install curl wget git nodejs -y
```

---

### 3️⃣ Install code-server

Run:

```bash
npm install -g code-server
```

Verify:

```bash
code-server --version
```

---

### 4️⃣ Start code-server

In Termux:

```bash
code-server
```

You’ll see output like:

```
info  Using user-data-dir ~/.local/share/code-server
info  Server listening on http://127.0.0.1:8080
info  Password: 1234567890abcdef
```

👉 Copy that **password**.

---

### 5️⃣ Open VS Code in Your Browser

1. Open your phone/tablet’s browser (e.g. Chrome).
2. Visit:

   ```
   http://127.0.0.1:8080
   ```
3. Paste the password from Termux.
4. 🎉 You’re now in a full **VS Code environment** on your HarmonyOS device!

---

### 6️⃣ (Optional) Make It Accessible on Your Network

If you want to access it from your laptop or another device on Wi-Fi:

```bash
code-server --bind-addr 0.0.0.0:8080
```

Then open on your computer:

```
http://<your-phone-ip>:8080
```

---

### 7️⃣ Save and Reopen Projects

Use these commands to manage your projects:

```bash
cd ~/projects
mkdir myproject && cd myproject
code-server .
```

---

### 8️⃣ Stop the Server

Press **Ctrl + C** in Termux to stop it.

---

## 🧩 Optional: Auto-start Script

If you want code-server to start automatically:

```bash
echo 'code-server --bind-addr 0.0.0.0:8080' > ~/.startcode
chmod +x ~/.startcode
```

Then run:

```bash
bash ~/.startcode
```

---

## ✅ Summary

| Task                | Command                      |
| ------------------- | ---------------------------- |
| Update Termux       | `pkg update && pkg upgrade`  |
| Install Node.js     | `pkg install nodejs`         |
| Install code-server | `npm install -g code-server` |
| Run VS Code         | `code-server`                |
| Access in browser   | `http://127.0.0.1:8080`      |
| Stop server         | `Ctrl + C`                   |

---
