# Add portrait images to Slide 10

**Prompt:** Add portraits of Pascal, Fermat, Bayes, and Shannon to the "From Gambling to Prediction" slide (Slide 10) in llm-30.tex.

**Actions taken:**
1. Downloaded 3 portraits from Wikimedia Commons via `Special:FilePath` (direct thumb URLs were blocked):
   - `figures/pascal.jpg` (61KB) -- Blaise Pascal, Versailles painting
   - `figures/fermat.jpg` (38KB) -- Pierre de Fermat portrait
   - `figures/shannon.jpg` (37KB) -- Claude Shannon, MFO photo
2. No verified portrait of Thomas Bayes exists; used a "?" circle placeholder in the Bayes box title.
3. Restructured the Pascal-Fermat tikzpicture to show portraits with exchange arrows between them.
4. Added Shannon portrait inline in the tcolorbox title bar.
5. Compiled with 0 errors, 0 overfull boxes, 0 warnings.
6. Copied PDF to `docs/llm-30.pdf`.

**Outcome:** Slide 10 now shows portrait images for Pascal, Fermat, and Shannon, with a placeholder for Bayes. Layout verified visually.
