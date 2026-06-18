# RM Web App Design System — Guidelines

> Surface: **Web** (dashboard / desktop / browser).
> Figma: [🔺📁🖥️ RM Web App Design System](https://www.figma.com/design/L7QMwEGtWjMB5ODihwnKiR/RM-Web-App-Design-System) · `fileKey: L7QMwEGtWjMB5ODihwnKiR`
> Library key (for `search_design_system`):
> `lk-8bee2d8f1511c660d8395227ebb74fa0167958e6ce4798479e2678d478ad1a561fda23ff37ce9449c44b15b553d4f7cc2941c5cfb339319432318cc076136c4c`

**Extraction status (2026-06-18):** ✅ Typography (`5410:2642`) · ✅ Color
(`4709:2252`) · ✅ 16 components — Button, Input, Dropdown/Tooltip, Popup, Sidebar
menu, Header, Toast, Cards, Calendar, Extras/Tags, Logos, Toggle, Tabs, Table,
Checkbox/Radio, Side drawer (last two verified via screenshot + pixel sampling since
their canvases are too large to serialize). Icons = enumerate names on demand. A few
exact px marked `[confirm]`. Anything marked `[VALUE — extract from Figma]` /
`[confirm]` must be resolved from Figma before relying on it; never guess.

---

## Color ✅ VERIFIED

Source: Figma Colors page (`node-id 4709:2252`), extracted 2026-06-18 via bound-style
resolution (`get_variable_defs`) + swatch labels. Use these only; no ad-hoc hex.

### Primary (brand red)
| Role / style | Hex |
| ------------ | --- |
| `Primary/Brand` (Brand Color) | **`#C52031`** |
| `Primary/Mild Red` | `#E28F98` |
| `Primary/Light Red` | `#FFF5F6` |
| `Primary/Stroke` (red stroke) | `#FDA29B` |
| `Primary/Hover` | `#A7180D` (darker-red button hover) |

### Neutral (text / surface / line)
| Role | Hex |
| ---- | --- |
| Primary Text (`Neutral/Text`) | `#212121` |
| Secondary Text / Secondary Btn (`Neutral/Sub Content`) | `#646464` |
| Background (`Neutral/Background`) | `#F8F8F8` |
| Disabled (`Neutral/Disabled`, disabled button) | `#CCCCCC` |
| Stroke / border (`Neutral/Stroke`) | `#D2D6DB` |
| White (`Neutral/White`) | `#FFFFFF` |
| Doc grays | `Gray/900 #111927` · `Gray/500 #6C737F` |

> `Neutral/Grey 1` and `Neutral/Grey 2` exist as published styles but their exact
> hex wasn't separable on the page — `[confirm from Figma]`.

### Semantic — Error / Warning / Success / Prediction
Each family has `BG` (surface), `Header` (title/strong), `Content` (body).

| Family | BG | Header | Content |
| ------ | -- | ------ | ------- |
| `Error/*` | `[confirm]` | `#C52031` | `#D92D20` |
| `Warning/*` | `#FFF8E5` | `#DC9203` (Alert) | `#D9A541` |
| `Success/*` | `#ECFDF3` | `#027A48` | `#039855` |
| `Prediction/*` | `#ECF4FF` | `#1361CE` | `#3A84EC` |

> `Prediction/*` is an RM-specific semantic family (AI/forecast surfaces) — keep it
> distinct from Success/Warning. Pair `…/BG` + `…/Header` + `…/Content`.

### Domain status colors (order / booking states)
Documented on the Colors page for status chips/labels:

| Status | Hex |  | Status | Hex |
| ------ | --- |--| ------ | --- |
| Note | `#4F7D97` |  | Cancel | `#EB3454` |
| Progress | `#3A84EC` |  | Delivery | `#5EA51F` |
| Food Ready | `#437616` |  | Dispatch | `#ECBB02` |
| Prepare | `#20C5C5` |  | | |

### Elevation token (from this page)
- `Shadow/lg` = `0 4px 6px -2px rgba(16,24,40,.03)`, `0 12px 16px -4px rgba(16,24,40,.08)`

---

## Typography — Text styles ✅ VERIFIED

Source: Figma Typography page (`node-id 5410:2642`), extracted 2026-06-18.

- **Font family: `Poppins`** (the only typeface; weights below).
- **Weights:** Regular = 400 · Medium = 500 · SemiBold = 600 · Bold = 700.
- **Line height:** `100%` (auto / 1.0) on all token styles.
- **Letter spacing:** `0` on all token styles.

Two families: **Display** (headings, Medium/Semibold/Bold) and **Text** (body,
Regular/Medium/Semibold/Bold). Use the named style; never set an arbitrary size.

| Style family | Size | Weights (style names) |
| ------------ | ---- | --------------------- |
| `Display/Lg/…` | **30px** / 1.875rem | Medium · Semibold · Bold |
| `Display/Md/…` | **24px** / 1.5rem | Medium · Semibold · Bold |
| `Display/Sm/…` | **20px** / 1.25rem | Medium · Semibold · Bold |
| `Text/Lg/…` | **18px** / 1.125rem | Regular · Medium · Semibold · Bold |
| `Text/Md/…` | **16px** / 1rem | Regular · Medium · Semibold · Bold |
| `Text/Sm/…` | **14px** / 0.875rem | Regular · Medium · Semibold · Bold |
| `Text/XS/…` | **12px** / 0.75rem | Regular · Medium · Semibold · Bold |

Full token list (25): `Display/Lg/{Medium,Semibold,Bold}`,
`Display/Md/{Medium,Semibold,Bold}`, `Display/Sm/{Medium,Semibold,Bold}`,
`Text/Lg/{Regular,Medium,Semibold,Bold}`, `Text/Md/{Regular,Medium,Semibold,Bold}`,
`Text/Sm/{Regular,Medium,Semibold,Bold}`, `Text/XS/{Regular,Medium,Semibold,Bold}`.

> Documentation/specimen styles (not for general use): `Display lg/Normal`
> (Poppins Regular 48px / 60px / −2 letter-spacing) and `Text md/Normal`
> (Poppins Regular 16px / 24px / 0).

---

## Effects — shadows & focus (10)

| Style name | Purpose (inferred from name) | Value |
| ---------- | ---------------------------- | ----- |
| `Shadows/Shadow 2` | elevation, smallest | `[VALUE — extract from Figma]` |
| `Shadows/Shadow 4` | elevation | `[VALUE — extract from Figma]` |
| `Shadows/Shadow 8` | elevation | `[VALUE — extract from Figma]` |
| `Shadows/Shadow 16` | elevation, largest | `[VALUE — extract from Figma]` (Toast uses `0 4px 16px #100B2714`) |
| `Button Shadow` | button resting | `0 1px 2px #1018280D` ✅ |
| `Button Shadow Hovered` | button hover | `0 0 0 4px #F7F7F7, 0 1px 2px #1018280D` ✅ |
| `Box-Shadow` | generic container / drawer | `0 3px 10px #0000001A` ✅ |
| `Input Box` | input resting | `0 1px 2px #1018280D` ✅ |
| `Focused Effect` | input/control focus | `0 1px 2px #1018280D, 0 0 0 4px #F7F7F7` ✅ |
| `Focused w/Error input Box` | input focus + error | `0 1px 2px #1018280D, 0 0 0 4px #D92D2026` ✅ |
| `Shadow/sm` (Untitled-UI base) | small elevation | `0 1px 2px #1018280F, 0 1px 3px #1018281A` ✅ |

---

## Variables

No design **variables** are exposed through the published-library search (only
styles). If RM later publishes variables, resolve via `get_variable_defs`.

---

## Components — verified specs

Specs below are extracted directly from each component's Figma page (node ids
noted). Use these values exactly. `?` = not returned by the tool; resolve before
relying on it.

