# EasyEDA and STM32 Board Design

Animated, browser-based talks with printable handouts.

## For the event: start here

Open **`f446-build.html`**. It's the main event deck, 25 slides in four parts:

1. **The basics** (slides 3–8): the EasyEDA Standard screen, finding parts, wires, net labels and shortcuts.
2. **Two boards** (9–10): the STM32F407VGT6 robot I/O hub and the STM32F446RET6 fast control loop, and why we build the F446 first.
3. **Build the F446 core** (11–21): seven blocks wired pin by pin on the actual U1 symbol from our schematic. Each block's pins light up with their net labels, and the parts to add are drawn alongside.
4. **Start working** (22–25): task cards to hand out, splitting the work across sheets, common questions and links.

Print **`F446-Build-Sheet.pdf`**, one per person. Page 1 lists every core pin and what it connects to, with checkboxes. Page 2 is the EasyEDA Standard shortcut list.

Print **`F446-Parts-List.pdf`** too. It's three pages:

1. **Sheets 1 and 2** (MCU core, power and USB): every part with its designator, value, package and LCSC number. In EasyEDA Standard, press `Shift+F`, paste the LCSC number (for example `C14663`) and place the part. Each row also says what the part connects to and whether it's a JLCPCB Basic or Extended part.
2. **Sheets 3 and 4** (clocks and debug, signs of life), then an order list with one line per LCSC number: 20 different parts, 34 pieces per board.
3. **The Nucleo-F446RE**: which pins match our board, how to program our board with the Nucleo's ST-LINK, the first firmware to write, and a plan to Thursday and the final.

The SWD header J2 uses the same pin order as the Nucleo's CN4 debug header (1 +3V3, 2 SWCLK, 3 GND, 4 SWDIO, 5 NRST, 6 SWO), so it wires straight across.

The deck and the build sheet are written for **EasyEDA Standard** (easyeda.com/editor), the editor in our screenshots. The older lesson in `index.html` and `EasyEDA-Pro-Shortcuts.pdf` are for **EasyEDA Pro**, where some menus and keys differ.

## All the talks

