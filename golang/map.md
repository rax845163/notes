

## Key Types

Map keys may be of any type that is comparable. The [language spec](https://golang.org/ref/spec#Comparison_operators) defines this precisely, but in short, comparable types are boolean, numeric, string, pointer, channel, and interface types, and structs or arrays that contain only those types. Notably absent from the list are slices, maps, and functions; these types cannot be compared using ==, and may not be used as map keys.