## PyTricks

### Force keyword arguments

``` python
# In Python 3 you can use a bare "*" asterisk
# in function parameter lists to force the
# caller to use keyword arguments for certain
# parameters:

>>> def f(a, b, *, c='x', d='y', e='z'):
...     return 'Hello'

# To pass the value for c, d, and e you 
# will need to explicitly pass it as 
# "key=value" named arguments:
>>> f(1, 2, 'p', 'q', 'v')
TypeError: 
"f() takes 2 positional arguments but 5 were given"

>>> f(1, 2, c='p', d='q',e='v')
'Hello'
```



## PyMethod

**Note**: Reflection in python

``` python
# check all attribute of object
dir([object])
```



## PyPackage

### tempfile

``` python
# tempfile can be used to generate a file in /tmp
import tempfile
temp_file = tempfile.NamedTemporaryFile()
temp_file.name
```

### io

``` python
# io can be used to generate a 'virtual' file in RAM
# Actually, I used this module cooperated with threading module to dealing with low disk speed
import io
ram_file = io.BytesIO()
with open(<output_file>, 'w') as f:
    data_size = f.write(ram_file.getbuffer())
io_file.close()
```

