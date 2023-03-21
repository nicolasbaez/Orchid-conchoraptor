# Orchid-conchoraptor
A sweet and smooth tide

![buh](https://github.com/nicolasbaez/Orchid-conchoraptor/blob/main/xp004.gif)
```javascript
k = 0;
g = 16;
w = 500;
setup = (_) => {
  createCanvas(w, w);
  colorMode(RGB, w * 1.5);
};
draw = (_) => {
  noStroke();
  rect(0, 0, w, w);
  for (i = 0; i < w; i += g) {
    for (j = 0; j < w; j += g) {
      stroke(i, j, w);
      strokeWeight(noise(i, j, k) * g);
      line(i, j, i + g, j + g);
      line(i, j + g, i + g, j);
    }
  }
  k += 0.02;
};
function keyPressed() {
  if (key === "s") {
    saveGif("xp004.gif", 512, { delay: 0, units: "frames" });
  }
}
