### Lock files for VISA conda environments

```
# Generate pixi lock file
pixi lock
# Convert to conda-lock file format
pixi run convert pixi.lock --output conda-lock-files/
# Convert to conda spec file format
# The pypi dependencies are only used by the converter, so it's safe to
# ignore them. But that also means we need all the packages on conda.
pixi workspace export conda-explicit-spec --ignore-pypi-errors conda-spec-files/
```

Creating a conda env from the spec files.
```
conda create --name myenv --file conda-spec-files/ess-diffraction_osx-arm64_conda_spec.txt
```
