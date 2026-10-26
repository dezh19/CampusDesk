# CampusDesk

A campus service request manager built as the JavaFX desktop client for the ITE 2200 individual project at the University of Guyana. Students and staff can log IT, facilities, academic, library and housing requests, track them through to resolution, and see live priority and workload information.

## Features

- **Dashboard**: priority breakdown, staff workload, and a switch between priority strategies
- **Requests**: log, assign and comment on requests and move them through their statuses, with a timeline of every change
- **Staff**: add staff members, mark them active or inactive, and see their active request counts
- **Reports**: a snapshot of the queue by priority, category and staff workload, with CSV export and printing
- **Light and dark themes**

Priority is never entered by hand. A swappable scoring strategy computes it from category, age and urgency keywords, and you can recalculate it with an alternative SLA-based strategy from the Dashboard.

## Design

| Package | Role |
| --- | --- |
| `model` | `ServiceRequest`, `StaffMember`, `HistoryEntry` and the enums for priority, status and category |
| `repository` | Repository interfaces with in-memory implementations |
| `service` | `RequestService` and `StaffService`, including validation |
| `observer` | Observer pattern: history logging and staff-workload tracking react to request changes |
| `strategy` | Strategy pattern: interchangeable priority rules (`SlaPriorityStrategy`, `WeightedPriorityStrategy`) |
| `controller` | FXML page controllers and UI factories (avatars, icons, stat cards, charts) |

Built with Java 25, JavaFX 25.0.1 and Maven.

## Running it

This repository holds the packaged Windows build produced by `jpackage`, with its own bundled Java runtime, so nothing else needs to be installed.

1. Clone or download this repository.
2. Run `CampusDesk.exe`.

## Layout

```
CampusDesk.exe   Windows launcher
app/             application JAR, JavaFX libraries and launcher config
runtime/         bundled Java runtime
```