### Button (`5343:2396`)
- **Variants:** Type = Primary / Secondary / Tertiary / Quaternary · Size = Small /
  Medium / Large / Extra Large · State = Default / Hover / Disable · booleans:
  Icon Left, Icon Right, Only Icon.
- **Sizing:** height Small 32 · Medium 38 · Large 44 · Extra Large 50px;
  padding 10px×16px; min-width 90px; icon↔label gap 4px; radius 8px;
  border 1px (Secondary/Quaternary). Only-Icon = square at each height.
- **Colors:** Primary fill `#C52031` / text `#FFFFFF` (no shadow). Secondary fill
  `#FFFFFF` / border `#D2D6DB` / text `#212121`. Tertiary fill `#FFFFFF` / no
  border / text `#C52031`. Quaternary fill `#FFFFFF` / border `#C52031` / text
  `#C52031`. Disable = opacity 50%.
- **Type:** `Text/Sm/Medium` (Poppins Medium 14px).
- **Shadow:** `Button Shadow` = `#1018280D` 0/1 r2 on Secondary/Tertiary/Quaternary.

### Text field / Input (`4469:1472`)
- **Variants:** State = Enabled / Focused / Error / Disabled · Text = Placeholder /
  Input · booleans: leadingIcon, trailingIcon, supportingText, required, prefix.
