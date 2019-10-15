# GDX2py

Read and write GAMS Data eXchange (GDX) files using Python.  

## Requirements

- GAMS: version 24.1 or higher
- Python: 3.6 or higher
- GAMS Data Exchange API (gdxcc): 7.0 or higher


### Installing GAMS

Get GAMS from [https://www.gams.com/download/](https://www.gams.com/download/) 
and install it to your system. No license is needed for the use of GDX libraries.


## Installation

Install with

    pip install [-e] git+https://github.com/ererkka/GDX2py
    
Use the `-e` switch to install in editable mode (for development).


## Usage

    >>> from gdx2py import GdxFile, GAMSSet, GAMSScalar, GAMSParameter
    >>> with GdxFile('/path/to/gdx/file.gdx', mode='w') as gdx:
    >>>     gdx['set1'] = GAMSSet(['a', 'b', 'c'])   # Write a set
    >>>     set1 = gdx['set1']  # Read a symbol
    >>>     gdx['set2'] = GAMSSet([('a', 'foo'), ('b', 'bar'), ('c', 'baz')])   # Write a 2-dimensional set
    >>>     gdx['scalar'] = GAMSScalar(3.14, expl_text="Value of pi")  # Write a scalar with explanatory text
    >>>     gdx['par1'] = GAMSParameter({'a': 1, 'b': 2, 'c':3, 'd': 4}, domain=['set1'])  # Write a parameter with domain
 

