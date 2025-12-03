# CMS Beamline Quick‑Start:

This Quick-Start Guide is for users starting Bluesky, Xi‑CAM & SciAnalysis at beamline workstations. In case of any software crash, start a new terminal and type the following command.


## 0) Before You Begin

* **Accounts & access**

  * Ensure your BNL credentials, Duo/MFA, and CMS access are active.
  * Ensure your training is up to date.
  * Ensure you appear on the proposal/SAF experimenter list.

* **Data locations (examples—use your own)**

  * Proposal root:

    ```
    /nsls2/data/cms/proposals/<cycle>/pass-<######>/
    ```
  * Experiment folder:

    ```
    /nsls2/data/cms/proposals/<cycle>/pass-<######>/experiments/<ExpName>/
    ```
  * User configuration or plan file (example path):

    ```
    /nsls2/data/cms/shared/config/bluesky/profile_collection/users/<cycle>/<user_name>/user_TSAXSWAXS.py
    ```
  * Typical SWAXS layout:

    ```
    <ExpName>/saxs/{raw,analysis}/
    ```

---

## 1) Start Bluesky (interactive beamline session)

1. **Sync your proposal to the beamline environment**

   ```bash
   sync-experiment -b cms -p <proposal_id>
   ```

   Follow the prompts to sign in (Duo/MFA).

2. **Launch Bluesky UI shell**

   ```bash
   bsui
   ```

3. **(Optional) Load a user configuration or plan file**
   Replace the path below with the current cycle and file you need.

   ```python
   %run -i /nsls2/data/cms/shared/config/bluesky/profile_collection/users/<cycle>/<user_name>/user_TSAXSWAXS.py
   ```

---

## 2) Launch Xi‑CAM (graphical data browsing)

1. **Switch to your user account**

   ```bash
   su - <username>
   ```

2. **Activate the Xi‑CAM conda environment**

   ```bash
   conda activate xi-cam-py3-2025
   ```

3. **Start Xi‑CAM**

   ```bash
   xicam
   ```

4. **Open your raw data folder**
   Navigate to something like:

   ```
   /nsls2/data/cms/proposals/<cycle>/pass-<######>/experiments/<ExpName>/saxs/raw
   ```

---

## 3) Run SciAnalysis (batch analysis)

1. **Switch to your user account (if needed)**

   ```bash
   su - <username>
   ```

2. **Prepare your analysis script**
   Copy your `runXS.py` into the experiment’s `analysis` folder:

   ```bash
   cp /path/to/your/runXS.py \
      /nsls2/data/cms/proposals/<cycle>/pass-<######>/experiments/<ExpName>/saxs/analysis/
   ```

3. **Open the analysis folder in VS Code for editing**

   ```bash
   code /nsls2/data/cms/proposals/<cycle>/pass-<######>/experiments/<ExpName>/saxs/analysis/
   # edit runXS.py as needed
   ```

4. **Activate the analysis environment**

   ```bash
   conda activate <analysis-env>
   ```

5. **Run the analysis**

   ```bash
   cd /nsls2/data/cms/proposals/<cycle>/pass-<######>/experiments/<ExpName>/saxs/analysis/
   python runXS.py
   ```

> Outputs typically appear under the same `analysis/` folder (e.g., plots, `.dat` files, logs). Adjust paths inside `runXS.py` if you use WAXS or alternate layouts.

---

## 4) Common Layout Reference (examples)

```
/nsls2/data/cms/proposals/
  └── <cycle>/
      └── pass-<######>/
          └── experiments/
              └── <ExpName>/
                  ├── saxs/
                  │   ├── raw/
                  │   └── analysis/
                  └── waxs/
                      ├── raw/
                      └── analysis/
```

---

## 5) Quick Troubleshooting

* **Permission denied** → Confirm you’re on the approved experimenter list for the proposal/pass; re-login after updates.
* **Xi‑CAM won’t start** → Ensure the correct conda env is active.
* **Analysis can’t find files** → Double-check `<cycle>`, `<######>`, `<ExpName>` and that your `runXS.py` points to `raw/` and writes to `analysis/`.

---


## Appendix: Placeholder Keys

* `<cycle>`: NSLS‑II run cycle (e.g., `2025-2`).
* `<######>`: Your pass number.
* `<ExpName>`: Your experiment name/folder under `experiments/`.
* `<proposal_id>`: Your proposal identifier used with `sync-experiment`.
* `<username>`: Your BNL/CMS account username.
* `<analysis-env>`: The conda environment for your analysis workflow.

