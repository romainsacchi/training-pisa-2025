
# INSTRUCTIONS BEFORE ARRIVAL

Please follow the below instructions before arriving at the course.  
If you encounter any issues, please contact us (Romain), and we will troubleshoot,  
so that you can arrive with everything set up on your computer.

---

## WORK ON SERVERS vs. LOCAL MACHINES

You will set up everything on your **local machine**, instead of us providing a server for the course.

Why? Because you will likely work on your own machine at home too. We want to give you the experience  
of setting up everything in your real-world environment.

> [!IMPORTANT]  
> We recommend at least **8GB of RAM** on your computer,  
> as some of the calculations can be memory-intensive.

---

## WHAT IS ANACONDA AND GIT?

- **Anaconda** is a program that helps manage Python environments and the libraries they contain.
- **Git** is a tool used to download and sync files from the internet (e.g., course material).

---

## STEP 1: INSTALL ANACONDA AND GIT

Download and install:

- Anaconda: https://www.anaconda.com/products/distribution  
- Git: https://git-scm.com/downloads

### For Mac users:

We recommend installing Git using [Homebrew](https://brew.sh):

```bash
brew install git
```

### For Windows users:

Download and run the Git installer from the Git website above (choose the 64-bit version).

---

## STEP 2: CLONE THE COURSE REPOSITORY

You can do this in two ways:

### Option A: GitHub Desktop (recommended for beginners)

1. Download [GitHub Desktop](https://desktop.github.com/download/)
2. Click **"Clone a repository"**
3. Paste this link:  
   `https://github.com/romainsacchi/training-pisa-2025.git`

### Option B: Using the terminal (Command Line Interface)

#### 📍 First, open your terminal:

- **Mac**: Applications > Utilities > Terminal
- **Windows**: Open “Anaconda Prompt” (from Start Menu)

To check where you are:

```bash
pwd
```

To go to your Documents folder:

```bash
cd Documents
```

To go back a folder:

```bash
cd ..
```

To create a new folder:

```bash
mkdir training-brightway-2025
cd training-brightway-2025
```

Now clone the course materials:

```bash
git clone https://github.com/romainsacchi/training-pisa-2025.git
```

---

## STEP 3: SET UP THE PYTHON ENVIRONMENTS

We have prepared environment files to install everything for you.

First, **navigate to the envs folder**:

```bash
cd training-pisa-2025/envs
```

### Create the `bw2` environment

- On **Windows** or Mac **with Intel**:

```bash
conda env create -f bw2_env_win64.yaml
```

- On **Mac with M1/M2/M3/M4** processor:

```bash
conda env create -f bw2_env_osxARM.yaml
```

This installs everything for `brightway2` and `activity-browser`.

### Create the `premise` environment

Still in the `envs` folder:

```bash
conda env create -f premise_env.yaml
```

Check the environments:

```bash
conda env list
```

Activate an environment:

```bash
conda activate bw2
```

Check packages installed:

```bash
conda list
```

---

## STEP 4: IMPORT THE ECOINVENT DATABASE

You will need **ecoinvent credentials** (username and password).  
Ask your group/university or ecoinvent support for access.

We will use **ecoinvent 3.10 cut-off**.

### Steps:

1. Navigate to the envs folder:

```bash
cd training-pisa-2025/envs
```

2. Activate the `bw2` environment:

```bash
conda activate bw2
```

3. Run this command (replace username/password):

```bash
python prepare_project.py "ecoinvent_username" "ecoinvent_password"
```

> [!IMPORTANT]  
> On Mac, use **single quotes** around the credentials:
>
> ```bash
> python prepare_project.py 'your_username' 'your_password'
> ```

If successful, you’ll see:

```bash
List of databases in training-day project: Databases dictionary with 2 object(s):
    biosphere
    ecoinvent-3.10.1-cutoff
```

---

## STEP 5: CODE EDITOR

We recommend:

- [PyCharm Community Edition](https://www.jetbrains.com/de-de/pycharm/download/)
- [Visual Studio Code](https://code.visualstudio.com)

> [!NOTE]  
> Both are **free** (choose the “Community” edition).  
> These editors provide helpful features for coding and debugging.

---

## 💡 COMMON ISSUES

> **❓ Command not found**  
> Anaconda or Git might not be installed or added to your system PATH. Try restarting your terminal.

> **❓ Permission denied**  
> Try running your terminal as Administrator (Windows) or using `sudo` on Mac (if you know the password).

> **❓ Python or conda not recognized**  
> Reboot your system. If the problem persists, reinstall Anaconda.

If anything fails — don't worry, contact [romain.sacchi@psi.ch](mailto:romain.sacchi@psi.ch) and we’ll help.

Good luck, and see you soon!
