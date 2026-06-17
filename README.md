# Protein Painter
Generate PyMOL and ChimeraX coloring scripts with user-defined or premade coloring schemes.



Protein Painter turns protein domain specifications into ready-to-paste coloring scripts for PyMOL and ChimeraX. There's two forms:

- **`Protein_painter.html`** — the no-install version; Double-click to open in your web browser. The only limitation: custom color schemes you save aren't remembered after you close the browser tab (you can save/load them as `.json` files by hand though).
- **`Protein_painter_app.py`** — the app version. Needs Python (below), but adds custom color schemes that can persist after the browser tab is closed. 
If you just want to use the tool and don't care about permanently saved schemes, use the HTML file and ignore the rest of this guide.

---

## For the app version
---

## To check if you already have Python somewhere
Open a terminal:

- **Windows:** press Start, type `cmd`, open "Command Prompt." (Or "Anaconda Prompt" if you use Anaconda — see the note below.)
- **Mac:** open "Terminal" (Applications → Utilities → Terminal).
- **Linux:** open your terminal app.

Type this and press Enter:

```
python --version
```

- If it prints something like `Python 3.11.4`, you have Python — go to Step 2.
- If it says "command not found" or similar, try `python3 --version`.
- If neither works, go to the next step. 

**Anaconda users:** if you have Anaconda or Miniconda, congrats: you already have Python. Just use the "Anaconda Prompt" (Windows) or your conda terminal (Mac/Linux) for all the commands in this guide, and `python` will work.

---

## Step 1 — Install Python (only if you don't have it)

If you plan to have more utilities that require Python/R/RStudio, Anaconda is a useful tool that can manage environments for all 3 (and more.) Learn more here: <https://www.anaconda.com/products/navigator>

If you don't plan on using/developing python programs or using R, then just the bare-bones python will do. Go to <https://www.python.org/downloads/> and download the installer for your system, then run it.

- **Windows:** during installation, **check the box that says "Add Python to PATH"** before clicking Install. This matters — without it the `python`command won't be found. Then close and reopen Command Prompt.
- **Mac / Linux:** run the installer normally, then reopen the terminal. (Many Macs and Linux machines already have Python as `python3`.)

---

## Step 2 — Install Flask

In a python-enabled terminal, type:

```
pip install flask
```

If `pip` isn't found, try `pip3 install flask`. If you use Anaconda, you can also use `conda install flask`.

You only need to do this once- after that, the package stays on your computer. 

**Optional, tidier way:** if you keep `requirements.txt` next to the app, you can instead run `pip install -r requirements.txt`, which installs the same thing.

---

## Step 3 — Download and Run the app

Download the Protein_painter_app.py file from this page and save it somewhere. 

Then navigate the terminal to the folder where you saved `Protein_painter_app.py`. The `cd` ("change directory") command does this. For example, if the file is in your Downloads folder (not a recommended long-term solution):

```
cd Downloads
```

(On Windows that's usually `cd %USERPROFILE%\Downloads`; on Mac/Linux, `cd ~/Downloads`.)

Then start the app:

```
python Protein_painter_app.py
```

(Use `python3` if that's what your system uses.)

You'll see a few lines print, including:

```
Protein Painter running at http://127.0.0.1:5000
```

Your web browser should open to the app automatically. If it doesn't, copy that `http://127.0.0.1:5000` address into your browser yourself.

---

## Using it day to day

- **Keep the terminal window open** while you use the app — that window is the running program. Closing it stops the app. That's normal.
- **To stop the app:** click the terminal and press `Ctrl + C`.
- **To run it again later:** you only repeat Step 3 (navigate to the folder, then `python protein_painter_app.py`). Python and Flask stay installed.

---

## Where your saved schemes live

The first time you use **★ Save as scheme**, the app creates a small file to store your color schemes. You don't set this up — it happens automatically.
It lives here:

- **Windows:** `%APPDATA%\ProteinPainter\schemes.json`
- **Mac:** `~/Library/Application Support/ProteinPainter/schemes.json`
- **Linux:** `~/.config/ProteinPainter/schemes.json`

These schemes stay on *your* computer and are remembered between sessions. They aren't shared between people or machines. To wipe all saved schemes, delete that file.

---

## Troubleshooting

**"python is not recognized" / "command not found" (Windows)**
Python isn't on your PATH. Reinstall Python and check "Add Python to PATH," or use the Anaconda Prompt if you have Anaconda.

**"No module named flask"**
Flask didn't install, or installed for a different Python. Run `pip install flask` again in the same terminal you use to start the app.

**"Address already in use" / port 5000 error**
A previous copy of the app is still running. Close the other terminal window, or restart your computer, then try again.

**The browser didn't open**
Copy `http://127.0.0.1:5000` into your browser's address bar manually.

**Port 5000 is taken by something else (common on some Macs)**
Tell whoever set this up and they can change the port in the script — it's a one-line edit near the bottom of `protein_painter_app.py` (`port = 5000`).

---

## Quick reference

| Task | Command |
|------|---------|
| Check Python | `python --version` |
| Install Flask | `pip install flask` |
| Go to the app's folder | `cd <folder>` |
| Run the app | `python protein_painter_app.py` |
| Stop the app | `Ctrl + C` in the terminal |
