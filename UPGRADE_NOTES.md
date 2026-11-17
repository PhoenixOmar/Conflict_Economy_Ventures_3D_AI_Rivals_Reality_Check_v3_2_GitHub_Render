# Upgrade notes — Reality Check Education Edition (v3.2)

**Complete replacement package.** Includes all files from the 3D AI Rivals edition. No old files need to be combined with it.

### Changes
- New `reality-content.js`: reflection prompts, four-economy comparison, final mediation dilemma and learning outcomes.
- Updated `server.js`: six host-controlled debrief phases, private individual phone submissions, anonymous synchronized results and polls; game ratings frozen after final awards.
- Updated `public/host.js`, `public/player.js`, and `public/styles.css`: integrated host controls, player submissions, mobile-friendly matrix and voting screens.
- Added `tests/reality-check.test.js`: verifies anonymity before reveal, synchronized steps, final scoreboard preservation, and resetting.
- `package.json` and health endpoint updated to **3.2.0**.

### Deploy without a nested folder error
1. Extract this ZIP and copy its **contents** into the GitHub repository's app directory.
2. If `server.js` is at the GitHub root, leave Render Root Directory blank. If the app lives in a subfolder, keep that exact subfolder in Render Root Directory.
3. Keep the commands `npm install` and `npm start`. Commit and push. Render normally deploys the new commit automatically.
4. **Deploy only between sessions:** the restart can erase active in-memory rooms. Create a fresh room after deployment.
5. Visit `/api/health` and verify `version: "3.2.0"`.
6. Test a Quick game with one human and three AI rivals. After the last round, click **Begin Reality Check** and answer from the phone. Check that no answers are visible on the host until Reveal.

### What has not changed
The five-resource economy, profits, strikes, AI strategy, factions, multiplayer rooms, QR joining, 3D map, gameplay scoring and initial team briefing remain the same.

### Validation
21 automated Node tests pass (17 inherited plus 4 debrief tests). Simulated desktop/mobile browser interactions passed without JavaScript errors. Live Node Socket.io connections were not tested in this environment because the required npm packages were not available locally.

