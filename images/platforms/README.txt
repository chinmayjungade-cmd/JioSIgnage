Platform logos for platforms.html (the "One platform, four ecosystems" cards).

Add these files here (transparent PNG recommended, roughly square, ~128px+):

  android.png    - Android logo
  windows.png    - Windows logo
  samsung.png    - Samsung logo
  lg.png         - LG logo

Each logo sits in a 56x56 white rounded tile with padding (object-fit: contain),
so a transparent square logo works best.

Until a file is added, the card automatically falls back to a tinted line icon
(via the <img> onerror handler) — so the page never looks broken.

You can also use .svg instead of .png — just update the src in platforms.html
(the four <img src="images/platforms/....png"> tags in the plat-grid section).
