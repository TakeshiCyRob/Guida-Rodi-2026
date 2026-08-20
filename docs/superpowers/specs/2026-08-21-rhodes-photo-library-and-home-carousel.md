# Photo library and day carousel

## Purpose

The guide must let two travellers choose places with their eyes, not merely read a list. A photograph represents the named subject, never a broad geographic area used as a placeholder.

## Content model

- Each visitable named place receives a dedicated, locally saved, credited photograph when an accurate reusable source exists.
- A stop containing two named places receives two independently captioned images; three named places receive three. Composite image strips never silently substitute one place for another.
- Restaurants, parking and logistical points receive an exact photo only when a reliable public source identifies that place. They otherwise retain map, description and no fabricated image.
- Each of the eight days has a gallery of 8–12 images. Its order follows the day and includes genuine alternatives only where a traveller must choose.

## Home gallery

The existing day-dependent photo band becomes a three-slot day carousel.

- The lead slot and two supporting slots always show different images from the selected day.
- Every 7 seconds all slots advance one step, using a crossfade; their offsets prevent the same image appearing twice at once.
- Back/next controls, swipe on touch screens, and a readable counter/caption expose manual selection.
- Interaction pauses automatic progression. `prefers-reduced-motion: reduce` disables autoplay and replaces animation with an immediate update.
- Changing day restarts the gallery at that day’s first three distinct images.

## Itinerary and atlas

- The expanded guide of every stop renders its exact image set, with captions identifying the individual places.
- POI cards use the exact photo of that POI only.
- Existing maps, markers, links and day selection remain independent of gallery state.

## Performance and accessibility

- Images are local JPEG/WebP assets, compressed for mobile, `loading="lazy"` outside the current three home images.
- Captions are visible; alt text identifies the subject rather than saying “image of the day”.
- Controls are buttons with labels and keyboard focus. No important choice depends on motion.

## Verification

1. Inventory every itinerary stop, POI and compound stop against dedicated assets/captions.
2. Confirm all local image URLs return 200 and no photo is used as a stand-in for a differently named place.
3. Test autoplay, pause, previous/next, day switching and reduced-motion behavior on desktop and a 390px iPhone viewport.
4. Recheck map coordinates and route marker order after the data-model migration.
