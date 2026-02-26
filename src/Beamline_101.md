# Beamline 101: User Must Know

Welcome! This guide gives you the essential information you need to use this beamline—whether you're applying for beamtime, planning your experiment, or reporting your results.

> **Contact Early!**
> 
> **We strongly encourage you to contact beamline staff early in your planning process.** Staff can help you design your experiment, estimate time, and avoid common pitfalls. Email rli@bnl.gov or swu4@bnl.gov for advice.

> **Instrument Limitations:**

> - Incompatible materials: Highly radioactive, corrosive, or explosive samples are not permitted.
> - Energy range: 10–17 keV only
> - Some advanced in-situ tools may require prior arrangement or may not be available for all runs.

## Quick Navigation

1. [Beamline Overview](#1-beamline-overview)
2. [Beamline Capabilities](#2-beamline-capabilities)
3. [What the Beamline Can Do](#3-what-the-beamline-can-do)
4. [Sample Setup Options](#4-sample-setup-options)
5. [Collection and Data](#5-collection-and-data)
6. [Getting Help](#6-getting-help)

---

<details open>
<summary>expand/collapse</summary>

## 1. Beamline Overview

### What is this beamline?

This beamline produces a focused X-ray beam for studying materials and their structures. Researchers use it to understand how molecules arrange themselves in polymers, thin films, and nanostructures.

### Location & Contact

- **Location:** Complex Materials Scattering (CMS) Beamline, 11-BM, National Synchrotron Light Source II (NSLS-II)
- **Address:** Building 744 (green LOB), Brookhaven National Laboratory, Upton, NY
- **Beamline Phone:** 631-344-1911
- **Hours:** Check the [NSLS-II schedule](https://scheduler.nsls2.bnl.gov/) for current status

> **Note:** Always check the beamline website for current status and any scheduled maintenance.

</details>

## 2. Beamline Capabilities

### X-ray Energy Range

The beamline can produce X-rays at different energies. Higher energies penetrate deeper into materials.

- **Energy range:** 10 to 17 keV
- **Common energies used:** 13.5 keV (most popular for general SAXS/WAXS), 10 keV (for smaller q-range), 17 keV (for higher penetration and higher q-range)
- **Energy resolution:** ΔE/E = 0.7% (fixed bandwidth)

> **Tip for your proposal:** Specify the energy you need for your experiment. Staff can adjust this for you.

### Beam Size & Shape

The X-ray beam can be focused to different sizes (horizontally × vertically). Choose based on your sample and what you're measuring.

- **Smallest beam:** ~10 μm (for high-resolution local measurements, for example, mapping using x-ray as a probe)
- **Typical beam:**
  - 200 x 200 μm (standard for most SAXS/WAXS experiments)  - 200 x 50 μm (for grazing incidence measurements)
- **Largest beam:** Up to 500 μm (for quick surveys)

### Beam Brightness (Flux)

The beam intensity varies by energy, size, and slit settings. Higher flux means faster data collection, but smaller beams have lower flux.

- **Full beam (no slits):** 1.3 × 10¹² photons/s (at 13.5 keV, 400 mA ring current)
- **Typical slit sizes:** 0.2 × 0.2 mm → 1.2 × 10¹¹ ph/s (normal)
- **Small slits:** 0.05 × 0.05 mm → 8.6 × 10⁹ ph/s (high resolution)
- **Note:** Flux scales with ring current; check current status before planning

> **For your experiment design:** Faster collection is useful for time-sensitive samples or when doing many measurements.

---

## 3. What the Beamline Can Do

### Measurement Techniques

This beamline supports:

- **SAXS (Small-Angle X-ray Scattering):** Measures nanostructures (1–200 nm). Perfect for polymers, nanoparticles, and hierarchical materials.
- **WAXS (Wide-Angle X-ray Scattering):** Reveals atomic-scale crystal structure. Good for studying crystallinity and phase identification.
- **GISAXS (Grazing Incidence SAXS):** Surface-sensitive technique for thin films and interfaces at very shallow angles.
- **GIWAXS (Grazing Incidence WAXS):** Combines surface sensitivity with atomic-scale resolution for thin film crystals.
- **XRR (X-ray Reflectivity):** Measures layer thickness, density, and surface roughness in multilayer thin films.

> **Choose your technique based on:** What question you're answering about your material's structure?

### What Can You Measure?

- **Nanostructure size & spacing:** From ~1.5 nm to 200 nm (q-range: 0.003–4.2 Å⁻¹)
- **Crystal structure & orientation:** Lattice spacing, degree of crystallinity
- **Layer thickness & roughness:** For thin films and multilayers
- **Density variations:** Within nanostructures and interfaces
- **Kinetics:** Real-time measurements as samples change with temperature, time, or processing
- **Spatial mapping:** How structure varies across your sample (with scanning)

## 4. Detectors & How They Capture Data

### Detectors Available

Two detectors are available, each suited for different purposes:

| Detector | Pixels | Pixel Size | Notes |
|----------|---------|----------|---------| 
| Pilatus 800K | 1043 × 981 | 172 μm | standard choice for WAXS, with bottom-left module removed for simultaneous SAXS/WAXS |
| Pilatus 800k2 | 1043 × 981 | 172 μm | Also called "MAXS" for open-area experiments, with bottom-right module removed for simultaneous SAXS/MAXS |
| Pilatus 2M | 1475 × 1679 | 172 μm | standard choice for SAXS, with high-resolution capability |

Both detectors are 2D and can be positioned at different distances for various q-ranges.

> **q-range explanation:** The range of spatial scales your measurement covers. Closer positioning shows larger q ranges (smaller structures). Farther position allows you to see finer details in the small q range.

### Detector Distance from Sample

The detector can be repositioned to measure different size ranges:

**For WAXS:**

- **0.26 m:** WAXS detector is usually fixed at 0.26 m for atomic-scale measurements (q > 1 Å⁻¹), but can be adjusted for specific experiments. WAXS detector can widely travel in the x-y plane to capture different scattering angles. Typical q-range for WAXS is 0.5–4.2 Å⁻¹, depending on energy and sample-detector distance.

**For MAXS:**

- **0.22 m:**  MAXS detector is typically positioned at 0.22 m for maximum-q measurements at open-area experiments. MAXS detector can also travel in the x-y plane to capture different scattering angles.

**For SAXS:**

- **~1–3 m:** Usually for smaller structures (1–10 nm) or when you want to have a continuous q-range with WAXS data.
- **~5 m:** Standard setup for most SAXS experiments, covering q-range from 0.002–0.2 Å⁻¹ (depending on energy).

> **Tip:** Specify your q-range needs in your proposal. Staff will set the best geometry for your sample.

---

## 4. Sample Setup Options

### Two Experimental Areas

**Vacuum Chamber**:

- Best for: Static sample measurements, high-throughput sample measurements operated by robotic sample changers, air-sensitive materials, or samples requiring controlled atmosphere
- Vacuum environment ( < 0.5 mbar) reduces background scattering and allows for better signal-to-noise ratio

> **Important:** 1. Changing samples in vacuum requires venting and re-pumping, which takes time. Plan accordingly. 2. There is a Kapton window that separates the sample chamber from the beam path, if you want to keep your sample in air, there might be some scattering from the window, ask beamline staff for background removal tips.

**Open Beam Area**:

- Best for: In situ experiments with large sample-setup.
- More accessible: modular table allows easy in situ setup change: you can bring your own sample environment (e.g., heating stage, tensile cell) and set it up on the table, and push the entire table into the beam path for measurement.

> **Tip:** If you have a large or custom sample environment, discuss with beamline staff in advance to ensure it can fit and be safely used in the open beam area.

**Sample Holders & Stages**:

Standard holders available for:

- Universal sample mounting (typically hold 15 samples, up to 45 samples per bar)
- Capillaries (up to 2 mm diameter, 15 samples per bar)
- Films on substrates (GI-SAXS/WAXS bar, 11 cm length, typically 5–15 samples per bar depending on substrate size, robot can hold up to 12 bars per run)
- High-throughput 96-well plates or 324-well plates. (for transmission SAXS/WAXS)

> **Important:** Arrange unusual sample holders with beamline staff well in advance.

**Temperature & Environment Control**:

| Capability | Range | Notes |
| ----------- | ------- | ------- |
| Heating | Room temp to ~ 250°C | Custom holder can hold upto 15 samples per run |
| Cooling | Room temp to ~-90°C | Uses liquid nitrogen, available upon request |
| Humidity | Dry to humid air | Solvent vapor available upon request |
| Inert gas | Nitrogen, argon | Available upon request |

**Special In-Situ Capabilities** 

Several tools are available to apply conditions during measurement (request in advance):

- **High-precision thermal stages:** Linkam stages for controlled heating and cooling, with precise temperature control. Ideal for studying temperature-dependent structural changes. Can hold 1~3 samples for sequential measurements.
- **Tensile cells:** Linkam-MFS stage to apply stress while measuring structure. Great for studying mechanical properties and deformation. Can hold 1 sample at a time. Heating and cooling capabilities are also available (-20°C to 250°C). Tensile force range: 0.1 N to 200 N. 600N version is also available upon request. Recommended sample length > 15 mm.
- **Shear cells:** For studying flow-induced structure
- **Spin-coating setup:** For in situ film formation studies
- **Solvent annealing:** To study solvent uptake and swelling
- **Custom electochemical cells:** For studying electrochemical processes in situ
- **Photocurable/photothermal equipment:** For UV- or laser-triggered processes
- **Diamond anvil cell:** For high-pressure studies
- **Other custom environments:** Contact beamline staff to discuss your specific needs

> **Important:** Include these requests in your beamtime proposal. Staff will confirm availability and provide setup guides.

## 5. Collection and Data

### How Data is Collected

**Single Exposure**:

- One snapshot of your sample
- File size: ~5-10 MB per image
- Exposure time: typically 1–10 seconds (depends on sample and beam intensity)
- Good for: quick checks, static samples, or when you have many samples to screen

**Time Series**:

- Rapid images of the same spot (useful for watching samples change over time)
- Frame rate: up to 50 frames per second (burst mode), for regular time series, typically 1 frame every 2~3 seconds to minutes.
- Good for: heating studies, crystallization, phase changes

**Spatial Scans**:

- Move sample across the beam, collecting at each position
- Maps out how structure varies across your sample
- Time: minutes to hours depending on step size and grid

### Data Format & Output

Data is saved as:

- **TIFF images** (standard for raw data and stitched images)
- **HDF5 files** (upon request, suitable for large datasets and metadata storage)
- **Metadata:** Each image includes metadata (energy, exposure time, sample name, etc.) for easy tracking and analysis, accessible through TILED services.

### Data Analysis Resources

- **SciAnalysis:** Real-time automated reduction (q-space conversion, averaging, sector integration). GitHub: [CFN-softbio/SciAnalysis](https://github.com/CFN-softbio/SciAnalysis)
- **Xi-CAM:** GUI-based visualization and advanced analysis. Website: [camera.lbl.gov/xi-cam-interface](https://www.camera.lbl.gov/xi-cam-interface)
- **Tutorials:** Available on [CMS wiki](https://gisaxs.com/index.php/CMS)
- **Support:** Beamline staff provide immediate help during your beamtime and answer questions afterward

---

## 6. Getting Help

**Beamline Scientists**:

- **Ruipeng Li** (Lead Scientist): <rli@bnl.gov>, 631-344-5994
- **Siyu Wu** (Beamline Scientist): <swu4@bnl.gov>, 631-344-8004
- **Honghu Zhang** (Beamline Scientist): <hzhang@bnl.gov>, 631-344-5626
- **Esther Tsai** (CFN Partner Scientist): <etsai@bnl.gov>, 631-344-6149
- **Yugang Zhang** (CFN Partner Scientist): <yuzhang@bnl.gov>, 631-344-5674

**Online Resources**:

- [CMS Beamline Wiki](https://gisaxs.com/index.php/CMS) — Technical specifications and tutorials
- [NSLS-II User Guide](https://www.bnl.gov/nsls2/userguide/) — General beamtime procedures
- [Official CMS Homepage](https://www.bnl.gov/nsls2/beamlines/beamline.php?r=CMS) — Science highlights & publications
- [Apply for Beamtime](https://pass.bnl.gov/) — NSLS-II PASS system
- [NSLS-II Training](https://www.bnl.gov/ps/training/) — Safety and beamline-specific training

---

## Key Takeaways for Your Publication

When describing your experiment in a paper or report, include:

- **Energy used:** (e.g., 13.5 keV)
- **Detector type and distance:** (e.g., "Pilatus 2M at 5.0 m")
- **Sample environment:** (vacuum, air, temperature, humidity)
- **Measurement type:** (SAXS / WAXS / GISAXS / GIWAXS, transmission or grazing incidence)
- **Exposure time per frame:** (seconds)
- **Beam size:** (μm)
- **Facility:** "CMS beamline, 11-BM, NSLS-II, Brookhaven National Laboratory"

This information allows other researchers to understand your measurements and verify your results.

---

> **Acknowledgement for Publications:** If you use CMS data, please include this in your acknowledgments:
>
> "This work used the 11-BM CMS beamline of the National Synchrotron Light Source II (NSLS-II), Brookhaven National Laboratory (BNL), a U.S. Department of Energy User Facility operated for the Office of Science by BNL under contract DE-SC0012704."

---

> **Questions?** Don't hesitate to contact the beamline staff at 631-344-1911 or <rli@bnl.gov>. We're here to help you succeed!
