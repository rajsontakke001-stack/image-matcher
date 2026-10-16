# PhotoMatch — Simple UI

## Run
1. Extract the ZIP.
2. Open the `image-matcher` folder in VS Code (the folder containing `package.json`).
3. Run:
   ```bash
   npm install
   npm run dev
   ```
4. Open the local URL shown in the terminal.

## Use
1. Add photos or choose a folder for your photo database.
2. Upload the latest photo.
3. Click **Find matches**.
4. Only accepted matches are shown. The exact same image file gets 100%; different files must pass a conservative face-descriptor distance threshold (0.45). If no photo passes, the app displays “No match found” instead of presenting the closest unrelated photo as a match.
5. Use **Download report** to save the results as CSV.

## Notes
- The app uses a browser-based face descriptor model; an internet connection is needed the first time the model loads.
- Similarity percentages are estimates, not certainty of identity. Lighting, angle, blur, and face visibility affect the result.
- Images are stored locally in the browser's IndexedDB database.


## Gaming UI edition
This edition changes the styling to a dark neon game-arena look while preserving the existing image database, upload, matching and report functionality.


## Strict no-match fix
- Photos that fail the face-distance threshold are excluded from matching results.
- If no database photo passes the threshold, the report shows no reliable match found.
- A same-file SHA-256 match is accepted as an exact match.
- Face matching can still have false positives/negatives; validate the threshold with your own image set.
