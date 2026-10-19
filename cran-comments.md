# CRAN submission comments — SWORD 0.1.0

## R CMD check results

**0 errors | 0 warnings | 1 note (CRAN servers)**

On CRAN check machines only the standard "New submission" NOTE is expected.

### NOTE 1 — expected for a first submission (all platforms)

```
* checking CRAN incoming feasibility ... NOTE
  New submission

  Possibly misspelled words in DESCRIPTION:
    Cao, Carta, Frigau
```
The flagged words are author surnames (Carta and Frigau are the package
authors; Cao is a co-author of the cited Yang, Song and Cao (2005) paper).

### Local-only NOTEs (do NOT appear on CRAN servers)

```
* checking top-level files ... NOTE
  Files 'README.md' or 'NEWS.md' cannot be checked without 'pandoc' being installed.
```
Pandoc is not installed in the local check environment. Confirmed absent on R-hub.

```
* checking for future file timestamps ... NOTE
  unable to verify current time
```
No NTP access in the local check environment. Confirmed absent on R-hub and
win-builder.

```
* checking compiled code ... NOTE
  (objdump.exe could not be executed)
```
Windows Smart App Control blocks the unsigned Rtools binaries on the local
machine. Confirmed absent on win-builder.

---

## Test environments

| Platform | R version | Errors | Warnings | Notes |
|---|---|---|---|---|
| Windows (win-builder) | R 4.6.1 ucrt | 0 | 0 | 1 (New submission; surnames flagged by the spell check) |
| macOS (GitHub Actions, macos-latest) | release | 0 | 0 | 0 |
| Windows (GitHub Actions, windows-latest) | release | 0 | 0 | 0 |
| Ubuntu (GitHub Actions) | devel | 0 | 0 | 0 |
| Ubuntu (GitHub Actions) | release | 0 | 0 | 0 |
| Ubuntu (GitHub Actions) | oldrel-1 | 0 | 0 | 0 |
| Windows 11 (local, `--as-cran`) | R 4.5.3 ucrt | 0 | 0 | 3 (local-only, see above) |

The GitHub Actions jobs use the standard `r-lib/actions` check
(`R-CMD-check.yaml`); the `--as-cran` check was run locally and on win-builder.

## Reverse dependencies

None. This is a new package with no existing reverse dependencies.
