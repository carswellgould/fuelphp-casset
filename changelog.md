Changelog
=========

This file lists the important changes between versions. For a list of minor changes, check the log.

v1.11
-----
 - Asset URLs can be obtained, see "Getting asset paths / urls".
 - Casset::add_group() has been re-implemented.
 - Callbacks now exist: You can use these to process js/css files after they're loaded, but before they're cached. Allows use of SASS, Coffeescript, etc.
 - Exception now thrown if someone attempts to define a group that already exists.
 - Group options are now specified using array syntax, instead of separate function arguments.
 - Option to inline groups moved from Caset::render() to when the group's defined.
 - Option to add attributes to a group's tag moved from Casset::render() to when the group's defined.
 - Add dependencies between groups. Rendering a group will automatically render its dependencies.
 - New functions to allow changing of group options on-the-fly.

v1.10
-----
Hotfix release.
Fixed #3, reported by krtek4, where render_css had an erroneous second loop, meaning that it would render files when it wasn't supposed to

v1.9
---
Hotfix release.
Fixes #1, reported by jaysonic, where add_path was (for some reason) private.


v1.8
----

- CSS files are no longer sorted, instead keeping the order they were added to the group in.
- Allow overriding of js_dir, css_dir and img_dir on a per-path basis (see the 'paths' config key).
- `Casset::render()` lost its 'min' parameter. Instead, minification can be controlled on a per-group basis from the config file.
- 'combine' option added. Read the readme ("Minification and combining") for details on how to use this with the 'min' option. This addition changes the behaviour of 'min' slighlty, but shouldn't break anything.
- Assets at remote locations are now supported. There are (necessarily) some gotchas, so please read the readme!
- The 'enabled' option in the 'groups' config key is now optional, and defaults to true.