1. **Build an STM32F446 board, from the basics up** (`f446-build.html`). EasyEDA Standard. The event deck above.
2. **Designing a PCB in EasyEDA Pro** (`index.html`). Students build one small board start to finish in [pro.easyeda.com/editor](https://pro.easyeda.com/editor): a push button that lights an LED. Comes with a two-page Pro shortcut sheet.
3. **Picking parts for a custom STM32 board** (`mcu-parts.html`). The deeper talk on going from requirements to a parts list and choosing the crystal, with a live crystal calculator. Comes with a three-page fill-in worksheet.

## What's in this folder

| File | What it is |
|---|---|
| `f446-build.html` | **Event deck:** EasyEDA Standard basics, then the F446 core wired pin by pin, 25 slides |
| `f446-build-sheet.html` | Event handout: the build sheet as a web page, with a Print button |
| `F446-Build-Sheet.pdf` | The same build sheet as a 2-page letter-size PDF |
| `f446-parts-list.html` | Parts list by EasyEDA sheet with LCSC numbers, the order list and the Nucleo plan, as a web page |
| `F446-Parts-List.pdf` | The same parts list as a 3-page letter-size PDF |
| `index.html` | Talk 1: the EasyEDA Pro lesson, 21 slides with step-by-step animations |
| `cheatsheet.html` | Talk 1 handout: the shortcut sheet as a web page, with a Print button |
| `EasyEDA-Pro-Shortcuts.pdf` | The same shortcut sheet as a 2-page letter-size PDF |
| `mcu-parts.html` | Talk 2: picking STM32 parts and crystals, 23 slides with a live crystal calculator |
| `parts-worksheet.html` | Talk 2 handout: the fill-in worksheet as a web page, with a Print button |
| `STM32-Parts-Worksheet.pdf` | The same worksheet as a 3-page letter-size PDF |
| `fonts/` | Barlow typeface files so everything looks right offline (SIL Open Font License, see `fonts/OFL.txt`) |

## Talk 2: picking parts for a custom STM32 board

Open `mcu-parts.html`. The keys are the same as talk 1 (listed below).

| Slides | Covers |
|---|---|
| 1–3 | The two boards and the eight-step method |
| 4–7 | Requirements, pin budget, reading the part number, locking the pinout in CubeMX |
| 8–11 | The support circuit every STM32 needs, power, interface parts, stock and assembly |
| 12–19 | Crystals: why, which frequency, the datasheet, gain margin, load capacitors, a live calculator, layout, and crystal vs oscillator |
| 20–21 | Parts lists for Board A and Board B |
| 22–23 | Discussion questions and sources |

**Updating the parts lists.** Slides 20 and 21 (and the pin budget on slide 5) are built from two lists near the top of the `<script>` in `mcu-parts.html`, marked `EDIT HERE`. Fill in `part`, `lcsc` and `cls` (`"Basic"` or `"Extended"`) for each row; anything left as `""` shows as "To pick". Edit `PINS` to change the pin budget bars.

**The crystal calculator** (slide 17) uses ST's start-up check from application note AN2867. Type in any crystal's datasheet values, or use the five example presets. All example values are illustrative; use the datasheet for the crystal you buy.

## Presenting

Open `index.html` in Chrome, Edge, Firefox or Safari. It works from a USB stick or a local folder with no internet connection.

| Key | Does |
|---|---|
| `→` `Space` `Page Down` or a clicker | Next step or slide |
| `←` `Page Up` | Back |
| `N` | Show or hide speaker notes |
| `F` | Full screen |
| `Home` / `End` | First / last slide |
| `?` | Show the key list |

Many slides animate in steps (wires drawing, parts moving into place, tracks routing), so press Next to play each step. You can also link to a slide directly: `index.html#13` opens slide 13.

### Lesson outline

1. Title
2. The eight-step workflow
3. What EasyEDA Pro is
4. **Step 1:** Create a project
5. The editor layout
6. Moving around the canvas
7. **Step 2:** Place the parts
8. **Step 3:** Wire the schematic
9. **Step 4:** Check the schematic
10. **Step 5:** Convert to a PCB
11. **Step 6:** Board outline and design rules
12. **Step 6:** Lay out the parts
13. **Step 7:** Route the tracks
14. **Step 7:** Add a ground pour
15. **Step 8:** Run the design rule check
16. Check it in 3D
17. **Step 8:** Export and order
18. Mistakes to catch before you order
19. Lab assignment
20. Shortcuts worth memorizing
21. Questions and resources

## Putting it on GitHub

### Upload the files

1. Sign in to [github.com](https://github.com) and click **New repository**. Name it something like `easyeda-lesson`, make it **Public**, and click **Create repository**.
2. On the new repository page, click **uploading an existing file**.
3. Drag in **everything inside this folder**, including the `fonts` folder. Make sure `index.html` ends up at the top level, not inside another folder.
4. Click **Commit changes**.

### Turn on GitHub Pages so students get a link

1. In the repository, go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Choose the **main** branch and the **/ (root)** folder, then click **Save**.
4. After a minute or two, the page shows your site address. It looks like `https://YOUR-USERNAME.github.io/easyeda-lesson/`.

Share that link with students. The site address opens the EasyEDA Pro lesson (`index.html`). Every other file is at the same address followed by its name. For the event, share `.../f446-build.html`, `.../F446-Build-Sheet.pdf` and `.../F446-Parts-List.pdf`.

## Printing the shortcut sheet

Print `EasyEDA-Pro-Shortcuts.pdf` double-sided on letter paper. The front has the everyday shortcuts and where each menu command lives; the back has every default shortcut.

Print `STM32-Parts-Worksheet.pdf` for talk 2: one page per board plus a crystal page, single-sided so people can write on every page.

If you edit `cheatsheet.html` or `parts-worksheet.html`, re-create the PDF from Chrome: **Print → Save as PDF**, paper size **Letter**, margins **None**, and turn on **Background graphics**.

## Editing the lesson

Slide text lives in `index.html` (talk 1) and `mcu-parts.html` (talk 2). Each slide is a `<section class="slide">` block, and the speaker notes for that slide are in the `<aside class="notes">` inside it. Open the file in any text editor (VS Code, Notepad, or GitHub's own editor with the pencil icon) and change the words between the tags.

## A note on the shortcuts

The keys come from the official EasyEDA Pro shortcut reference: [prodocs.easyeda.com/en/introduction/hotkeys](https://prodocs.easyeda.com/en/introduction/hotkeys/). Anyone can change their keys under **Settings → Shortcut Keys**, so a shared lab computer may not match. Some setups route tracks with `Alt+W` instead of `W`, and the zoom keys may be unassigned by default (the scroll wheel always works).

The dialogs and panels in the slides are simplified illustrations, not screenshots, so the real editor will look a little different.
