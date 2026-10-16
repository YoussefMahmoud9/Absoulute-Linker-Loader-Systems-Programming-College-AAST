# Absolute and Linking Loader College AAST

AAST Systems Programming college project: a Python demonstration of SIC absolute loading and SIC/XE linking loading. It reads sample object records and displays a hexadecimal memory grid with `pandasgui`.

## How it works

Run `loader.py` (or `run.bat`) and choose a mode:

| Choice | Input | Function | Purpose |
| --- | --- | --- | --- |
| 1, SIC | `sic.txt` | `absolute()` | Place bytes from dot-separated H/T/E records at their stated addresses. |
| 2, SIC/XE | `sicxe.txt` | `extable()` | Build an external symbol table, place text bytes, and apply modification records. |

The grid has hexadecimal columns `0` to `F`; an `x` marks a position without a loaded byte. The SIC/XE example contains H, D, R, T, M, and E records across three control sections. `main.py` is an older commented-out draft; `loader.py` is the active program.

## Run

From the `loader` folder, install the dependencies and run:

```powershell
python -m pip install -r requirements.txt
python loader.py
```

The display requires a desktop GUI. The SIC/XE implementation hardcodes initial load address `403F` and assumes aspects of the supplied record layout, so it is a teaching sample rather than a general loader. Runtime compatibility with current dependency versions has not been verified here.

## Documentation

- [Project report PDF](docs/Systems_Project_Report.pdf) and [editable Word report](docs/Systems_Project_Report.docx)
- [Architecture scheme](docs/Architecture_Scheme.svg)
- [Assembler and loader flowcharts](docs/Workflow_Flowcharts.svg)
- Related [assembler project](https://github.com/YoussefMahmoud9/2-Pass-assembler-System-Programming-College-AAST)

The included `sic.txt` and `sicxe.txt` are demonstration object files. They are independent of the assembler project's generated `hte.txt`.
