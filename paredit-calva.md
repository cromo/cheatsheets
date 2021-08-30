# Paredit (Calva) Cheatsheet

This is a cheatsheet for [Calva's implementation of Paredit](https://calva.io/paredit/). The purpose of this cheatsheet is the opposite of Calva's - to provide a very compact list of operations to make it easy to find and learn specific ones.

## Conventions

| Symbol | Key |
| ------ | --- |
| `^` | Control |
| `!` | Alt |
| `+` | Shift |
| `⇐` | Home |
| `⇒` | End |
| `␣` | Space |
| `␡` | Delete |
| `␈` | Backspace |
| ✂ | Cut |
| 📋 | Paste |

The "Equivalents" column is sometimes not an exact equivalent due to automatic formatting or smart boundary detection performed by paredit.

Forward and backward refer to increasing and decreasing the index of the cursor in the file respectively, while up and down respectively refer to moving into the parent sexp and child sexp.


## Navigation

| Combo | Equivalents | Description |
| ----- | ----------- | ----------- |
| `^→` | | → sexp |
| `^←` | | ← sexp |
| `^⇒` | `^→` 𝄇 | end sexp |
| `^⇐` | `^←` 𝄇 | start sexp |
| `^↓` | | ↘ sexp |
| `^↑` | | ↖ sexp |
| `^!↓` | `^↑ ^→` | ↗ sexp |
| `^!↑` | `^← ^↓ ^⇒` | ↙ sexp |

## Selection

| Combo | Equivalents | Description |
| ----- | ----------- | ----------- |
| `+!→` | | expand selection |
| `+!←` | | shrink selection |
| `^!w ␣` | `^↑` 𝄇 `^+→` | select top level form |
| `+` nav | | select using navigation movement |

## Editing

| Combo | Equivalents | Description |
| ----- | ----------- | ----------- |
| `^!→` | | slurp → |
| `^!←` | | barf → |
| `^!+←` | | slurp ← |
| `^!+→` | | barf ← |
| `^+s` | | splice (remove enclosure) |
| `^+j` | | join adjacent sexps |
| `^!p ^!r` | `^↑ ^␈ ^→ ^␡ ^+s` | raise sexp |
| `^!t` | `^+← ` ✂ `^→` 📋 | transpose adjacent sexps |
| `!↑` | | drag sexp ← |
| `!↓` | | drag sexp → |
| `^!+u` | | drag sexp ↖ |
| `^!+d` | | drag sexp ↘ |
| `^!+k` | | drag sexp ↗ |
| `^!+j` | | drag sexp ↙ |
| `^+c` | swap `^+⇐` with `^↑ ^+⇐` | convolute |
| `^+␡` | `^+→ ␡` | kill sexp → |
| `^+␈` | `^+← ␡` | kill sexp ← |
| `^␡` | `^+⇒ ␡` | kill list → |
| `^␈` | `^+⇐ ␡` | kill list ← |
| `^!+␡` | `^␡ ^+s` | splice killing → |
| `^!+␈` | `^␈ ^+s` | splice killing ← |
| `^!+p` | | wrap with () |
| `^!+s` | | wrap with [] |
| `^!+c` | | wrap with {} |
| `^!+q` | | wrap with "" |
| `^!r ^!p` | | rewrap with () |
| `^!r ^!s` | | rewrap with [] |
| `^!r ^!c` | | rewrap with {} |
| `^!r ^!q` | | rewrap with "" |
