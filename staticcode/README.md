# StaticCode

A Pkl renderer that generates Swift or Kotlin code with values directly inline within the code. This is in contrast to [pkl-swift](https://github.com/apple/pkl-swift) and [pkl-codegen-kotlin](https://pkl-lang.org/main/current/kotlin-binding/codegen.html), both of which generate the types but load the values at runtime, requiring the pkl files to be distributed with the application.

## Basic Usage

Import the package into a file and set it as the output renderer:

**App.pkl**

```pkl
import "package://pkg.pkl-lang.org/github.com/element-hq/pkl-tools/staticcode@1.0.0#/StaticCode.pkl"

name = "Element"
tag: String? = null

metadata = new Metadata {
  version = "2.0.0"
  websiteURL = "https://element.io"
}

output {
  renderer = new StaticCode.Renderer {
    language = "Swift"
    objectName = "AppConfiguration"
  }
}
```

or for Kotlin

```pkl
…

output {
  renderer = new StaticCode.Renderer {
    language = "Kotlin"
    package = "io.element.App"
    objectName = "AppConfiguration"
  }
}
```

Evaluating the file will render your code:

```shell
~ ❯ pkl eval App.pkl 
enum AppConfiguration {
    static let name: String = "Element"
    static let tag: String? = nil
    static let metadata: Metadata = Metadata(
        version: "2.0.0",
        websiteURL: "https://element.io"
    )
    struct Metadata {
        let version: String
        let websiteURL: String
    }
}
```
