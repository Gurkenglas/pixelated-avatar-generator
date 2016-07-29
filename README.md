# Pixelated Avatar Generator [![Travis CI Status](https://api.travis-ci.org/ExcaliburZero/pixelated-avatar-generator.svg)](https://travis-ci.org/ExcaliburZero/pixelated-avatar-generator) [![Coverage Status](https://coveralls.io/repos/github/ExcaliburZero/pixelated-avatar-generator/badge.svg?branch=master)](https://coveralls.io/github/ExcaliburZero/pixelated-avatar-generator?branch=master)
Pixelated Avatar Generator is a Haskell library and application for generating pixelated avatar images from seed values.

```haskell
import Graphics.Avatars.Pixelated

createAndSaveAvatar :: String -> FilePath -> IO ()
createAndSaveAvatar s path = saveAvatar avatar path
  where avatar = scaleAvatar 32 $ generateAvatar seed
        seed   = createSeed s
```

![Some examples of avatars generated by the library.](example_image.png)

## Library
Pixelated Avatar Generator is a library which provides functions and data types for generating, altering, and saving pixelated avatars.

For information on how to use the library, see the documentation for the [`Graphics.Avatars.Pixelated`](https://hackage.haskell.org/package/pixelated-avatar-generator/docs/Graphics-Avatars-Pixelated.html) module.

### Documentation
The documentation for the latest release of the library can be found in [the library's Hackage entry](https://hackage.haskell.org/package/pixelated-avatar-generator).

Documentation of the development versions of the library can be generated by running the following command in the main directory of the project:

```
$ stack haddock
```

The generated html documentation can then be found in the following directory:

```
.stack-work/dist/x86_64-linux/Cabal-1.22.5.0/doc
```

## Executable
An executable program for generating avatar image files is also provided. It can generate several avatar images concurrently to given file locations.

The executable can be installed along with the library by running the following command:

```
$ stack install pixelated-avatar-generator
```

The executable can then by run by calling it with the desired filepath(s) of the output file(s) including the `.png` extension.

```
$ pixelated-avatar-generator image1.png image2.png
Successfully created 2 avatars.
```

By default, the avatars are at a size of 256x256px. Though the size can be changed by using a custom scaling factor via the `--scaling-factor` flag.

### Usage
```
Usage: pixelated-avatar-generator FILEPATH_1 [FILEPATH_2] [FILEPATH_3] ...

FILEPATH_(1...)   -- The locations to save generated avatars at. "img/test.png"

Options:

     --scaling-factor
         Use a custom scaling factor. The scaling factor is multiplied by 8 to
         get the dimensions of the image. For example, a scaling factor of 4
         would yield a 32x32px image. The default scaling factor is 32.
```

## Links
* [Pixelated Avatar Generator package on Hackage](https://hackage.haskell.org/package/pixelated-avatar-generator)

## License
The source code of Pixelated Avatar Generator is available under the [MIT license](https://opensource.org/licenses/MIT), see `LICENSE` for more information.
