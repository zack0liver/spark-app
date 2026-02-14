# Spark — Known Bugs

## Open

### Browse view blank on swipe left
- **Status**: Fixed (ideas now appear when swiping left)
- **Description**: Swiping left from the capture view to the browse view results in a completely blank page. The "No ideas yet" empty state and any saved idea cards are not rendering.
- **Expected**: Should show idea cards (or empty state if no ideas saved).
- **Notes**: Likely a CSS/layout issue with the views-slider or browse-view sizing after the recent layout refactor.

### Save success animation not triggering
- **Status**: Open
- **Description**: After tapping "Save Spark", the idea saves to Firestore and appears in browse view, but the success overlay animation (checkmark pop-in + "Spark saved!" text + workspace clear/reset) does not display.
- **Expected**: Full-screen overlay with animated checkmark, then fade out and cleared textarea.
- **Notes**: Animations are scoped to `.save-success.show` class. The class is being added in the save handler but the overlay isn't appearing visually. May need to debug with browser DevTools to check if the overlay element is rendering and if the animation keyframes are firing.
