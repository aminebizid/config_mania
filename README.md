# Config Mania


## API
```
CreateScope(scope)
GetScopes()

CreateVersion(scope, version)
GetVersions(scope)

SaveConfig(scope, key, value, do_overwrite=false)            # Saves the config key within the latest version of the scope
SaveConfig(scope, key, value, version, do_overwrite=false)
SaveConfig(scope, dict, do_overwrite=false)
SaveConfig(scope, dict, version, do_overwrite=false)


GetConfig(scope, key)  # Get latest config version for a given key
GetConfig(scope, keys) # Get latest config version for a given keys

GetConfig(scope, key, version)  # Gets the latest version of the config key
GetConfig(scope, keys, version) # Gets the config of the specified keys of the requested version
GetConfig(scope, version)       # Gets all the config keys of the requested version


Subscribe(scope, version)            # Fires an event if the config changed
Subscribe(scope, key, version)       # Fires an event if the config changed
Subscribe(scope, keys, version)      # Fires an event if the config changed
```
