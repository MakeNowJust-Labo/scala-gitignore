# scala-gitignore

> [`.gitignore`](https://git-scm.com/docs/gitignore) file traverse algorithm implementation.

## Example

```scala
scala> import java.nio.file.Path, codes.quine.labo.gitignore._
import java.nio.file.Path
import codes.quine.labo.gitignore._

scala> {
     |   val list = List.newBuilder[String]
     |   GitIgnore.traverse(Path.of("project")) { path =>
     |     list.addOne(Path.of("").toAbsolutePath.relativize(path).toString)
     |   }
     |   list.result()
     | }
res0: List[String] = List(project/build.properties, project/plugin.sbt)
```

## Features

  - Nested `.gitignore` is supported.
  - Complex glob syntax works.
  - Ignore filenames can be customized.

## License

MIT License.

2020 (C) TSUYUSATO "MakeNowJust" Kitsune
