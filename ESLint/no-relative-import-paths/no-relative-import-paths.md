Pattern: Relative import path

Issue: -

## Description

Moving a file to different folder, could result in changing all imports statement in that file. This will not happen is the import paths are absolute. The eslint rule helps enforcing having absolute import paths.

## Further Reading

* [GitHub - no-relative-import-paths](https://github.com/MelvinVermeer/eslint-plugin-no-relative-import-paths)