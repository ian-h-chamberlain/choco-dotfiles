# Custom chocolatey packages to be hosted on GH

Build + publish steps:

1. (Maybe) `choco apikey add` to avoid passing --api-key every time
1. `choco pack` (outputs a file like `testpkg.0.1.0.nupkg`)
1. `choco push --api-key=$TOKEN --source=https://nuget.pkg.github.com/ian-h-chamberlain/index.json ./testpkg.0.1.0.nupkg`
    TODO: maybe can add a shortcut for the source here idk

Pull / install from source

1. `choco source add --user=ian-h-chamberlain --password=$TOKEN --name=github --source=https://nuget.pkg.github.com/ian-h-chamberlain/index.json`
   Not sure if user/password are actually needed here?
1. `choco install` or `search` or whatever
