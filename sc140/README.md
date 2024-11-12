#### supercollider 140

```
play{
    GVerb.ar(
        VarSaw.ar(
            Duty.ar(1/36, 2, SinOsc.ar(5).range
            (200,1300)
            ), 
        0.5, 0.4, 0.8
        ), 
    30, 1
    )
};
```

