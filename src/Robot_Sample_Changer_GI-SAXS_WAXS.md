# Robot Sample Changer — High-Throughput Static GI-SAXS/WAXS


This guide explains how to use the CMS robot sample changer for high-throughput static GI-SAXS/WAXS experiments. It is written for beamline users and staff. Basic familiarity with the Python/Bluesky IPython console is helpful.

## Key files

- `startup/user_collection/user_static.py`: User-facing configuration file where you define samples, holders, default exposure times, incident angles, and the queue. Beamline staff should handle beamline-specific settings (calibration, detector geometry, helper functions).

## Overview

- The holder class used at CMS is typically `GIBar_Custom`. Each holder contains multiple sample slots.
- The robot moves holders from the garage to the sample stage, one holder at a time, for measurement and then returns the holder to the garage.
- For each sample the automated sequence will: put the beamline in alignment mode, align the sample, switch to measurement mode, move detectors/motors to SAXS/WAXS positions, and perform measurements at the configured incident angles and exposure times.

## Instructions

### Before your beamtime

- Work with beamline staff to confirm your experimental parameters: sample details, desired q-range and incident angles, exposure times, and number of samples/expected beamtime.
- Users are welcome to ask for sample bars to be shipped to them so they can load samples prior to their arrival. Alternatively, 3D-printed sample bar models are available.
- Users are encouraged to input their sample information into the Google spreadsheet prior to arrival.
- If possible, test a single sample early in the shift to validate alignment and detector settings.

### Day-of checklist

1) Edit `user_static.py` (staff or staff-assisted user)

 - Open `startup/user_collection/user_static.py` in an editor (for example, VS Code).
  - Typical edits:
    - `RE.md['experiment_alias_directory']` — set your experiment folder where data should be saved (staff or user) .
    - `RE.md['userpy_alias_directory']`  (staff) .
    - Detector calibration: `cms.SAXS.setCalibration([...])` (staff).
    - Helper functions: confirm `saxs_on()`, `swaxs_on()`, `waxs_on()` positions (staff) .
    - Per-sample defaults: inside the `Sample` class set `incident_angles_default`, `SAXS_time`, `WAXS_time`, and `naming_scheme` as needed.
    - Add your samples to holders (near bottom of the file) using the existing holder commands, for example:

      `hol1.addSampleSlotPosition(Sample('MySample1', **md), 1, 10, 'WAXS', incident_angles=[0.08,0.12], thickness=0.7)`

    - If you use a Google Sheet to generate lines, copy-paste the formatted lines into the holder block. Verify indentation and syntax.
    - Add/remove holders from the queue by (un)commenting `que.addHolderIntoQueue(...)` lines. Check the holder-to-garage coordinates.
    - Save the file.


2) Reload scripts in IPython

    ```python
    %run -i startup/user_collection/user_static.py
    ```

3) Console prompts and expected replies

- The `%run -i` reload may print questions from helper code. Typical prompts and answers:
  - "Is there a holder on the stage? (y/n)" → answer `y` if the holder is physically on the stage, otherwise `n`.
  - "Is there a holder on the robot? (y/n)" → answer `y` if the holder is physically on the robot, otherwise `n`. This typically applies to some condistion that robot control is crashed or jammed.
  - "If yes, what is the holder?" → answer holder name like `hol1` 
  - If you are unsure about, stop and ask beamline staff.

4) Vacuum and detector pre-checks

- Pump the sample chamber (only when instructed/authorized):

    ```python
    cms.pumpSample()
    ```

- Start or ensure WAXS detector is running:

    ```python
    startWAXS()
    ```

- Check the control screen (CSS) for:
  - Gate valve status
  - Photon shutter state
  - Detector readiness

5) Quick motor/position checks

- Use these to confirm holders and sample positions:

    ```python
    hol1.listSamples()        # List samples and slots on hol1
    hol1.gotoOrigin()         # Move holder to its saved origin
    sam = hol1.gotoSample(1)   # Obtain sample 1
    sam.gotoOrigin()          # Move sample motors to the saved origin
    ````

- For a quick detector frame (alignment check) use a short exposure or a snapshot plan. Example:

    ```python
    # Example: quick 0.5 s frame using the default detector
    sam.snap(0.5)
    ```

6) Run the queued holders

    ```python
    que.runHolders()
    ```

7) Monitor console output for errors such as document saving failures, read timeouts, or suspender triggers.

- Avoid stopping the queue while the robot is moving a holder; wait for safe points or ask staff.

8) Emergency stop and safe abort

- If you must stop a running plan, you can interupt the script by hitting Ctrl+C, then use `RE.abort()`. After aborting, ensure the beam is off:

    ```python
    RE.abort()
    beam.off()
    ```

8) End of experiment: venting

    ```python
    cms.ventSample()
    ```

### Common methods and examples

- Holder/sample listing and movement:

    ```python
    hol1.listSamples()
    hol1.gotoOrigin()
    sam = hol1.gotoSample(1)
    sam.gotoOrigin()
    ```

- Alignment and measurement (example sequence for one sample):

    ```python
    sam.align()                 # run alignment routine 
    sam.measureIncidentAngle(incident_angles, exposure_time=10, tiling='ygaps')
    ```

### Manual robot operations (staff-only or supervised)

- Pick and return holder (examples — confirm with staff):

    ```python
    # By holder object
    robot.pickHolder(hol1)
    robot.returnHolder(hol1)

    # Or by garage coordinates (row, column)
    robot.pickHolder([1,1])
    robot.returnHolder([1,1])
    ```

- Run one holder's automated sequence:

    ```python
    hol1.doSamples()
    ```

### If you need help

- If you encounter unexpected behavior (robot jam, communication errors, detector errors), stop and call beamline staff.
