# Revit BIM Automation Tools
A collection of Dynamo and Python scripts designed to eliminate repetitive manual documentation, enforce BIM QA/QC standards, and accelerate architectural delivery.

---

## 01. Batch Room Standardizer & BIM QA/QC Excel Auditor
* **Problem:** Manually standardizing 298 room elements takes 30+ minutes per submission, while unplaced "ghost rooms" silently bloat the Revit database and corrupt BoQ area schedules.
* **Solution:** An automated Dynamo QA/QC pipeline that enforces uppercase naming standards across all Room elements, filters active rooms from unplaced/redundant rooms (`Area == ""`), and exports a two-tab Excel audit report (`Room_QA` and `Ghost_Rooms_To_Purge`).
* **Impact:** Reduced room standardization and model health auditing from ~45 minutes to under 3 seconds; isolated 277 redundant ghost room elements (92.9% room database bloat) alongside 21 active rooms.

### Dynamo Graph (V2 with Excel QA Pipeline)
![Batch Room Name Standardizer Graph](01_Batch_Room_Name_Standardizer_Graph.png)


---

## 02. Automated Excel-to-Revit Sheet Generator
* **Problem:** Manually creating 20–50 drawing sheets in Revit and typing individual Sheet Numbers, Sheet Names, and selecting Titleblock families takes 45–60 minutes per project setup and introduces numbering typos.
* **Solution:** An OpenXML Excel-to-Revit ingestion pipeline (`02_Excel_To_Revit_Sheet_Generator.dyn`) that reads an external `Drawing_Register.xlsx` schedule, strips header metadata via `List.RestOfItems`, transposes column arrays, and batch-generates populated Revit sheets with assigned Titleblock families in a single execution.
* **Impact:** Reduced drawing register sheet setup from ~45 minutes to under 2 seconds (99% time reduction) with 100% alignment to external project transmittal schedules.

### Dynamo Graph (Excel Ingestion & Sheet Generation Pipeline)
![Excel to Revit Sheet Generator Graph](02_Excel_To_Revit_Sheet_Generator_Graph.png)
