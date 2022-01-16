# luarocket

luarocket is a script that vendors [Lua rocks][luarocks] into a local project
directory.

[luarocks]: https://luarocks.org/

## Usage

```
usage: luarocket [tree|modules]
```

luarocket utilizes these environment variables:
* `LUA_TREE`: relative path to the local Lua tree directory
* `LUA_MODULES`: relative path to the vendored rocks directory

Rocks to be installed from a remote repository are specified in the
`rock_versions` file in the root of your project directory.
Example:
```
uuid 0.3
enum 0.1.1
```

Rocks can also be built locally from `.rockspec`s in `$LUA_MODULES/.rockspecs`.

Add `$LUA_MODULES` to your Lua package path by including the following in your
Lua file:
```lua
package.path = './lua_modules/?.lua;' .. package.path
```

### Installation

luarocket is easiest to use when included directly in your project directory.
Clone this repository or copy the standalone `luarocket` file.

Ensure these dependencies are satisfied:
* bash
* luarocks
* lua headers (if building rocks locally)

Then:
* invoke it manually
* integrate it into your project's build process

## License

This project is licensed under the MIT License (see [LICENSE](LICENSE)).
