# RM Mobile App Design System — Guidelines

> Surface: **Mobile** (iOS / Android / phone / native app).
> Figma: [🔺📁📱 RM Mobile App Design System](https://www.figma.com/design/d1GJJKVRXmccqe5KIVU6Sc/RM-Mobile-App-Design-System) · `fileKey: d1GJJKVRXmccqe5KIVU6Sc`
> Library key (for `search_design_system`):
> `lk-005e651a422793f4960f7a24ed3cb382c05d3de0356f901ccb8e36f11432c3c57c38f87b7b0a0b782043b4c6059867d47b9af55ed0891478115318c6dc09eb04`

**Extraction status:** ✅ **Color and Typography are identical to the web system**
(team-confirmed, authoritative). ✅ Component specs extracted: **Button, Icon Button,
Add-Customer FAB, Input field (+ Text area / prefix / supporting), Toast, Top Navigation
bar, Tab bar, Reservation cards, Bottom Navigation Bar, Actions menu, Bottom Sheet,
Table view, Tags (payment/category/booking-via/digit), Filters, Dialog Box, Date & Time
Picker, Dropdown, Chips, Checkbox, Radio, Calendar**, plus the full **Icon library** +
brand logos. ⚠️ Mobile Checkbox & Radio selection = **Success-green** (`#027A48`), unlike
web's brand-red. ✅ **Complete** — the component index below is the full mobile set; there
are no other components. Anything marked `[confirm]` must be resolved before use; never guess.

---

## Color ✅ (same as web)

Identical to the web system. Use these named roles only; no ad-hoc hex.

### Primary (brand red)
`Primary/Brand` **`#C52031`** · `Primary/Mild Red` `#E28F98` · `Primary/Light Red`
`#FFF5F6` · `Primary/Stroke` `#FDA29B` · `Primary/Hover` `#A7180D`.

### Neutral
Text `#212121` · Secondary text `#646464` · Background `#F8F8F8` · Disabled `#CCCCCC`
· Stroke/border `#D2D6DB` · White `#FFFFFF` · (doc grays `#111927` / `#6C737F`).

### Semantic — Error / Warning / Success / Prediction (BG · Header · Content)
| Family | BG | Header | Content |
| ------ | -- | ------ | ------- |
| Error | `[confirm]` | `#C52031` | `#D92D20` |
| Warning | `#FFF8E5` | `#DC9203` | `#D9A541` |
| Success | `#ECFDF3` | `#027A48` | `#039855` |
| Prediction | `#ECF4FF` | `#1361CE` | `#3A84EC` |

### Domain status (order / booking states)
Note `#4F7D97` · Progress `#3A84EC` · Cancel `#EB3454` · Delivery `#5EA51F` ·
Food Ready `#437616` · Dispatch `#ECBB02` · Prepare `#20C5C5`.

---

## Typography ✅ (same as web)

**Font `Poppins`** · weights Regular 400 / Medium 500 / SemiBold 600 / Bold 700 ·
line-height 100% · letter-spacing 0.

| Family | Size | Weights |
| ------ | ---- | ------- |
| `Display/Lg` | 30px | Medium · Semibold · Bold |
| `Display/Md` | 24px | Medium · Semibold · Bold |
| `Display/Sm` | 20px | Medium · Semibold · Bold |
| `Text/Lg` | 18px | Regular · Medium · Semibold · Bold |
| `Text/Md` | 16px | Regular · Medium · Semibold · Bold |
| `Text/Sm` | 14px | Regular · Medium · Semibold · Bold |
| `Text/XS` | 12px | Regular · Medium · Semibold · Bold |

---

## Effects / shadows

Web effect tokens apply (`Button Shadow` / `Input Box` `0 1px 2px #1018280D`,
`Focused Effect` `0 1px 2px #1018280D, 0 0 0 4px #F7F7F7`, `Box-Shadow`
`0 3px 10px #0000001A`, Toast `0 4px 16px #100B2714`). Confirm mobile-specific
elevation (bottom sheet, FAB) from the mobile Figma when those pages are extracted.

---

## Components — verified specs

Extracted directly from the mobile Figma pages (node ids noted). Default mobile
component width is **343px** (screen-width). `?` / `[confirm]` = not yet resolved.

### Button (`1:1149`)
- **Props:** type = Primary / Secondary / Tertiary / Quaternary · state = Default /
  Hover / Disabled · `leftIcon`, `rightIcon` booleans.
- **Sizing:** height **45px**, min-width 90px, padding 10px×24px, radius 8px, gap 6px
  (Quaternary 4px); left icon 20px, right icon 15px.
- **Colors:** Primary fill `#C52031` / text white; **Hover `#A7180D`**; Disabled =
  opacity 50%. Secondary white / border `#D2D6DB` / text `#212121`, hover bg `#F2F4F6`.
  Tertiary white / no border / text `#C52031`, hover bg `#FFF7F8`. Quaternary white /
  border `#FDA29B` / text `#C52031`, hover bg `#FFF7F8`.
- **Type:** `Text/Md/Medium` (Poppins Medium 16px).
- **Shadow:** `Button Shadow` `0 1px 2px #1018280D`; hover adds `Button Shadow Hovered`
  `0 0 0 4px #F7F7F7, 0 1px 2px #1018280D`.

### Icon Button (`1:1149`)
- **Props:** Primary / Secondary / Tertiary / Quaternary.
- **Sizing:** 32px square, padding 7px, radius 8px, icon 18px, shadow `0 1px 2px #1018280D05`.
- **Colors:** Primary `#C52031`; Secondary white + border `#D2D6DB`; Tertiary white;
  Quaternary bg `#FFF7F8` + border `#C52031`.

### Add Customer Button — FAB (`1:1223`)
- 56px round (radius 50px), bg `#C52031`, plus-icon 20px white, red glow shadow
  `0 4px 6px rgba(197,32,49,0.3)`.

### Input field (`1:143`)
- **Components:** `Input` (default), `Text area field`, `Text Field with prefix`,
  `Supporting Text`, `Header`.
- **Props:** state = Enabled / Focused / Disabled / Error · textConfig = Placeholder /
  Input · `leftIcon`, `rightIcon`, `prefix`, `required`, header & supporting toggles.
- **Sizing:** height **45px**, width 343px (prefix variant 281px), padding 12px, gap
  8px, radius 8px, border 1px, icons 20px. Text area 131px tall.
- **Colors:** bg white; border `#D2D6DB` (enabled/focused); label `#646464`; required
  `*` `#C52031`; placeholder `#979797`; typed text `#212121`; disabled text `#D2D6DB`.
  **Error** border `#D92D20`. **Focused** ring `0 0 0 4px #F7F7F7`. **Error+input** ring
  `0 0 0 4px #D92D2026`.
- **Type:** label `Text/XS/Medium` (12) · value `Text/Sm/Regular` (14) · supporting
  `Text/XS/Regular` (12).
- **Supporting text:** Default `#979797` · Success `#039855` · Error `#C52031` (with
  info icon 20px).
- **Prefix:** "+91" `#646464` 14px + chevron-down 14px + divider line.

### Toast Notification (`1:2003`)
- **Variants:** state = Cancel / Success / Warning / Attention.
- **Sizing:** width 343px; padding 16px; radius 12px; gap 12px; status icon 24px;
  close 20px; border 1px. Message body width ~245px.
- **Colors (bg / border):** Cancel `#FFF7F8` / `#C52031` · Success `#ECFDF3` / `#027A48`
  · Warning `#FFFCF5` / `#DC9203` · Attention `#ECF4FF` / `#1361CE`. Title `#212121`,
  body `#646464`.
- **Type:** title `Text/Sm/Bold` (14) · body `Text/XS/Medium` (12).
- **Shadow:** `0 4px 16px rgba(16,11,39,0.08)`.

### Top Navigation Bar (`1:2134`)
- **Variants:** Header type = With side menu (type 1) / With back button (type 2) /
  With button right side (type 3); props `showIconButton`, `show2ndButton`, `rightIcon`.
- **Sizing:** bar height 60px (full header 104px incl. 44px status bar); width 375px;
  padding 14px×16px; gap 12px (right cluster 16px). Icon buttons 32px (pad 7, radius 8);
  "15 min" pill h32 min-w90 px14 py4 radius8; icons 18px; back arrow 20px; side-menu/QR
  24px (QR radius 4, border 0.867px).
- **Colors:** bar bg `#FFFFFF`; title `#212121`; default icon button white + border
  `#D2D6DB`; primary icon button `#C52031`; "live" button border `#FDA29B`. Bar shadow
  `0 0 3px rgba(0,0,0,0.16)`; button shadow `0 1px 2px #1018280D`.
- **Type:** title `Text/Md/Medium` (16); pill label Poppins Medium 12.
- **Notes:** type1 = side-menu + title + [15-min pill, live button, QR]; type2 = back +
  title + primary icon button; type3 = side-menu + title + 1–2 outlined buttons.

### Tab Bar (`1:3091`)
- **Variants:** base `Tab Button Base` props type (1 / 4), `current`, `icon`, `badge`.
  Pre-composed sets: TabBar (Reservation/Served/Queue), Live Table (Default/Party hall/
  Non AC/Take Away), Sessions & Slots (regular/exclusive/inventory), Forms, CRM
  (Details/Profile/History).
- **Sizing:** tab height 53px; padding-x 20px; gap 8px; container bottom border 0.8–1px
  `#D2D6DB`; **active underline `border-b 2px #C52031`**. Fixed tab widths 99px / 125px;
  icon 20px; badge px8 py2 radius16.
- **Colors:** inactive label `#979797`; active label + underline `#C52031`; container
  white. Active badge bg `#FFF7F8` / text `#C52031`; inactive badge bg `#DEE2E5` / text
  `#979797`.
- **Type:** tab label `Text/Sm/Medium` (14); badge Poppins Bold 12.
- **Notes:** underline is the only active indicator (no fill). Type 4 adds a leading icon.

### Reservation Cards (`1:3563`) — 26-variant gallery
- **Variant `Type=`:** Queue · Reservations (Default) · Served · served-cancelled ·
  Served-no-show · reservation form · Reservations-meta · Reservations (paid tag) ·
  Paid form · eazydiner · Inquiry · Sessions & slots · Inventory · Slots · Inquiry
  (Payment pending) · Feedback-zomato · Feedback-swiggy · Users · Transactions
  (pending/successful/failed/tip) · reservation form link · Join queue QR.
- **Card shell:** width 375px (Slots 343px); height 86–143px; content row 343px; top &
  bottom border 0.8px `#D2D6DB`; card bg `#FFFFFF`. Detail-row gap 8px.
- **Representative — Reservations (Default) (`1:3623`):**
  - Booking-via tag: bg `#FEF3F2`, radius-bl 8px, text `#646464` 9px.
  - Guest name `#212121` underlined `Text/Sm/Medium` (14); repeat-count chip border
    `#979797` radius 11px text 10px; time/pax `#646464` 12px.
  - `Digit` badge 26×18 radius 15px: Table-no bg `#1361CE`, persons bg `#027A48`, text
    **Inter SemiBold 12** white (`Text/SM/Strong`).
  - Action buttons: 38px circle bg `#F2F4F6` radius 22px, icon 22px.
  - Icons: heart 16 · redirect 14 · table 17 · clock/pax 14–18.
- **Note:** the other 25 variants share this shell; extract a specific one's exact deltas
  from its node when needed.

> **Font exception:** small numeric badges (`Digit`) use **Inter SemiBold**, not Poppins.

### Bottom Navigation Bar (`1:4954`)
- **Variants:** tab item `Default` / `Selected`; tabs = Home · Calendar · Live Tables · Feedback.
- **Sizing:** bar 375×75px, top radius 6px, padding 10px; tab 86×75px (`px15 py12.5`,
  gap 6px); icon 24px.
- **Colors:** bar bg `#FFFFFF`; label Default `#646464`, Selected `#C52031`; top
  drop-shadow `0 -6px 5.35px rgba(0,0,0,0.04)`.
- **Type:** label `Text/XS/Medium` (12). Selected swaps icon asset + label color.

### Actions menu (`1:5139`)
- **Structure:** container + repeatable `Button` rows (e.g. Call, Send Reminder, Notes,
  Update Details, Mark as No Show, Remove from queue).
- **Sizing:** container w181, radius 8px, border 1px; row `px12 py8`, gap 13px, icon 20px,
  row bottom-border 1px (last row none).
- **Colors:** bg `#FFFFFF`; border `#D2D6DB`; label `#212121`; **destructive** label
  (e.g. "Remove from queue") `#C52031`.
- **Type:** label Poppins Regular 12px / line-height 18. Optional numeric badge (Inter SemiBold).

### Bottom Sheet (`3:5408`)
- **Variants:** `title` (Without / With title) · `showButtons`.
- **Sizing:** top radius 20px; padding 16px, gap 24px; content area 343×413px; heading
  row padding 16px + bottom border 1px, close 20px; footer buttons row 343px gap 16px.
- **Buttons:** h45, `px24 py10`, gap 6, radius 8, min-w90 — Secondary white/`#D2D6DB`/
  `#212121` + shadow `0 1px 2px #1018280D`; Primary `#C52031`/white.
- **Colors:** sheet bg `#FFFFFF`; stroke `#D2D6DB`; title `#212121`.
- **Type:** title `Text/Sm/Semibold` (14); buttons `Text/Md/Medium` (16).

### Table View (`3:5473`)
- **Variants:** state = Occupied / Empty Table / Preferred table / Selected-preferred /
  Empty-selected. Props: tableNo, time, billAmount, pax.
- **Sizing:** card radius 12px, border 1px, `px10 py16`; empty/selected 106×106px;
  Occupied status badge 23px top-right; pax icon 14px.
- **Colors:** bg `#FFFFFF`; default border `#D2D6DB`, **selected border `#FDA29B`**;
  table-no default `#212121`, **selected `#C52031`**; occupied number `#979797`; meta `#212121`.
- **Type:** table-no `Display/Sm/Regular` (20); time/bill/pax `Text/XS/Regular` (12).

### Tags (`3:6378`) — 4 tag families
Shared: radius 24px, `px8 py2`, label Poppins Medium 12px; icons 12–16px.
- **Payment type** (successful / pending / failed / Tip): Paid bg `#ECFDF3`/`#039855` ·
  Pending bg `#FFFCF5`/`#D9A541` · Failed bg `#FFF5F6`/`#D92D20` · Tip bg `#ECF4FF`/`#3A84EC`.
- **Category type** (VIP / Veg / Non veg / timer / Allergies): VIP bg `rgba(140,52,209,.08)`
  text `#8C34D1` · Veg bg `#ECFDF3`/`#027A48` · Non veg bg `#FFF5F6`/`#C52031` · timer bg
  `#ECF4FF`/`#3A84EC` · Allergies bg `#FFF6E7`/`#F79202`.
- **Booking via** (Zomato/Swiggy/Internet/Dine in/eazydiner/Queue form/walk in/reservation
  form/paid form/Meta): bg `#FEF3F2`, radius-bl 8px, `px8 py3` gap 4, icon 16px, label
  Poppins Medium 9px `#646464`.
- **Digit** (Table no / no of persons): 26×18 pill radius 15px; Table-no bg `#1361CE`,
  persons bg `#027A48`; digit Inter SemiBold 12px white.

### Filters (`3:7225`)
- **Variants:** `Filter` props textConfig Input/Placeholder · `leftIcon` · `rightIcon` ·
  `supportingText`. E.g. date filter (calendar icon), meal-time filter (clock + chevron).
- **Sizing:** input radius 7px, border 1px, `px16 py10`, gap 8, icons 16px, shadow
  `0 1px 2px #1018280D`; field stack gap 6; row gap 16.
- **Colors:** bg `#FFFFFF`; border `#D2D6DB`; value `#212121`; placeholder/hint `#979797`.
- **Type:** value/placeholder `Text/XS/Regular` (12).

### Dialog Box (`3:7315`)
- **Variants:** `With Title` / `Without title` · `showHeading` · `showDialogBoxButtons`.
- **Sizing:** dialog radius 8px, inner w343, gap 24px; heading padding 16px + bottom
  border 1px, close 20px; content w310; footer buttons row w312 gap 16.
- **Buttons:** h45, `px24 py10`, gap 6, radius 8, min-w90 — Secondary white/`#D2D6DB`/
  `#212121`; Primary `#C52031`/white.
- **Colors:** dialog bg `#FFFFFF`; **heading bg `#F3F4F6`**; stroke `#D2D6DB`; title `#212121`.
- **Type:** title `Text/Md/Medium` (16); buttons Poppins Medium 16.

### Date & Time Picker (`3:7394`)
- **Variants:** state = Time Picker / Date Picker / Range.
- **Sizing:** Time Picker 343×300 radius 10px (shadow `0 25px 40px -10px rgba(0,0,0,0.06)`);
  Date/Range 336×348 radius 8px. Apply btn min-w90 `px24 py10` radius 8. Time spinner
  cells bg `#F7F8FA` border `#E0E0E0` 0.6px radius 8; day cell 24px, selected ring 2px radius 23.
- **Colors:** Apply bg `#C52031`/white; selected day fill `#C52031` (white) or ring
  `#C52031`; day text `#212121`/`#202020`; disabled day opacity 50%; weekday `#A4B9DE`;
  range connector `#F2F4F6`; time selected value `#212121`, adjacent `#979797`.
- **Type:** day numbers Poppins SemiBold 14; month/year Poppins SemiBold 22; time values
  `Display/Sm` (20); Apply `Text/Md/Medium` (16).

### Dropdown (`3:7783`)
- **Variants:** list `scrollbar` Y/N (w343). Cell state = Default / Hover / Selected /
  Disabled; `showIcon`.
- **Sizing:** container border 1px `#D2D6DB` radius 8 w343; cell `px16 py10` gap 8;
  scrollbar track 4px / thumb `#D2D6DB`; optional checkbox 16px radius 4.
- **Colors:** Default white / text `#212121`; Hover bg `#F2F4F6`; **Selected bg `#FFF7F8`**
  + trailing check 20px `#C52031`; Disabled text `#DEE2E5`.
- **Type:** option `Text/XS/Regular` (12).

### Chips (`3:7899`) — 4 families
Shared: border 1px, radius 7px, Poppins Medium 12px, shadow `0 1px 2px #1018280D`;
hover adds ring `0 0 0 4px #F7F7F7`.
- **Chips / Chips2** (Default/Hover/Disabled/Selected/Selected-Disabled): w90 `px10 py12`;
  Chips has sub-line "Available - 12" Poppins Regular 10px `#3A84EC`; check 20, close 12.
- **Chips03** (Default/Hover/Disabled/selected): h32 p12 gap4; check 15, close 12.
- **Chips02** (filter pill): h32 p12 gap6.
- **Colors:** unselected border `#D2D6DB` / white / `#212121`; **selected border `#C52031`,
  bg `#FFF7F8`, text `#C52031`** (Chips03 selected border `#FDA29B`); disabled opacity 50–75%.

### Checkbox (`3:7997`) ⚠️ differs from web
- **Variants:** state Default/Hover/Focused/Disabled · `checked` · size Medium/Small ·
  `withText`, `supportText`, `semiChecked`.
- **Sizing:** Medium box 20px radius 6; Small box 16px radius 4; border 1px; row gap 12 (Md)/8 (Sm).
- **Colors:** unchecked white / border `#D2D6DB`. **Checked = GREEN: bg `#ECFDF3`, border +
  check `#027A48`** — NOT the web brand-red. Label `#212121`; support `#979797`.
- **Type:** label Poppins Regular 14; support 12.
- **Note:** **Mobile checkbox selected is Success-green, unlike web (`#C52031`).** Keep them distinct.

### Radio button (`3:8252`)
- **Variants:** state Default/Hover/Focused/Disabled · `selected` · size Medium/Small ·
  `withText`, `supportText`.
- **Sizing:** Medium 20px radius 10; Small 16px radius 8; border 1px.
- **Colors:** unselected white / border `#D2D6DB`; **Selected = GREEN** (ring + dot
  `#027A48`, Success) — pixel-confirmed, matching checkbox, **NOT** web brand-red; Hover bg
  `#ECFDF3`; label `#212121`; support `#979797`/`#5D5D5D`.
- **Type:** label Poppins 14.
- **Note:** like checkbox, mobile radio selection is Success-green, unlike web (`#C52031`).

### Calendar (`3:8558`)
- **Variants:** Status dot = Available / Overflow / Almost full / Fully booked / No booking
  (8px). Calendar card (375×109) = …selected per status. Month grid (375×359) = Default /
  Date Selected. + Calendar Top Bar (375×56).
- **Sizing:** day column 88px `px12 py23`; meal card white radius 8 p12 (shadow
  `0 1px 1.5px rgba(0,0,0,0.1)`); month-grid selected day ring radius 28.
- **Colors:** Available-selected card bg `#ECFDF3` / border+date+label `#039855`; status
  tokens — Available `#039855`, Almost full `#D9A541`, Fully booked `#D92D20` (Overflow / No
  booking dot hexes `[confirm]`). **Month-grid selected DAY = `#C52031`** ring+text (brand),
  with `#FDA29B` and a `#D9A541` indicator. weekday `#646464`; counts `#212121`/`#646464`.
- **Type:** date number `Text/Lg/Semibold` (18); meal label Poppins SemiBold 12; counts 10.
- **Note:** day-of-month selection uses brand red; availability cards use status colors.

### Component index — the complete mobile set (`node-id`)

This is the **full** list of mobile components (one Figma page each). There are no
others; everything is specced above.

| Component | Page |
| --------- | ---- |
| Input field (+ Text area, prefix, Supporting Text) | `1:143` |
| Button · Icon Button · Add-Customer FAB | `1:1149` |
| Icon library + brand logos | `1:1293` |
| Toast Notification | `1:2003` |
| Top Navigation Bar (type 1/2/3) | `1:2134` |
| Tab Bar (+ Live Table / Sessions & Slots / Forms / CRM tab sets) | `1:3091` |
| Reservation Cards (26 variants) | `1:3563` |
| Bottom Navigation Bar | `1:4954` |
| Actions menu | `1:5139` |
| Bottom Sheet | `3:5408` |
| Table View | `3:5473` |
| Tags (payment / category / booking-via / digit) | `3:6378` |
| Filters | `3:7225` |
| Dialog Box | `3:7315` |
| Date & Time Picker | `3:7394` |
| Dropdown | `3:7783` |
| Chips | `3:7899` |
| Checkbox | `3:7997` |
| Radio Button | `3:8252` |
| Calendar | `3:8558` |

### Icon library ✅ (`1:1293`) — full set
Default render **20px** (some 24px as noted); swatch tile 137×102px. Glyphs:
`eye` · `eye-off` · `check-circle` · `alert-circle` · `chevron-down` · `chevron-up` ·
`chevron-left` · `chevron-right` · `check` · `close` · `close-circle` · `info` ·
`info-circle` · `alert` · `qr code` · `arrow-narrow-left` · `Side menu` · `Menu` (24) ·
`Menu-2` (24) · `Queue` · `walk in` · `Reservation` · `dine in` · `plus` · `calendar` ·
`Home` · `Feedback` · `Table` (24) · `Download` · `upload` · `share` · `form share` (24) ·
`notes` · `added notes` (25) · `whatsapp` · `Call with badge` · `call` · `Update details` ·
`no of persons` · `copy` · `link` · `clock` · `hourglass` · `countdown` (16) · `Filter` ·
`Birthday` (24) · `Anniversery` (24) · `anniversary` (12) · `Edit` · `trash` · `Outlet` ·
`sessions&slots` · `Reports` · `inquiries` · `Users` · `forms` · `Transactions` ·
`resend` · `view feedback` · `play` (25) · `Search` (24) · `preview` (24) ·
`import/export` · `Column configuration` (24) · `sort` · `CRM` (24) · `live 2` (24) ·
`idea` · `inbox` (24) · `Table Change` (24) · `google` · `payment provider`.
Loyalty/emoji marks (36px): `fire (2) 1`, `star 1`, `heart (1) 1` → Regular / Loyal /
Die-Heart-fan customer tiers.

### Brand / platform logos (`1:1293`)
`Reservation Manager Logo` (63.5px) · `zomato` (24) · `swiggy` (24) · `eazydiner` (24).

> **Status:** the index above is the complete mobile component set — every page has
> been extracted. There are no other components.

---

## How to extract a missing value (mobile)

```
search_design_system(
  query: "<style or component name>",
  fileKey: "d1GJJKVRXmccqe5KIVU6Sc",
  includeLibraryKeys: ["lk-005e651a…09eb04"]
)
get_variable_defs(fileKey: "d1GJJKVRXmccqe5KIVU6Sc", nodeId: "<node using the token>")
get_design_context(fileKey: "d1GJJKVRXmccqe5KIVU6Sc", nodeId: "<component instance>")
```

Because mobile tokens are largely unexposed through search, a node-specific
Figma link (`?node-id=…`) to the relevant screen/component is usually required
to resolve exact values. Ask the user for one when needed.
