attempting to install reactive-banana-wx with stack

```
~ λ stack new test-reactive-banana-wx --resolver lts-5.2
Downloading template "new-template" to create project "test-reactive-banana-wx" in test-reactive-banana-wx/ ...
The following parameters were needed by the template but not provided: author-email, author-name, category, copyright, github-username
You can provide them in /home/cody/.stack/config.yaml, like this:
templates:
  params:
    author-email: value
    author-name: value
    category: value
    copyright: value
    github-username: value
Or you can pass each one as parameters like this:
stack new test-reactive-banana-wx new-template -p "author-email:value" -p "author-name:value" -p "category:value" -p "copyright:value" -p "github-username:value"
Using cabal packages:
- test-reactive-banana-wx/test-reactive-banana-wx.cabal

Initialising configuration using resolver: lts-5.2
Writing configuration to file: test-reactive-banana-wx/stack.yaml
All done.
test-reactive-banana-wx λ stack solver --update-config 
Using configuration file: stack.yaml
Using cabal packages:
- test-reactive-banana-wx.cabal

Using resolver: lts-5.2
Using compiler: ghc-7.10.3
Asking cabal to calculate a build plan...
Trying with packages from lts-5.2 as hard constraints...
Successfully determined a build plan with 8 external dependencies.

The following changes will be made to stack.yaml:
* Resolver is lts-5.2
* Dependencies to be added
    extra-deps:
    - cabal-macosx-0.2.3.4
    - reactive-banana-1.1.0.0
    - reactive-banana-wx-1.1.0.0
    - text-1.2.2.0
    - wx-0.92.2.0
    - wxc-0.92.2.0
    - wxcore-0.92.2.0
    - wxdirect-0.92.2.0

Updated stack.yaml
test-reactive-banana-wx λ stack build 
text-1.2.2.0: configure
text-1.2.2.0: build
text-1.2.2.0: copy/register
parsec-3.1.9: configure
parsec-3.1.9: build
hashable-1.2.4.0: configure
hashable-1.2.4.0: build
ashable-1.2.4.0: copy/register
unordered-containers-0.2.5.1: configure
unordered-containers-0.2.5.1: build
parsec-3.1.9: copy/register
wxdirect-0.92.2.0: configure
wxdirect-0.92.2.0: build
cabal-macosx-0.2.3.4: configure
cabal-macosx-0.2.3.4: build
cabal-macosx-0.2.3.4: copy/register
unordered-containers-0.2.5.1: copy/register
vault-0.3.0.5: configure
vault-0.3.0.5: build
wxdirect-0.92.2.0: copy/register
wxc-0.92.2.0: configure
vault-0.3.0.5: copy/register
wxc-0.92.2.0: build
reactive-banana-1.1.0.0: configure
reactive-banana-1.1.0.0: build
reactive-banana-1.1.0.0: copy/register
wxc-0.92.2.0: copy/register
wxcore-0.92.2.0: configure
wxcore-0.92.2.0: build
wxcore-0.92.2.0: copy/register
wx-0.92.2.0: configure
wx-0.92.2.0: build
wx-0.92.2.0: copy/register
reactive-banana-wx-1.1.0.0: configure
Progress: 12/13
--  While building package reactive-banana-wx-1.1.0.0 using:
      /home/cody/.stack/programs/x86_64-linux/ghc-7.10.3/bin/ghc --make -odir /tmp/stack7801/reactive-banana-wx-1.1.0.0/.stack-work/dist/x86_64-linux/Cabal-1.22.5.0/setup -hidir /tmp/stack7801/reactive-banana-wx-1.1.0.0/.stack-work/dist/x86_64-linux/Cabal-1.22.5.0/setup -i -i. -package=Cabal-1.22.5.0 -clear-package-db -global-package-db -package-db=/home/cody/.stack/snapshots/x86_64-linux/lts-5.2/7.10.3/pkgdb /tmp/stack7801/reactive-banana-wx-1.1.0.0/Setup.hs -o /tmp/stack7801/reactive-banana-wx-1.1.0.0/.stack-work/dist/x86_64-linux/Cabal-1.22.5.0/setup/setup
    Process exited with code: ExitFailure 1
    Logs have been written to: /home/cody/test-reactive-banana-wx/.stack-work/logs/reactive-banana-wx-1.1.0.0.log

    
    /tmp/stack7801/reactive-banana-wx-1.1.0.0/Setup.hs:5:8:
        Could not find module ‘Distribution.MacOSX’
        Perhaps you meant
          Distribution.Make (from Cabal-1.22.5.0@Cabal_3ux67khMI118y6VpwrFnXN)
          Distribution.Make (needs flag -package-key Cabal-1.22.7.0@Cabal_FnleEOdguiYCYHtwjcyeKE)
          Distribution.GetOpt
        Use -v to see a list of the files searched for.
```
