# Revit BIM Automation Tools
A collection of Dynamo and Python scripts designed to eliminate repetitive manual documentation, enforce BIM QA/QC standards, and accelerate architectural delivery.

---

## 01. Batch Room Standardizer & BIM QA/QC Excel Auditor
* **Problem:** Manually standardizing 200+ room tags takes 30+ minutes per submission, while unplaced "ghost rooms" silently bloat the Revit database and corrupt BoQ area schedules.
* **Solution:** An automated Dynamo QA/QC pipeline that enforces uppercase naming standards across all Room elements, filters active rooms from unplaced/redundant rooms (`Area == ""`), and exports a two-tab Excel audit report (`Room_QA` and `Ghost_Rooms_To_Purge`).
* **Impact:** Reduced room standardization and model health auditing from ~45 minutes to under 3 seconds; isolated 185+ redundant room elements in initial testing.

### Dynamo Graph (V2 with Excel QA Pipeline)
![Batch Room Name Standardizer Graph](01_Batch_Room_Name_Standardizer_Graph.png)
