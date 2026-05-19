linspace
inline

## Numerical Cancellation
There is two ways of dealing with it:
### Rationalization
If there is a $-\sqrt{x}$ (negative square root of something) you may be able to get rid of that by using rationalization and avoid numerical cancellation.
### Taylor Expansion
If there is something like $e^x$ or $sin(x)$ you can avoid numerical cancellation by using taylor expansion of it.

You can find the taylor expansion of a function by doing:
```
f = @(x) sin(x);
taylortool(f);
```

![[Pasted image 20240701021818.png]]
![[Pasted image 20240701022016.png]]
## N, t
