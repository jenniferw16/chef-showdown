# Chef Showdown — Netlify package

This package contains the existing Chef Showdown Test Mode plus an initial online multiplayer implementation.

## Publish from an iPhone
1. Open Safari and sign in to Netlify (create a free account if needed).
2. Open Netlify Drop: https://app.netlify.com/drop
3. Upload the ZIP file after extracting it in the Files app. Netlify Drop needs the project folder contents; if Safari/Files cannot upload the extracted folder, use the Netlify dashboard's manual deploy flow.
4. Wait for the deploy to finish and open the generated site URL.
5. Test from two separate devices using **Set up a player room**.

## Important
- Test Mode remains a local solo mode with simulated chefs.
- Online rooms use a Netlify Function and Netlify Blobs; room state and answer scoring are handled server-side.
- This package is a first deploy candidate, not a verified production release. It has not been deployed to your Netlify account or tested across independent live devices from this environment.
- Netlify Blobs is key/value storage, not a full transactional database. The function serializes room mutations with a short-lived lock. For a high-traffic public game, migrate room state to a transactional database before relying on it for large tournaments.
- Rooms expire after six hours. The first version supports up to eight players, four rounds, twenty questions, 20-second questions, and server-validated answers. The host advances each question after everyone answers or the timer expires.
