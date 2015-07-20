# EntitySupports - Support Build Entity Class

[![Circle CI](https://circleci.com/gh/kr9ly/entity-supports-compiler/tree/master.svg?style=shield)](https://circleci.com/gh/kr9ly/entity-supports-compiler/tree/master)

# Usage

Add this to `repositories` block in your build.gradle

```
maven { url 'http://kr9ly.github.io/maven/' }
```

And Add this to `dependencies` block in your build.gradle

```
compile 'net.kr9ly:entity-supports:0.0.1'
apt 'net.kr9ly:entity-supports-compiler:0.0.1'
```

### Support Annotations

```java
@net.kr9ly.entitysupports.BuilderSupport
@net.kr9ly.entitysupports.EqualsSupport
@net.kr9ly.entitysupports.HashCodeSupport
@net.kr9ly.entitysupports.ToStringSupport
public class Sample {

    public static Sample newInstance() {
        // auto-generated SampleBuilder class
        return SampleBuilder.newBuilder()
            .field1("")
            .field2(0)
            .field3(0d)
            .build();
    }

    String field1;
    
    int field2;
    
    double field3;
    
    @Override
    public boolean equals(Object o) {
        // auto-generated SampleEquals class
        return SampleEquals.equals(this, o);
    }
    
    @Override
    public int hashCode() {
        // auto-generated SampleHashCode class
        return SampleHashCode.hashCode(this);
    }
    
    @Override
    public String toString() {
        // auto-generated SampleToString class
        return SampleToString.toString(this);
    }
}
```

# License

```
Copyright 2015 kr9ly

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```