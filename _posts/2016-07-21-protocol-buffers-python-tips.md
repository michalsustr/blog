---
layout: single
title: Protocol buffers - python tips
created: 2016-07-21
categories:
- python
---
[Protocol buffers](https://developers.google.com/protocol-buffers/) (protobufs) are well known Google's mechanism for a language-neutral, platform-neutral, extensible mean for serializing structured data.

Basically, it's exchange format that is smaller than JSON/XML/whatever because it is saved in binary. And you can use code generators to make it very simple to use it in different languages.

To make it to work quickly, just get the binary release from [official relases](https://github.com/google/protobuf/releases) and put the `protoc` command to `/usr/bin/protoc`. Once you write your own .proto spec file, like [the addressbook in examples](https://github.com/google/protobuf/blob/master/examples/addressbook.proto) you can compile it with

```
$ protoc --python_out=. *.proto
```

The docs for how to create the .proto specs are well documented on their website, so no need to explain it here. Maybe just a few things to keep in mind when you write your protocol headers:

Extending protobufs:
- you must not change the tag numbers of any existing fields.
- you must not add or delete any required fields.
- you may delete optional or repeated fields.
- you may add new optional or repeated fields but you must use fresh tag numbers (i.e. tag numbers that were never used in this protocol buffer, not even by deleted fields).

Currently there are two active versions:

- [proto2](https://developers.google.com/protocol-buffers/docs/proto2)
- [proto3](https://developers.google.com/protocol-buffers/docs/proto2)

The **proto2** version is still actively supported, probably mainly because I find the **proto3** kind of *sucks* :-) (one thing I didn't like it doesn't have support for *default values*. As it turns out, [I'm not the only one who doesn't like it](https://groups.google.com/forum/#!topic/protobuf/ZRpcfmeGK6s) but [it has reasons](https://stackoverflow.com/questions/33222551/why-are-there-no-custom-default-values-in-proto3) ).

In python I struggled for an hour to find a way how to create human readable .prototxt files. All you have to do is (extending the python examples [add_person.py](https://github.com/google/protobuf/blob/master/examples/add_person.py) and [list_people.p](https://github.com/google/protobuf/blob/master/examples/list_people.py) )

```python
# import this
from google.protobuf import text_format
# and then use this to read
text_format.Parse(f.read(), address_book)
# and this to write
text_format.MessageToString(address_book)
```

Enjoy.


