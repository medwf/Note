```python
import random
dir(random) = ['BPF', 'LOG4', 'NV_MAGICCONST', 'RECIP_BPF', 'Random', 'SG_MAGICCONST', 'SystemRandom', 'TWOPI', '_ONE', '_Sequence', '_Set', '__all__', '__builtins__', '__cached__', '__doc__', '__file__', '__loader__', '__name__', '__package__', '__spec__', '_accumulate', '_acos', '_bisect', '_ceil', '_cos', '_e', '_exp', '_floor', '_index', '_inst', '_isfinite', '_log', '_os', '_pi', '_random', '_repeat', '_sha512', '_sin', '_sqrt', '_test', '_test_generator', '_urandom', '_warn', 'betavariate', 'choice', 'choices', 'expovariate', 'gammavariate', 'gauss', 'getrandbits', 'getstate', 'lognormvariate', 'normalvariate', 'paretovariate', 'randbytes', 'randint', 'random', 'randrange', 'sample', 'seed', 'setstate', 'shuffle', 'triangular', 'uniform', 'vonmisesvariate', 'weibullvariate']

random.random()
# Return the next random floating point number in the range `0.0 <= X < 1.0`

random.uniform(a, b)
# Return a random floating point number _N_ such
	# that `a <= N <= b` for `a <= b` and `b <= N <= a` for `b < a`.

# uniform(a, b) = (b - a) * random()

random.randint(a, b)
# Return a random integer _N_ 
# such that `a <= N <= b`. Alias for `randrange(a, b+1)`.

random.choice(seq)
# Return a random element from the non-empty sequence _seq_.
# If _seq_ is empty, raises IndexError "IndexError").

```