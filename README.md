### Lock files for VISA conda environments

```
# Generate pixi lock file
pixi lock
# Convert to conda-lock file format
pixi run convert pixi.lock --output conda-lock-files/
```
