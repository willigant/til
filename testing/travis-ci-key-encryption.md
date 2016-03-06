# Travis CI key encryption
Recently I wanted to test a module that required an API key and wanted to use
Travis CI to do so. You can use the [Travis CI Client](https://github.com/travis-ci/travis.rb)
to encrypt the key and make it an environment variable for Travis CI to use.

```
travis encrypt 'KEY_NAME_WHICH_WILL_BE_THE_ENV_NAME=someapikeythatyouwanttoprotect' --add
```
This will generate some encrypted hash and the `add` flag will automatically put
this in your Travis CI yml file.

For my use case I needed to use it in a python file, and was able to do so by
```
KEY = os.environ['KEY_NAME_WHICH_WILL_BE_THE_ENV_NAME']
```
