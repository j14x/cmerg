# mfile
Python parser for CarMaker ERG files.

## 

## Use and Examples

Moslty these are notes for myself but hopefully someone else finds them useful.

### Examples

Make sure that all the dependencies are installed.

``` pip install asammdf numpy ```

Import the package folder.

``` import mfile ```

Create ERG file object. (Using example file from repo)

``` log1 = mfile.ERG('test-data/Test-Dataset-1_175937.erg') ```

List of the signals in the file.

``` log1.signals ```

Save the vehicle speed signal to a variable.

``` speed = log1.get('Vhcl.v') ```

Plot signal.

``` speed.plot() ```

Add signal to dataframe.

``` python

# New easy call to return a pandas dataframe.
df = log1.to_pd()

```

``` python

# Simple example of adding ERG data to pandas.
# TODO: Make 'toPd()' call
import mfile
import pandas as pd
import numpy as np

log1 = mfile.ERG('data-file.erg')

speed = log1.get('Vhcl.v')

t = np.array(speed.timestamps)
spd = np.array(speed.samples)

df = pd.DataFrame({'time':t, 'speed':spd})

```
