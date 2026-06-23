### How to Access Your Data via Globus

1. Go to **https://www.globus.org** and click **Login**.  
   Select **Brookhaven National Laboratory** as your institution and log in using your BNL credentials.

2. Once logged in, open **Collections** (left menu) and search for **NSLS2**.  
   Select the **NSLS2** collection.

   - If you are first-time user, you might need to go to **File Manager** on the left pannel and search for **NSLS2**
   - There might be extra authentication step.

4. In the NSLS2 collection, click **File Manager**.

5. Change the default path (your home directory) to the CMS beamline data directory:  

```bash
/nsls2/data/cms/proposals/2025-3/pass-xxxxxx/experiments/
```

5. Browse to the folder corresponding to your run or experiment.

6. For the **second endpoint**, choose your local machine or institution’s Globus endpoint.  
If you don’t have one, install **Globus Connect Personal** and then re-try.

7. With both endpoints active, select the files or folders you want to transfer using the checkboxes, then click **Transfer or Sync to…**.
   - If the folder contains too many files. You can ask beamline staff for help. We can zip the folder.
