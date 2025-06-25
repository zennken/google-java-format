# google-java-format

`google-java-format` is a program that reformats Java source code to comply with
[Google Java Style][].

[Google Java Style]: https://google.github.io/styleguide/javaguide.html

## Customization

To maintain backward compatibility, some customizations have been applied:

Changes
1. Indentation: 2 → 4 spaces
2. Maximum line length: 100 → 120 characters

New
1. --euc-kr option: Enables reading and writing Java files with EUC-KR encoding

## Using the formatter

### From the command-line

[Download the formatter](https://github.com/google/google-java-format/releases)
and run it with:

```
java -jar /path/to/google-java-format-${GJF_VERSION?}-all-deps.jar <options> [files...]
```

Options
- -i: Replace source code
- --euc-kr

***Note:*** *There is no configurability as to the formatter's algorithm for
formatting. This is a deliberate design decision to unify our code formatting on
a single format.*

```java
String formattedSource = new Formatter().formatSource(sourceString);
```

or

```java
CharSource source = ...
CharSink output = ...
new Formatter().formatSource(source, output);
```

Your starting point should be the instance methods of
`com.google.googlejavaformat.java.Formatter`.

## Building from source

```
mvn install -DskipTests
ls ./core/target/google-java-format-HEAD-SNAPSHOT-all-deps.jar
```

## Contributing

Please see [the contributors guide](CONTRIBUTING.md) for details.

## License

```text
Licensed under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License. You may obtain a copy of
the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
License for the specific language governing permissions and limitations under
the License.
```
