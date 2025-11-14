# runXS.py Starter Guide

Here’s a **step-by-step guide** to running and customizing the runXS.py script from SciAnalysis on your own Windows machine:

---

### **✅ 1. Set the SciAnalysis Path**

At the top of the script, you’ll see:

```
SciAnalysis_PATH='/home/kyager/current/code/SciAnalysis/main/'
SciAnalysis_PATH in sys.path or sys.path.append(SciAnalysis_PATH)
```

🛠️ **Change this to your actual SciAnalysis folder path.** For example, if you cloned the repo to your Desktop:

```
SciAnalysis_PATH = 'C:\\Users\\YourName\\Desktop\\SciAnalysis\\SciAnalysis'
```

Make sure to:

- Use **double backslashes** \\ or a raw string r'C:\path'
- Point to the **SciAnalysis subfolder containing XSAnalysis/ and tools.py**

---

### **📁2. Set the Mask Path**

The mask is often used for excluding detector artifacts or bad pixels.

in CaliWS.yaml, Look for lines like:

```
mask_dir: "/nsls2/data/cms/legacy/xf11bm/software/SciAnalysis//SciAnalysis/XSAnalysis/masks/"
# mask_file: "Dectris/Pilatus800k_gaps-mask.png"
mask_file: "Dectris/Pilatus800k_vertical_gaps-mask.png"
custom_mask: "./Pilatus800_current-mask.png"
```

🛠️ Un-comment and change this to your actual mask file path (Example):

```
mask_dir = 'C:\\Users\\YourName\\Your_SciAnalysis_Path\\mask\\'
```

If you don’t have a mask, you can either:

- Generate one from a white and black image.
- Comment it out and proceed (some protocols will still work without a mask).

---

### **🧪3. Customize Input and Output Paths**

Later in the script (typically inside a loop or batch block), define:

```
input_dir = '/path/to/data/'
output_dir = '/path/to/output/'
```

🛠️ Replace these with actual folder paths:

```
input_dir = 'C:\\Users\\YourName\\Desktop\\data\\'
output_dir = 'C:\\Users\\YourName\\Desktop\\results\\'
```

Ensure:

- Data files (e.g., .tif, .h5, etc.) are present in input_dir
- output_dir exists or will be created

---

### **🧬4. Customize or Add Protocols**

SciAnalysis lets you define **custom protocols** by subclassing existing ones:

Example from the script:

```
protocols = [
    Protocols.sector_average(name='vertical', angle=0, dangle=20, ylog=True, plot_range=[0, 3.5, None, None],  gridlines=True, save_results = [ 'txt', 'plots' ]) ,
    Protocols.sector_average(name='horizontal', angle=90, dangle=20, ylog=True, plot_range=[0, 3.5, None, None],  gridlines=True, save_results = [ 'txt', 'plots' ]) ,
    Protocols.linecut_angle(q0=2.10, dq=0.05*2, name='linecut_angle_peak3',show_region='save') ,

    ]
```

You can:

- Modify protocols to change parameters, saving behavior, or others

---

### **⚙️5. Batch Processing Configuration**

Locate the file name selector like:

```python
#pattern = '*flaton*'
#pattern = 'Ag*'
pattern = '*'
#pattern = '*71857*'
```

The pattern variable determines **which files in your input_dir are processed**:

- '*' — Process **all files**.
- 'Ag*' — Process files **starting with “Ag”**.
- '*flaton*' — Process files **containing “flaton”** anywhere in the filename.
- '*71857*' — Process files with **“71857” in the name**.

✅ You can **uncomment** and **customize** any one of these lines to suit your data selection.

Locate batch processor like: 

```
# Run
########################################
print('Processing {} infiles...'.format(len(infiles)))
process.run(infiles, protocols, output_dir=output_dir, force=True)
```

- force=True **forces re-processing** of all input files:
    - Even if **results already exist** (e.g., .xml, .png, .dat files), they will be **overwritten**.
    - Useful when you’ve changed protocols, masks, or input parameters and want to regenerate outputs.
- If you want to **skip already-processed files**, change to: force = False

---

### **🚀**

### **6. Run the Script**

Open **Anaconda Prompt** or **Command Prompt**, navigate to the script folder:

```
cd C:\Users\YourName\Desktop\SciAnalysis\examples
python runXS.py
```

---