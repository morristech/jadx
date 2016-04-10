> This is a fork of [**skylot/jadx**](https://github.com/skylot/jadx) that has been modified to be used in [**Show Java**](https://github.com/niranjan94-show-java) - a java decompiler for android. If you're searching for jadx, i suggest you head over to [github.com/skylot/jadx](<https://github.com/skylot/jadx>).

#### JADX (modified for use with Show Java)

JADX is a Dex to Java decompiler

Command line and GUI tools for produce Java source code from Android Dex and Apk files


#### Building from source
    git clone https://github.com/niranjan94/jadx.git
    cd jadx
    ./gradlew dist

(on Windows, use `gradlew.bat` instead of `./gradlew`)

Scripts for run jadx will be placed in `build/jadx/bin`
and also packed to `build/jadx-<version>.zip`


#### Run
Run **jadx** on itself:

    cd build/jadx/
    bin/jadx -d out lib/jadx-core-*.jar
    #or
    bin/jadx-gui lib/jadx-core-*.jar


#### Usage
```
jadx[-gui] [options] <input file> (.dex, .apk, .jar or .class)
options:
 -d, --output-dir           - output directory
 -j, --threads-count        - processing threads count
 -r, --no-res               - do not decode resources
 -s, --no-src               - do not decompile source code
 -e, --export-gradle        - save as android gradle project
     --show-bad-code        - show inconsistent code (incorrectly decompiled)
     --no-replace-consts    - don't replace constant value with matching constant field
     --escape-unicode       - escape non latin characters in strings (with \u)
     --deobf                - activate deobfuscation
     --deobf-min            - min length of name
     --deobf-max            - max length of name
     --deobf-rewrite-cfg    - force to save deobfuscation map
     --deobf-use-sourcename - use source file name as class name alias
     --cfg                  - save methods control flow graph to dot file
     --raw-cfg              - save methods control flow graph (use raw instructions)
 -f, --fallback             - make simple dump (using goto instead of 'if', 'for', etc)
 -v, --verbose              - verbose output
 -h, --help                 - print this help
Example:
 jadx -d out classes.dex
```

#### Troubleshooting
##### Out of memory error:
  - Reduce processing threads count (`-j` option)
  - Increase maximum java heap size:
    * command line (example for linux):
      `JAVA_OPTS="-Xmx4G" jadx -j 1 some.apk`
    * edit 'jadx' script (jadx.bat on Windows) and setup bigger heap size:
      `DEFAULT_JVM_OPTS="-Xmx2500M"`


---------------------------------------
```
Licensed under the Apache 2.0 License
Copyright 2015 by Skylot
```

```
Modifications by Niranjan
````