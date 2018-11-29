slug
====

This is fork of [slug][https://github.com/gosimple/slug] package.

This is fork has had a few improvements from the original slug package such as:

* Added new private constants to setting of default language and word separator of slug 
* Extended MakeLang function. Now you can set word separator of slug as parameter of function
* Extended body of Make function for comply new descriptor of MakeLag function

Package `slug` generate slug from unicode string, URL-friendly slugify with
multiple languages support.

## Example

```go
package main

import (
	"fmt"
	"github.com/sidmal/slug"
)

func main() {
	text := slug.Make("Hellö Wörld хелло ворлд")
	fmt.Println(text) // Will print: "hello_world_khello_vorld"

	enText := slug.MakeLang("This & that", "en", "*")
	fmt.Println(enText) // Will print: "this*and*that"

	slug.CustomSub = map[string]string{
		"water": "sand",
	}
	textSub := slug.Make("water is hot")
	fmt.Println(textSub) // Will print: "sand_is_hot"
}

```

## How install
```sh
go get -u github.com/sidmal/slug
```

## License

License of original package you can find by this [link][https://github.com/gosimple/slug/blob/master/LICENSE]