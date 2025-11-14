# Python Starter Guide

---

## **🧰 PART 1: Install Required Tools**

### **1.**

### **Install Anaconda (Python with Conda)**

1. Go to: [https://www.anaconda.com/download/](https://www.anaconda.com/download/)
2. Download the **Windows 64-bit** version.
3. Run the installer:
    - Choose **“Just Me”**
    - **(Optional)** Check the box: *Add Anaconda to my PATH*
    - Finish the installation.

---

### **2.**

### **Install Visual Studio Code (VS Code)**

1. Go to: [https://code.visualstudio.com/](https://code.visualstudio.com/)
2. Download and install using the defaults.
3. Check **“Add to PATH”** and **“Register Code as editor”** during install.

---

## **📦 PART 2: Download SciAnalysis**

### **3.**

### **Download ZIP from GitHub**

1. Visit: [https://github.com/CFN-SoftBio/SciAnalysis](https://github.com/CFN-SoftBio/SciAnalysis)
2. Click the green **“Code”** button → Choose **“Download ZIP”**.
3. Save the file to your **Desktop**.
4. Right-click the ZIP file → **Extract All**.
5. Rename the extracted folder to just SciAnalysis.

---

## **🧭 PART 3: Setup Environment Using Command Prompt**

### **4.**

### **Open Command Prompt**

- Press Windows + R, type cmd, press Enter.

### **5.**

### **Navigate to Any Folder (example)**

```
cd C:\Users\YourUsername\Desktop\SciAnalysis
```

To check, type:

```
dir
```

You should see files like setup.py.

---

### **6.**

### **Create and Activate Conda Environment**

```
conda create -n scianalysis_env python=3.9 -y
```

Then activate it:

```
conda activate scianalysis_env
```

---

### **7.**

### **Install Required Packages (That may take long to figure out)**

Install SciAnalysis dependencies:

```
conda install numpy 
```

Or multiple package at once:

```markdown
conda install scipy matplotlib h5py lxml pillow -y
```

---

## **📝 PART 4: Edit the Script in VS Code**

### **8.**

### **Open VS Code**

1. Launch VS Code.
2. Go to **File → Open Folder** → Select: runWS.py

### **9.**

### **Install Python Extension in VS Code**

1. Click the **Extensions** icon (left bar).
2. Search **“Python”** and click **Install**.

### **10.**

### **Edit the Script**

1. Open: runWS.py
2. You can adjust input/output paths or settings as needed.

---

## **▶️ PART 5: Run the Script**

Back in Command Prompt:

1. Make sure you’re in the right folder:

```
cd C:\Users\YourUsername\YourDataFolder
conda activate scianalysis_env
```

1. Run the WAXS analysis script:

```
python runWS.py
```

---