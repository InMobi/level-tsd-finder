# level-tsd-finder

leveldb backed conenctor for graphite web


## Installion instructions

### Assumption
You are familiar on how to install and operate graphite in general. If not, have a look at [these instructions](https://graphite.readthedocs.org/en/latest/install.html). The _install from source instructions_ [(this one)](https://graphite.readthedocs.org/en/latest/install-source.html) is what the rest of the document specifically based on.


### Graphite-web
__Assumption :__ The graphite version is 0.10.0 or above. Specifically, it needs to support the STORAGE_FINDERS directive

Add the following to your local_settings.py

```py
STORAGE_FINDERS = ( 
    'pyleveltsd_finder.gateway.LevelRpcFinder',
)

LEVEL_RPC_PATH="http://localhost:2005"
```

Note that you may need to modify the _STORAGE_FINDERS_ section if you have other storage mechanisms that need to be used. Most users would be interested in also adding _graphite.finders.standard.StandardFinder_ to the list.
