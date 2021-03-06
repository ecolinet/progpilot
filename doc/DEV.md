# Development

## Dependencies

This project would not have been possible without these dependencies :

- [ircmaxell/php-cfg](https://github.com/ircmaxell/php-cfg/)
- [nikic/php-parser](https://github.com/nikic/php-parser/)

## Tests

We are using more than 2400 tests cases from [PHP Vulnerability test suite](https://github.com/stivalet/PHP-Vulnerability-test-suite) for testing our tool.

## License

Progpilot is licensed under the [MIT License](../LICENSE)

## Authors

- Eric Therond | [github](https://github.com/eric-therond/) | [website](https://www.designsecurity.org) | [eric.therond.fr@gmail.com](mailto:eric.therond.fr@gmail.com)

See also the list of [contributors](https://github.com/designsecurity/progpilot/contributors) who participated in this project.

## Roadmap

There is a lot of tasks to do :
- Object heritage
- Passing by reference
- Pushing elements into array (like array[] = ele; or push_array())
- Property of an object is an object
- static property
- definitions on the same line (def = eee; def = aaa;)
- If property hasn't been declared but used later (class { miss public $property;})
- Chained functions calls : $obj->func1()->func2()
- Chained references  : $var = "eee"; $ref1 = &$var; $ref2 = &$ref1;
- Sprintf strings transformations
- No need to new for simplexml_load_file (return $instance) so we miss object creation
- $tainted = $tainted + 0; => cast to int
- Specials rules : missing set_cookies secure or twig default escaping for examples
- Namespace (phpparser example : NsFunccall)
- mysqli_fetch_object (all the properties are tainted : is_object like is_array in the definition of source)
- mysqli style object (will be handled by custom rules : $mysqli = new mysqli; $result = $mysqli->query(); (return of query method of instance mysqli is an object of type ect) $result->fetch_array();)