- **Sizing:** input padding 8.5px×16px; field gap 8px; label↔field gap 6px;
  radius 7px; border 1px; icon 16px; default width 377px.
- **Colors:** bg `#FFFFFF`; border `#D2D6DB` (enabled/focused); label `#646464`;
  required `*` `#C52031`; placeholder/hint `#979797`; typed text `#212121`.
  **Error:** border/label/text/hint `#D92D20`. **Focused:** + 4px ring `#F7F7F7`.
- **Type:** label `Text/XS/Medium` (12px) · value `Text/Sm/Regular` (14px) ·
  hint `Text/XS/Regular` (12px).
- **Shadow:** `Input Box` = `#1018280D` 0/1 r2. Optional prefix slot (label + chevron + divider).

### Dropdown & Tooltip (`6395:1566`)
- **Tooltip:** Position = Center / Left / Right / +2. bg `#373737`, text `#FFFFFF`
  Poppins Regular 12px, padding 10px, radius 5px, pointer arrow.
- **Dropdown cell:** State = Default / Hover / Selected / Disabled × Checkbox Y/N.
  bg `#FFFFFF`, padding-y 10px, gap 8px, width 382px, ~38–40px tall; label
  `#212121` 12px; Selected → check icon 20px `#C52031`.
- **Dropdown container:** Scrollbar Y/N; ~382–386px wide.

### Popup / dialog (`7198:141`)
- **Variants:** No Icon / With Icon · booleans: title, showSubtext.
- **Sizing:** width 500px; radius 10px; header 16px×24px; body 24px; footer
  16px×24px; section dividers 1px `#D2D6DB`; icon badge 36px round; gap 12px.
- **Colors:** bg `#FFFFFF`; icon badge bg `#FFF7F8` (Primary/Light Red); title
  `#212121`; subtext & body `#646464`; footer = Primary + Secondary buttons.
- **Type:** title `Text/Md/Semibold` (16px) · subtext `Text/XS/Medium` (12px) ·
  body `Text/Sm/Medium` (14px) · buttons Poppins Medium 14px.

### Sidebar menu (`10483:43`)
- **Sizing:** drawer 292px wide (244px nav rail), 1024px tall; right border
  `#D2D6DB`; nav item padding 12px, gap 16px; outlet card radius 16px / border
  0.8px `#D2D6DB` / h67; icons 24px.
- **Colors:** bg `#FFFFFF`; active label `#C52031`, inactive `#646464`; outlet
  name `#0D2130` (Poppins SemiBold 12px); "New" badge `#3A84EC`/white; footer
  panel bg `#F2F4F6`; Download-APK button `#C52031`.
- **Type:** nav labels `Text/Md/Regular` (16px); footer copy `Text/XS/Medium` (12px).
- **Items:** Home · Live tables · Calendar · Feedback · Inquiries · Customer Profile ·
  Sessions & Slots · Forms · Reports · User Management · Transactions · Logout.

### Header (`10483:327`)
- **Variants:** showLeftArrow, showButton.
- **Sizing:** height 70px; padding 16px×24px; bottom border 1px `#D2D6DB`;
  button-group gap 16px; back arrow 24px.
- **Colors:** bg `#FFFFFF`; page title `#646464` (`Text/Lg/Medium` 18px); buttons =
  Secondary (white/`#D2D6DB`/`#212121`) + Primary (`#C52031`/white), h38 min-w90
  padding 10×16 radius 8. Default: "Live Status" + "Add Customer".

