```
p1: stack(s("[bd sd bd hh*2 | bd ~ hh cp | cp:4 hh hh sd:2 | sd bd hh*2 cp]")
    .fast(3)
    .decay("<.1 .2 .3 .4>").sustain(0.3)
    .pan("<.5 1 .5 0>")
    .room(0.5)
    .gain(0.8)
    .lpf("1000:.2 1200:.4 1400:.6 1600:.8")
    .lpe(sine.range(500,1500))
    .bank("RolandTR909")
)

p2: stack(n("7 2 3 9").scale("C:minor") 
    .s("square supersaw")
    .fast(3)
    .decay("<.1 .2 .3 .4>").sustain(0.2)
    .release("<0 .1 .4 .6 1>") 
    .pan("<.5 1 .5 0>")
    .lpf(perlin.range(200, 1000))
    .lpe(sine.range(500,1000))
)

p3: stack(n("[1,3,5,7] | [2,6,9,0] | [4,9,8,3] | [6,0,2,7]")
    .sometimes(x=>x.add(n("0 7 5 9").scale("C:minor")))
    .scale("C:minor") 
    .s("gm_synth_strings_2")
    .fast(6)
    .decay("<.1 .2 .3 .4>").sustain(0.2)
    .release("<0 .1 .4 .6 1>")
    .room(3)
    .gain(0.3)
)

await initHydra()
osc(50, 3, 2.5)
  .modulate(noise(10), 1)
  .blend(osc(20, 0.1, 0.5), 0.5)
   shape(4, 0.5, 0.8)
  .rotate(() => Math.sin(time) * 0.5)
  .colorama(1)
  .luma()
  .out()
osc(10, 0.1, 2)
  .colorama(0.5)
  .color(1.0, 1.5, 0.3)
  .rotate(0.1, 0.2)
  .modulate(noise(2), 0.4)
  .out() 

await initHydra()
osc(45, 1, 10)
  .modulate(noise(20), 0.3)
  .blend(osc(15, 0.1, 10), 0.2)
  .color(0.7, 0.7, 1) //
  .rotate(() => Math.sin(time) * 0.5)
  .colorama(0.2)
  .luma(0.3)
  .out()
```

##### run on [Strudel REPL](https://strudel.cc/) 
#### feel free to edit parameters^ 





