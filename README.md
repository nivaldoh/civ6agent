# civ6agent
* **Map Controller**: Orchestrates the “pan-and-scan” process, moves the camera systematically until the map is exhaustively covered. Stops in non-overlapping positions.
* **Tile Classifier** (Deep Learning Model):
   * Identifies each tile’s “type” (e.g., terrain, resource, improvement, city, or other relevant categories).
   * Could also detect local features (rivers, roads, units, etc.).
* **Tile Matcher / Stitcher**: Figures out each extracted tile’s global coordinate. Uses overlap or keypoint matching to piece together local screenshots into the *world map*.
* **Map Representation**: Stores the current state of the entire known world in a 2D data structure plus any additional metadata. Updates “fog of war” status as new tiles come into view.
* **Updater**: During each turn, merges newly observed tiles into the existing map representation.
