bindgen 0.47.0
Generates Rust bindings from C/C++ headers.

USAGE:
    bindgen [FLAGS] [OPTIONS] <header> -- <clang-args>...

FLAGS:
        --block-extern-crate                     Use extern crate instead of use for block.
        --builtins                               Output bindings for builtin definitions, e.g. __builtin_va_list.
        --conservative-inline-namespaces         Conservatively generate inline namespaces to avoid name conflicts.
        --disable-name-namespacing
            Disable namespacing via mangling, causing bindgen to generate names like "Baz" instead of "foo_bar_Baz" for
            an input name "foo::bar::Baz".
        --distrust-clang-mangling                Do not trust the libclang-provided mangling
        --dump-preprocessed-input
            Preprocess and dump the input header files to disk. Useful when debugging bindgen, using C-Reduce, or when
            filing issues. The resulting file will be named something like `__bindgen.i` or `__bindgen.ii`.
        --emit-clang-ast                         Output the Clang AST for debugging purposes.
        --emit-ir                                Output our internal IR for debugging purposes.
        --enable-cxx-namespaces                  Enable support for C++ namespaces.
        --enable-function-attribute-detection
            Enables detecting unexposed attributes in functions (slow).
                                   Used to generate #[must_use] annotations.
        --generate-block                         Generate block signatures instead of void pointers.
        --generate-inline-functions              Generate inline functions.
    -h, --help                                   Prints help information
        --ignore-functions
            Do not generate bindings for functions or methods. This is useful when you only care about struct layouts.

        --ignore-methods                         Do not generate bindings for methods.
        --impl-debug                             Create Debug implementation, if it can not be derived automatically.
        --impl-partialeq
            Create PartialEq implementation, if it can not be derived automatically.

        --no-convert-floats                      Do not automatically convert floats to f32/f64.
        --no-derive-copy                         Avoid deriving Copy on any type.
        --no-derive-debug                        Avoid deriving Debug on any type.
        --no-doc-comments
            Avoid including doc comments in the output, see: https://github.com/rust-lang-nursery/rust-
            bindgen/issues/426
        --no-layout-tests                        Avoid generating layout tests for any type.
        --no-prepend-enum-name                   Do not prepend the enum name to bitfield or constant variants.
        --no-record-matches
            Do not record matching items in the regex sets. This disables reporting of unused items.

        --no-recursive-whitelist
            Disable whitelisting types recursively. This will cause bindgen to emit Rust code that won't compile! See
            the `bindgen::Builder::whitelist_recursively` method's documentation for details.
        --no-rustfmt-bindings                    Do not format the generated bindings with rustfmt.
        --objc-extern-crate                      Use extern crate instead of use for objc.
        --rustfmt-bindings
            Format the generated bindings with rustfmt. DEPRECATED: --rustfmt-bindings is now enabled by default.
            Disable with --no-rustfmt-bindings.
        --time-phases                            Time the different bindgen phases and print to stderr
        --unstable-rust                          Generate unstable Rust code (deprecated; use --rust-target instead).
        --use-core                               Use types from Rust core instead of std.
        --use-msvc-mangling                      MSVC C++ ABI mangling. DEPRECATED: Has no effect.
    -V, --version                                Prints version information
        --verbose                                Print verbose error messages.
        --with-derive-default                    Derive Default on any type.
        --with-derive-eq
            Derive eq on any type. Enable this option also enables --with-derive-partialeq

        --with-derive-hash                       Derive hash on any type.
        --with-derive-ord
            Derive ord on any type. Enable this option also enables --with-derive-partialord

        --with-derive-partialeq                  Derive partialeq on any type.
        --with-derive-partialord                 Derive partialord on any type.

OPTIONS:
        --bitfield-enum <regex>...             Mark any enum whose name matches <regex> as a set of bitfield flags.
        --blacklist-function <function>...     Mark <function> as hidden.
        --blacklist-item <item>...             Mark <item> as hidden.
        --blacklist-type <type>...             Mark <type> as hidden.
        --constified-enum <regex>...           Mark any enum whose name matches <regex> as a series of constants.
        --constified-enum-module <regex>...    Mark any enum whose name matches <regex> as a module of constants.
        --ctypes-prefix <prefix>               Use the given prefix before raw types instead of ::std::os::raw.
        --default-enum-style <variant>         The default style of code used to generate enums. [default: consts]
                                               [possible values: consts, moduleconsts, bitfield, rust]
        --emit-ir-graphviz <path>              Dump graphviz dot file.
        --generate <generate>                  Generate only given items, split by commas. Valid values are
                                               "functions","types", "vars", "methods", "constructors" and "destructors".
        --no-copy <regex>...                   Avoid deriving Copy for types matching <regex>.
        --no-hash <regex>...                   Avoid deriving Hash for types matching <regex>.
        --no-partialeq <regex>...              Avoid deriving PartialEq for types matching <regex>.
        --opaque-type <type>...                Mark <type> as opaque.
    -o, --output <output>                      Write Rust bindings to <output>.
        --raw-line <raw-line>...               Add a raw line of Rust code at the beginning of output.
        --rust-target <rust-target>            Version of the Rust compiler to target. Valid options are: ["1.0",
                                               "1.19", "1.20", "1.21", "1.25", "1.26", "1.27", "1.28", "1.33",
                                               "nightly"]. Defaults to "1.21".
        --rustfmt-configuration-file <path>    The absolute path to the rustfmt configuration file. The configuration
                                               file will be used for formatting the bindings. This parameter is
                                               incompatible with --no-rustfmt-bindings.
        --rustified-enum <regex>...            Mark any enum whose name matches <regex> as a Rust enum.
        --whitelist-function <regex>...        Whitelist all the free-standing functions matching <regex>. Other non-
                                               whitelisted functions will not be generated.
        --whitelist-type <regex>...            Only generate types matching <regex>. Other non-whitelisted types will
                                               not be generated.
        --whitelist-var <regex>...             Whitelist all the free-standing variables matching <regex>. Other non-
                                               whitelisted variables will not be generated.

ARGS:
    <header>           C or C++ header file
    <clang-args>...    