### Toast — Light Toast (`10483:12112`)
- **Variants:** State = Cancel / Success / Warning / Attention / +1.
- **Sizing:** width 343px; padding 16px; gap 12px; radius 12px; border 1px;
  icon 24px; close 18px; ~75px tall.
- **Colors:** Success bg `#ECFDF3`/border `#027A48`; Warning bg `#FFF8E5`/border
  `#DC9203`; title `#212121` (`Text/Sm/Bold` 14px); message `#646464` (12px);
  close `#979FA9`. Shadow `#100B2714` 0/4 r16.

### Cards (`10483:12272`)
- **Main card:** Type = User / Variant2. bg `#FFFFFF`, border 0.8px `#D2D6DB`,
  padding 24px, width 1100px; title `#212121` (`Text/Lg/Medium` 18px); 38px square
  action buttons (white / `#D2D6DB` / radius 8) with 20px icons + divider.
- **Also on page:** `Queue card` (1100×104) and tag sub-systems — `Customer type`,
  `Booking via` (Dine in / Zomato / Swiggy / Internet / eazydiner / queue form),
  `Category type tags` (VIP / Veg / Non veg / timer / Allergies), `Payment type tags`
  (successful / pending / failed / Tip), `Digit` (Table no / persons). Colors per
  tag `[confirm from Figma]`.

### Calendar (`10483:12720`)
- **Variants:** Calendar = Default (740×661). Gridcell = Default / overflow
  selected / Available selected / No-booking / Fully booked selected / almost full
  selected. Status dot = Available / Overflow / Almost full / Fully booked /
  No booking (8px).
- **Sizing:** cell ≈99.7×79.2px, padding 10px, gap 2px, border 1px; date pill
  radius 19.5px; status dot 8px; mini icons 12px.
- **Colors (Available-selected):** cell bg `#ECFDF3` / border `#039855`; date pill
  `#027A48` + white (14px); counts `#212121` (`Text/XS/Bold` 12px). Other states key
  to their domain status colors (see Color §Domain status).

### Extras — Tags / Chips / Table view (`10483:19722`)
- **Tag:** Type = Unselected / Selected / Disabled. Selected: bg `#FFF5F6`
  (Error/BG) / border `#FDA29B` (Primary/Stroke) / text `#C52031`; min-w 90px,
  padding 8px×10px, radius 8px, gap 2px; primary line Poppins Medium 12px, sub
  line Poppins Regular 10px; Button Shadow `#1018280D` 0/1 r2.
- **Also:** `Chips`, `Category type tags` (VIP/Veg/Non veg), `Table view` (State =
  Occupied / Empty / Selection, 106px square) — structure captured, colors `[confirm]`.

### Logos (`10483:12202`)
- Reservation Manager logo (63.5px) + brand marks `Zomato`, `Swiggy`, `Eazydiner`
  (24px each) with captions (~`Text/Md` 16px). SVG assets.

### Toggle / Switch (`5675:4814`)
- **Props:** Size = Small · State = Default / Focused / Disable · `status` (on/off) ·
  `icon` · `withText` · `supportText`.
- **Track:** 36×20px, radius 12px. **Off** bg `#D2D6DB` (Neutral/Stroke). **On** bg
  `#039855` (Success/Content green). Knob 16px, inset 2px; slides left→right (on).
- **Focused:** ring `Focused Effect` = `0 1px 2px #1018280D, 0 0 0 4px #F7F7F7`.
  **Disable:** opacity 50%.
- **With text:** label `Text/Sm/Medium` `#212121`; support text `#979797` (Poppins
  Regular 14px); label↔control gap 8px.
- **Segmented On/Off pill ("Type X — for tables", the `On-Off` comp):** 90px×24px,
  radius 12px; active half = `#C52031` (Off) or `#027A48` (On) with white label,
  inactive half white with black label; border `#D2D6DB`. Labels Poppins Medium 14px.

### Tabs (`10483:550`)
- **Props:** Tabs `type` = Queue / Reservation / Served. Tab button `type` = 1 / 2 /
  3 / 4 (T1 underline text-only · T2 pill/filled · T3 pill+icon · T4 underline+icon);
  booleans `current`, `badge`, `icon`.
- **Sizing:** button h 42px (also 41/53px); padding 16–20px horizontal; gap 7–8px;
  active underline `border-b 2px`; pill radius 8px; icon 20px. Badge `px8 py2`,
  radius 16px. Container bar `border-b 1px`.
