# Pkl Tools

Some helpful tools for use across all of our Pkl projects. Currently there is only a single tool, [StaticCode](staticcode/), a renderer that generates Swift or Kotlin code with values directly inline within the code (in contrast to pkl-swift and pkl-codegen-kotlin which load the values in at runtime from a .pkl file).

## Usage

The tools in this repo are available as Pkl packages in the following format: `"package://pkg.pkl-lang.org/github.com/element-hq/pkl-tools/<NAME>@<VERSION>`. This can be imported directly into a Pkl file:

```pkl
import "package://pkg.pkl-lang.org/github.com/element-hq/pkl-tools/staticcode@1.0.0#/StaticCode.pkl"
```

Or within a project:

```pkl
amends "pkl:Project"

dependencies {
  ["staticcode"] { uri = "package://pkg.pkl-lang.org/github.com/element-hq/pkl-tools/staticcode@1.0.0" }
}
```

## Releasing

Instructions to make a new release of a package can be found in the [release](release/) directory.
