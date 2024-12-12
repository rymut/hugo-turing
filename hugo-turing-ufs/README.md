# Hugo Turing UFS

Module allows for reading / quering HUGO virtual unified file system (UFS).

# Functionality

## file_exists.html

## read_dir.html

# Configuration

Running this module requires dependencies (and own project) to be present in workpath.

## Hugo modules

For cached dependencies this should be done by symlink `_deps/cache` to hugo cache directory or setting enviromental variable `HUGO_CACHEDIR=<workdir>/_cache`

Symlink `_deps/cache` can points directly to hugo cache directory contaiting path `modules/filecache/modules/pkg/mod` or directly to `hugo_cache` directory bellow OS user cache, or `hugo_cache_$USER` directory bellow OS temp directory.

## Hugo workspace modules

Hugo workspace is supported with two caviats: 
1) Workspace file must be set by HUGO_MODULE_WORKSPACE
2) Symlink `_deps/workspace` must be present and pointing to root of hugo workspace (which contains all modules and workspace file)

Project example:

- [some_path/]workspace/
    - hugo.work
    - module1/
        - ...
        - go.mod
        - hugo.toml
    - module2/
        - ...
        - go.mod
        - hugo.toml

- [other_path/]project/
    - ...
    - go.mod
    - _deps/
        - workspace => [some_path]/workspace/

In presented case HUGO_MODULE_WORKSPACE can be set to `[some_path/]workspace/hugo.work` or `[other_path/]project/_deps/workspace/hugo.work`

## Project

For some reason there is small caviat when using in UFS module: `os.FileExists` resolves if file exists in module and not in root of the project
Due to it it is required to create symlink to the project under `_deps/self`

- [some_path/]project
    - hugo.toml
    - go.mod
    - _deps/
        - self/ => symlink to `[some_path/]project`  

### Explanation

- module1/ (uses ufs)
    - layouts/partials/
        - mod1/
            - file_exists.html
            - list_dir_if_exists.html
        - mod2/
            - ...

- project/
    - go.mod (uses module1 mounts only layouts/partials/mod1 => layouts/partials/mod1)
    - hugo.toml
    - layouts/_default/
        - index.html


file_exists.html 
```
{{ $path := . }}
<p>"$path" exists = <strong>{{ os.FileExists $path }}</p>
```
list_dir_if_exists.html list file contents if exists
```
{{ $path := . }}
{{ if os.FileExists $path }}
    {{ $stat := os.Stat $path }}
    {{ if $stat.IsDir }}
        <ul>
        {{ range os.ReadDir $path }}
            <li>{{ .Name }}</li>
        {{ end }}
        </ul>
    {{ end }}
{{ end }}
```

hugo.toml: 
```
[[module.imports]]
    path = "<host>/moduel1"
    [[imports.mounts]]
        source = "layouts/partials/mod1"
        target = "layotus/partials/mod1"
```
index.html calls file_exists.html from module1 as:
```
{{ partial "mod1/exists.html" "layouts/partials/mod1" }}
{{ partial "mod1/exists.html" "layouts/partials/mod2" }}
```

Both will result true 
in both both cases calling list_dir_if_exists.html will result in build error due to directory in question does not existing under `project/`