- **Colors:** active text/underline `#C52031`; inactive text `#646464` (or `#979797`).
  Pill-active bg `#FFF7F8` (Primary/Light Red). Active badge bg `#FFF5F6` / text
  `#C52031`; inactive badge bg `#F3F4F6` (Gray/100) / text `#979797`. Bar bg
  `#FFFFFF`, stroke `#D2D6DB`. Pill adds Button Shadow `0 1px 2px #1018280D`.
- **Type:** label `Text/Md/Medium` (16) or `Text/Sm/Medium` (14); badge `Text/XS` (12).

### Table (`4431:2019`)
- **Structure:** single component (no variants). Width 1350px; root radius 10px;
  frozen first column 202px.
- **Sizing:** header row h 57px (`px20 py12`); body cell h 53px (`px20 py10`); cell
  divider `border-b 1px`; pagination bar h 59px (`px20 py12`), bottom radius 12px.
- **Colors:** header bg `#F2F4F6` (Neutral/Background); body bg `#FFFFFF`; row divider
  `#D2D6DB`; pagination bg `#FFECEE`; accent `#C52031`. Text: header `#646464`, cells
  `#212121`. Status-dot palette: `#06F5EC · #30D4E8 · #77CB60 · #F9AE01 · #C52031`.
- **Type:** header `Text/XS/Medium` (12); cells `Text/XS/Regular` (12) / `Text/Sm` (14).

### Checkbox & Radio (`5410:2827`) — verified visually (screenshot + pixel sample)
- **Components:** `Checkboxes` and `Radio Buttons`.
- **Variants:** Size = Small / Medium · State = Default / Hover / Focused / Disabled ·
  Config = without text / with text / with text + supporting text.
- **Checkbox:** rounded-square; unselected white fill, `#D2D6DB` border; **selected
  `#C52031` fill + white check**. Disabled = muted/low-opacity.
- **Radio:** circle; unselected white + `#D2D6DB` border; **selected `#C52031`** ring +
  centre dot.
- **Focused:** adds focus ring `Focused Effect` (`0 0 0 4px #F7F7F7`).
- **Label:** `Text/Sm/Medium` `#212121`; supporting text `#979797` (Poppins Regular).
- **Sizing:** control box `[confirm px — ~16 Small / ~20 Medium]`; label gap `[confirm]`.

### Side drawer (`10495:10411`) — verified visually (geometry too large to serialize)
- **Layout:** right-side overlay panel, **white** bg (`#FFFFFF`). Header (`Main Title`,
  optional `Supporting Text`) + close ✕ top-right · scrollable body content slot ·
  footer with **Secondary + Primary** buttons (right-aligned).
- **Header padding:** 24px left/right (per on-canvas design note; was 16).
- **Colors:** title `#212121`; supporting text `#646464`; body surface `#F2F4F6`;
  footer Primary `#C52031`/white + Secondary white/`#D2D6DB`/`#212121`; stroke `#D2D6DB`.
- **Shadow:** `Box-Shadow` = `0 3px 10px #0000001A`. **Type:** Poppins Md/Sm/XS.
- **Width:** `[confirm px]` (renders ~400–480px, similar to Popup 500px).

### Icons (`10495:10412`) — glyph set
The icon grid is too large for the MCP to serialize, and per-icon vectors aren't
needed (they're glyphs). Enumerate icon names on demand via `search_design_system`
(web library key above), or reference the named set in `mobile.md` (the two apps
share the same icon family). Render sizes 16 / 20 / 24px; default glyph color
`#646464` or contextual (`#C52031` when active).

---

## How to extract a missing value (web)

```
search_design_system(
  query: "<style or component name>",
  fileKey: "L7QMwEGtWjMB5ODihwnKiR",
  includeLibraryKeys: ["lk-8bee2d8f…136c4c"]
)
# then, for a value bound to a node:
get_variable_defs(fileKey: "L7QMwEGtWjMB5ODihwnKiR", nodeId: "<node using the style>")
get_design_context(fileKey: "L7QMwEGtWjMB5ODihwnKiR", nodeId: "<component instance>")
```

If a value is only available on a specific frame, ask the user for a Figma link
with `?node-id=…` pointing at it.
