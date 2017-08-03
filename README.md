# Bukwild Stylus Library

Components:

- **index.styl** - The package.json `main`, this glob loads all mixins from the "lib" directory.  It also imports other stylus npm dependencies.  These dependencies are generally functions and mixins that have utility for all projects.
- **lib/** - Contains .styl files that define functions / imports. None of these files should contain any css selectors.  Read the comments within the individual files for details.
- **boilerplate.styl** - CSS rules that are intended to be loaded after a CSS reset or normalize on a project.  Essentially, this is a set of global Bukwild conventions.
