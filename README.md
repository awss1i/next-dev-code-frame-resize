# next dev code frames keep the startup terminal width

Code frames for server errors in `next dev` are sized to the terminal width from when the dev server started. After the terminal is resized, they keep that width.

1. Run `npm install`, then `npm run dev` in a terminal (not in CI, output not redirected).
2. Open http://localhost:3000/width. The route logs an error and the terminal shows its code frame.
3. Make the terminal window narrower.
4. Open http://localhost:3000/width again. The code frame still has the old width, so its lines wrap.

With `next@16.4.0-canary.61` the second code frame fits the narrower terminal.
