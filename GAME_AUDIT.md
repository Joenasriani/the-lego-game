# BrickBuilder 3D — Full System Audit + Refurbishment Log

Audit/refurbishment date: 2026-04-25

## 1) Full System Audit (Brutally Honest)

### Interaction flows found
1. **Add block:** hover ghost + click plane/brick face to place.
2. **Move block:** select in Move mode, then relocate.
3. **Delete block:** delete mode click removes brick.
4. **Rotate block:** rotate via toolbar.
5. **Stack block:** top-face targeting allowed Y+ placement.
6. **Replace block:** originally missing (now added).

### Broken/confusing/inconsistent behaviors found
- Move behavior was previously two-step and not true drag, causing friction.
- Delete action was mostly mode-driven; selection-based deletion visibility was weak.
- Invalid placement failures were easy to miss.
- Selection/hover state feedback was too subtle.
- Camera could drift away from active build context without a strong recenter affordance.
- No direct replacement workflow despite being an expected builder action.

### UX friction points found
- Mental model mismatch: users expected “grab and move,” not “select then click elsewhere.”
- Hidden power actions (rotate/replace/delete contextual intent) not grouped around selection.
- Mode switching cost was high for common edit operations.

### Visual clarity issues found
- Ghost feedback did not consistently communicate valid vs invalid state.
- Selected/hovered blocks lacked strong visual distinction.
- Action discoverability for selected objects was limited.

### Hidden/non-obvious mechanics found
- Face-normal stacking worked but was not clearly telegraphed.
- Undo/redo existed but did not always feel tied to object-edit operations.

---

## 2) Precision Refurbishments Applied

### A. Add/Stack flow clarity and snap reliability
- Added stricter build bounds helper and validation in placement/move flows.
- Upgraded snap behavior with top/bottom/side face handling that prioritizes vertical stacking on top faces.
- Ghost preview now always shows strong **green(valid) / red(invalid)** feedback.

### B. Delete/Rotate/Replace visibility
- Added a persistent **Selected Block Actions** panel when a block is selected.
- Added explicit, always-visible:
  - Delete
  - Rotate -90°
  - Rotate +90°
  - Replace shape flow (select target shape + apply)

### C. Move interaction refactor (drag-based)
- Move mode now supports pointer drag behavior:
  - pointer-down on block starts drag,
  - live snapped preview follows pointer,
  - drop commits only if valid,
  - invalid drop is blocked with immediate message.

### D. Strong visual feedback
- Hovered block now highlights.
- Selected block now shows stronger emissive outline effect.
- Invalid operations produce immediate toast messages; no silent failures.

### E. Camera reliability
- Orbit controls tuned with wider zoom range.
- Added camera target tracking based on build centroid.
- Added explicit **Recenter** action.

### F. State/system integrity
- Preserved undo/redo and commit model.
- Centralized drag finalization logic to avoid partial/ambiguous moves.

---

## 3) Before vs After (Behavior)

### Move
- **Before:** select then click-to-place; less tactile.
- **After:** drag-to-move with live snapping and validity feedback.

### Delete
- **Before:** mostly mode-based.
- **After:** explicit selected-object delete button is always visible when selected.

### Replace
- **Before:** no replace workflow.
- **After:** select block → choose shape → Replace (same anchor retained, collision-checked).

### Stack
- **Before:** workable but under-signaled.
- **After:** face-aware snapping with clearer top-face vertical behavior + ghost validity color.

### Visual feedback
- **Before:** limited selection/hover distinction.
- **After:** hover highlight + selected glow + red invalid preview + toasts.

---

## 4) Remaining Honest Gaps (Not Ignored)
- App is still single-file; long-term maintainability needs component extraction.
- Save/reload still uses browser `alert` for some flows (should fully migrate to toasts).
- No guided challenge track yet (still sandbox-first).

---

## 5) Acceptance Snapshot
- [x] Actions are visible.
- [x] Interactions are predictable and reversible.
- [x] Drag move is live + snapped.
- [x] Delete/rotate/replace are explicit and discoverable.
- [x] Invalid actions are clearly signaled.
- [x] Camera is less likely to lose context.
