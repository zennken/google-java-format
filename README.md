# google-java-format

`google-java-format` is a program that reformats Java source code to comply with
[Google Java Style][].

[Google Java Style]: https://google.github.io/styleguide/javaguide.html

## Customization

This repository is a fork of [google/google-java-format](https://github.com/google/google-java-format/) and includes several customizations made for personal purposes.

**Changes to maintain backward compatibility**
- Indentation: 2 → 4 spaces
- Maximum line length: 100 → 120 characters

**New feature**
- --euc-kr option: Enables reading and writing Java files with EUC-KR encoding

## Building from source

```
mvn install -DskipTests
ls ./core/target/google-java-format-HEAD-SNAPSHOT-all-deps.jar
```
## Using the formatter

### From the command-line

```bash
find src -name "*.java" -print0 | xargs -0 java -jar google-java-format-HEAD-SNAPSHOT-all-deps.jar -i [--euc-kr]
```

Options
- -i: replace source code
- --euc-kr: reading and writing Java files with EUC-KR encoding

### From Java code
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
