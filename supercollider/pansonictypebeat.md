```supercollider
n = 12;
c = LFSaw.ar(50) * Env.perc(1/100,1/10).ar(0, TDuty.ar(Dseq([7/40,7/40,7/40,7/40],2))) * ({ LFNoise1.ar(0.1).range(1,1.01) } ! n);
10.do{ c = (c.distort + c)*0.7};
c = c * 1.5;
c = DelayC.ar(c, delaytime: 0.01, feedback: 1);
c = FreeVerb.ar(c, 0.8, 0.7); // Better when first value is higher
```
The ~400BPM sound, with a bit of distortion and reverb thrown in. Note to self: look into `Dseq`.

```supercollider
10.do{ a = (Normalizer.ar(a.distort, 1.0) + a) * 0.9}; // distort a bunch of times and normalise on every iteration to keep it in check
```
Better loop distortion
```supercollider
var bpm = 400;
a = WhiteNoise.ar(freq: 440, mul: SinOsc.kr(400/60));
```
Using ugen for multiplier argument.
