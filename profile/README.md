# Point:project

> _"If there's a limit, we break through it._
> _If there's no limit, we become the limit._
> _Repeat until it fails."_
> - N3ZT POSSIBLE G3N

We build window managers. Lean ones. The kind that run on hardware other people threw away, do more than the alternatives, and use less RAM than a browser tab.

No bloat. No middleware. No excuses.

---

## The Projects

### [Point:Blank](https://github.com/Point-project/PointBlank) - X11 Window Manager
`C++20` · `Unstable/WIP` · `v1.0.1.0`

A tiling window manager for X11 with 8 layout modes, a proper DSL, 50+ EWMH atoms, a `dlopen` plugin system, and a hot-reloading config. Leaner than dwm. More capable than i3.

```
PSS at idle:     401 KB
Own memory:      240 KB
Dirty pages:      90 KB
Total RSS:        3.6 MB   (including all shared system libraries)
```

Tested on a Lenovo 500e Chromebook. If it runs there, it runs anywhere.

**Why it exists:** Someone got mad enough at existing WMs to write their own. That's the whole origin story.

→ [Repository](https://github.com/Point-project/PointBlank) · [README](https://github.com/Point-project/Pointblank#readme)

---


## The Philosophy

We don't add features to add features. Every line of code in a Point:project binary is there because removing it would break something real. Every kilobyte of RAM is accounted for. If a feature can't justify its memory cost, it doesn't ship.
The hardware target isn't aspirational it's a hard constraint. If it doesn't run well on a Celeron N4100, we didn't finish it yet.

---

## Who We Are

**N3ZT POSSIBLE G3N** - Point:project founder, the One Maniac™
We are not a company. We are not a foundation. We are people who got frustrated with the state of desktop software and decided to do something about it, one malloc at a time.

---

## The Numbers (Point:Blank, verified)

| Metric | Value | Context |
|---|---|---|
| PSS | 401 KB | Full EWMH, 8 layouts, DSL, plugin system |
| vs dwm | 6× smaller | dwm: ~2.5 MB PSS |
| vs i3 | 45× smaller | i3: ~18 MB PSS |
| vs bspwm | 25× smaller | bspwm: ~10 MB PSS |
| Dirty pages | 90 KB | What the core logic actually touched |
| Codebase | 19,010 lines | 29 `.cpp` + 32 `.hpp`, C++20 |

These aren't cherry-picked. Measured with `smem`, `pmap`, and `/proc/[pid]/smaps` on Arch Linux, Lenovo 500e, one terminal open.

---

## The Stack

| Project | Language | Target | Status |
|---|---|---|---|
| Point:Blank | C++20, 19K lines | X11 / Xlib |  Unstable |

Every Point:Project's WM use a custom `.wmi` DSL for configuration. We target the same hardware. The same philosophy about what software should cost to run.

---

## Contributing

Read the code first. It's dense but it's clean.

**Point:Blank**: Modern C++20, RAII everywhere, no raw owning pointers, no exceptions in hot paths. Test your changes. Submit a PR. Wait for the One Maniac™ to review.
Extensions for Point:Blank: copy `extension_template/`, implement your hooks, compile to `.so`, done. Extensions go through ABI review before bundling.

Bug reports are more useful than silence. Coffee is more useful than either.

---

## Links

| | |
|---|---|
| Point:Blank repo | [Point:Project/Point:Blank](https://github.com/Point-project/PointBlank) |
| License | MIT (both projects) |
| Tested on | Lenovo 500e 2nd Gen, Arch Linux |
| Minimum viable hardware | Anything with a CPU and enough RAM to be embarrassed about using more |

---

_Point:project - the limit ends. the void doesn't._
