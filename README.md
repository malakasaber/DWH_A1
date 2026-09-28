# DWH_A1

A SQL Server Integration Services (SSIS) data warehouse project designed to build and populate a data warehouse named `DWH_A1` using staged ETL workflows.

This repository contains the project definition, SSIS package files, and the database metadata needed to extract, transform, and load data into a SQL Server-based warehouse environment.

## Project Overview

`DWH_A1` is a data engineering project focused on:

- ingesting source data from file-based inputs
- loading data into a SQL Server database
- organizing ETL processing into task-based SSIS packages
- preparing the data for warehouse/reporting use cases

The project is structured as an SSIS solution and includes multiple packages (`Task1.dtsx`, `Task2.dtsx`, `Task3.dtsx`, `Task4.dtsx`, `FinalTask4.dtsx`) that collectively implement the ETL pipeline.

## Repository Structure

```text
DWH_A1/
├── .gitattributes
├── .gitignore
├── DWH_A1.database
├── DWH_A1.dtproj
├── DWH_A1.sln
├── FinalTask4.dtsx
├── Project.params
├── README.md
├── Task1.dtsx
├── Task2.dtsx
├── Task3.dtsx
├── Task4.dtsx
├── task1Draft.dtsx
└── .git/
```

## ETL Workflow

The repository is organized around an SSIS ETL workflow:

- `Task1.dtsx` – initial extraction and staging task
- `Task2.dtsx` – additional ETL/data movement task
- `Task3.dtsx` – transformation / validation logic
- `Task4.dtsx` – main loading and final warehouse processing
- `FinalTask4.dtsx` – final task package / end-to-end orchestration

The project also includes `DWH_A1.database`, which is part of the SSIS project metadata used to manage the database environment for the warehouse.

## Data Engineering Stack

- SQL Server Integration Services (SSIS)
- SQL Server / SQL Server Data Warehouse database
- Flat-file data sources (CSV-style input observed in project connection managers)
- Visual Studio SSIS project model (`.dtproj`, `.sln`)

## Prerequisites

Before opening or running the project, ensure you have:

- SQL Server installed and accessible
- SQL Server Integration Services (SSIS) support available
- SQL Server Data Tools (SSDT) or Visual Studio with SSIS tooling
- A configured SQL Server database named `DWH_A1`
- Access to the source files used by the ETL packages

## Setup

1. Clone the repository.
2. Open `DWH_A1.sln` in Visual Studio / SSDT.
3. Confirm the SSIS project connections reference the correct SQL Server instance and source files.
4. Update database and file paths if they differ from the local environment.
5. Build the project and run the package(s) in the intended order.

## Recommended Execution Order

For a successful ETL run, execute the tasks in this general sequence:

```text
Task1 -> Task2 -> Task3 -> Task4 -> FinalTask4
```

This ordering supports staged processing and helps keep the warehouse load manageable and traceable.

## Notes

- The project is designed for local SQL Server and SSIS-based ETL development.
- Connection strings and file locations in the project may need to be adjusted to match your environment.
- The repository currently contains the project files but does not appear to include a full operational documentation set beyond the SSIS package structure.

## License

This project does not currently declare a license file in the repository. If you plan to share or reuse it publicly, consider adding an explicit license such as MIT or Apache 2.0.

## Summary

`DWH_A1` is a practical SSIS-driven data warehouse project that demonstrates ETL workflows for loading data into a SQL Server-based warehouse. It is structured as a task-based ETL solution and is suitable for learning, extending, and adapting to a real warehouse ingestion scenario.
