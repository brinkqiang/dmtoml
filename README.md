# dmtoml

Copyright (c) 2013-2018 brinkqiang (brink.qiang@gmail.com)

[![dmtoml](https://img.shields.io/badge/brinkqiang-dmtoml-blue.svg?style=flat-square)](https://github.com/brinkqiang/dmtoml)
[![License](https://img.shields.io/badge/license-MIT-brightgreen.svg)](https://github.com/brinkqiang/dmtoml/blob/master/LICENSE)
[![blog](https://img.shields.io/badge/Author-Blog-7AD6FD.svg)](https://brinkqiang.github.io/)
[![Open Source Love](https://badges.frapsoft.com/os/v3/open-source.png)](https://github.com/brinkqiang)
[![GitHub stars](https://img.shields.io/github/stars/brinkqiang/dmtoml.svg?label=Stars)](https://github.com/brinkqiang/dmtoml) 
[![GitHub forks](https://img.shields.io/github/forks/brinkqiang/dmtoml.svg?label=Fork)](https://github.com/brinkqiang/dmtoml)

## Build status
| [Linux][lin-link] | [Mac][mac-link] | [Windows][win-link] |
| :---------------: | :----------------: | :-----------------: |
| ![lin-badge]      | ![mac-badge]       | ![win-badge]        |

[lin-badge]: https://github.com/brinkqiang/dmtoml/workflows/linux/badge.svg "linux build status"
[lin-link]:  https://github.com/brinkqiang/dmtoml/actions/workflows/linux.yml "linux build status"
[mac-badge]: https://github.com/brinkqiang/dmtoml/workflows/mac/badge.svg "mac build status"
[mac-link]:  https://github.com/brinkqiang/dmtoml/actions/workflows/mac.yml "mac build status"
[win-badge]: https://github.com/brinkqiang/dmtoml/workflows/win/badge.svg "win build status"
[win-link]:  https://github.com/brinkqiang/dmtoml/actions/workflows/win.yml "win build status"

## Intro
dmtoml
```cpp


#include <iostream>
#include "dmtoml.h"

int main(int argc, char* argv[])
{
    std::shared_ptr<cpptoml::table> root = cpptoml::make_table();
    root->insert("Integer", 1234L);
    root->insert("Double", 1.234);
    root->insert("String", std::string("ABCD"));

    auto table = cpptoml::make_table();
    table->insert("ElementOne", 1L);
    table->insert("ElementTwo", 2.0);
    table->insert("ElementThree", std::string("THREE"));

    auto nested_table = cpptoml::make_table();
    nested_table->insert("ElementOne", 2L);
    nested_table->insert("ElementTwo", 3.0);
    nested_table->insert("ElementThree", std::string("FOUR"));

    table->insert("Nested", nested_table);

    root->insert("Table", table);

    auto int_array = cpptoml::make_array();
    int_array->push_back(1L);
    int_array->push_back(2L);
    int_array->push_back(3L);
    int_array->push_back(4L);
    int_array->push_back(5L);

    root->insert("IntegerArray", int_array);

    auto double_array = cpptoml::make_array();
    double_array->push_back(1.1);
    double_array->push_back(2.2);
    double_array->push_back(3.3);
    double_array->push_back(4.4);
    double_array->push_back(5.5);

    root->insert("DoubleArray", double_array);

    auto string_array = cpptoml::make_array();
    string_array->push_back(std::string("A"));
    string_array->push_back(std::string("B"));
    string_array->push_back(std::string("C"));
    string_array->push_back(std::string("D"));
    string_array->push_back(std::string("E"));

    root->insert("StringArray", string_array);

    auto table_array = cpptoml::make_table_array();
    table_array->push_back(table);
    table_array->push_back(table);
    table_array->push_back(table);

    root->insert("TableArray", table_array);

    auto array_of_arrays = cpptoml::make_array();
    array_of_arrays->push_back(int_array);
    array_of_arrays->push_back(double_array);
    array_of_arrays->push_back(string_array);

    root->insert("ArrayOfArrays", array_of_arrays);

    std::cout << (*root);
    return 0;
}

```
## Contacts

## Thanks
