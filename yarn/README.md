- Upgrade Packages Interactively:
> `$ yarn upgrade-interactive --latest`

- Install a module globally:
> `$ yarn global add {{module_name}}`

- Install all dependencies referenced in the package.json file (the install is optional):
> `$ yarn install`

- Install a module and save it as a dependency to the package.json file (add --dev to save as a dev dependency):
> `$ yarn add {{module_name}}@{{version}}`

- Uninstall a module and remove it from the package.json file:
> `$ yarn remove {{module_name}}`

- Interactively create a package.json file:
> `$ yarn init`

- Identify whether a module is a dependency and list other modules that depend upon it:
> `$ yarn why {{module_name}}`

- Upgrading all dependencies:
> `$ yarn upgrade`

- Check For Integrity Of Dependencies:
> `$ yarn check --integrity`

- Remove Any Duplicate Dependency For npm or yarn:
> `$ yarn-deduplicate yarn.lock`

- Upgrading a specific package:
> `$ yarn upgrade PACKAGE-NAME`

==PS==: Adding the `--latest` flag at the end of `upgrade` commands makes yarn ignore the specified version range and install the latest version(s).
