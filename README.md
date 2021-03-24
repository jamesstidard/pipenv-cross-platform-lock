# Pipenv Cross Platform
`pipenv` will only create a lock file for the current platform it has been run on.
This means other platform specific dependencies are not track, so sharing a lock
file across platforms can lead to missing dependencies.

Unless all developers run `pipenv lock --keep-outdated` the chances are dependnecies
will be dropped for other platforms and build broken.

This github workflow will create a commit making sure all platforms are handled in
the `Pipfile.lock` and then committing it back to the repo.
