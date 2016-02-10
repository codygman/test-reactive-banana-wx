attempting to install reactive-banana-wx with stack

First I encountered this error:

```
       Could not find module ‘Distribution.MacOSX’
        Perhaps you meant
          Distribution.Make (from Cabal-1.22.5.0@Cabal_3ux67khMI118y6VpwrFnXN)
          Distribution.Make (needs flag -package-key Cabal-1.22.7.0@Cabal_FnleEOdguiYCYHtwjcyeKE)
          Distribution.GetOpt
        Use -v to see a list of the files searched for.
```

and found [a solution](https://github.com/commercialhaskell/stack/issues/1316#issuecomment-157629954) that instructed me to add this to my stack.yaml:

```
explicit-setup-deps:
    "reactive-banana-wx": true
    entropy: false
```

After I tried another stack build:

```
test-reactive-banana-wx:master* λ stack build 
reactive-banana-wx-1.1.0.0: configure
Progress: 1/2
--  While building package reactive-banana-wx-1.1.0.0 using:
      /home/cody/.stack/programs/x86_64-linux/ghc-7.10.3/bin/ghc --make -odir /tmp/stack11571/reactive-banana-wx-1.1.0.0/.stack-work/dist/x86_64-linux/Cabal-1.22.5.0/setup -hidir /tmp/stack11571/reactive-banana-wx-1.1.0.0/.stack-work/dist/x86_64-linux/Cabal-1.22.5.0/setup -i -i. -clear-package-db -global-package-db -package-db=/home/cody/.stack/snapshots/x86_64-linux/lts-5.2/7.10.3/pkgdb -package-db=/home/cody/test-reactive-banana-wx/.stack-work/install/x86_64-linux/lts-5.2/7.10.3/pkgdb -hide-all-packages -package=Cabal-1.22.5.0 -package-id=array-0.5.1.0-960bf9ae8875cc30355e086f8853a049 -package-id=base-4.8.2.0-0d6d1084fbc041e1cded9228e80e264d -package-id=bin-package-db-0.0.0.0-b99ff8351e6cad51a902f741b5afedb7 -package-id=binary-0.7.5.0-5784fd031a720c3b84e73006e444c7ca -package-id=bytestring-0.10.6.0-c60f4c543b22c7f7293a06ae48820437 -package-id=cabal-macosx-0.2.3.4-6b74c70a3c280c0115cbedb8aecacfb5 -package-id=containers-0.5.6.2-e59c9b78d840fa743d4169d4bea15592 -package-id=deepseq-1.4.1.1-614b63b36dd6e29d2b35afff57c25311 -package-id=directory-1.2.2.0-f8e14a9d121b76a00a0f669ee724a732 -package-id=filepath-1.4.0.0-f97d1e4aebfd7a03be6980454fe31d6e -package-id=ghc-prim-0.4.0.0-6cdc86811872333585fa98756aa7c51e -package-id=haskeline-0.7.2.1-ee66b80ab55ef13718feae46e4940f5d -package-id=hoopl-3.10.0.2-0f19d8f452f19e2befbe96868260767a -package-id=hpc-0.6.0.2-0ad027f63b3708216688ed6c3f70c62d -package-id=integer-gmp-1.0.0.0-3c8c40657a9870f5c33be17496806d8d -package-id=pretty-1.1.2.0-5cc412214ea63f61ee84c4fbabdbe0ec -package-id=process-1.2.3.0-78f206acb2330ea8066c6c19c87356f0 -package-id=reactive-banana-1.1.0.0-2c4674b67b4d86bcfae7cf1ee96e6f3f -package-id=template-haskell-2.10.0.0-3c4cb52230f347282af9b2817f013181 -package-id=terminfo-0.4.0.1-ff5b3d5838955b7711e16ccc720f06f4 -package-id=time-1.5.0.1-edbd1a50e7922b396ada189ab8e8523b -package-id=transformers-0.4.2.0-81450cd8f86b36eaa8fa0cbaf6efc3a3 -package-id=unix-2.7.1.0-343d4f566f30113da92e819f4a148640 -package-id=wx-0.92.2.0-3624885c0a63caf909846ff6b1900e2f -package-id=wxcore-0.92.2.0-c1c2229782d9c4b04aed9b823ca8d901 -package-id=xhtml-3000.2.1-e005917157f780654d68110616d034e8 /tmp/stack11571/reactive-banana-wx-1.1.0.0/Setup.hs -o /tmp/stack11571/reactive-banana-wx-1.1.0.0/.stack-work/dist/x86_64-linux/Cabal-1.22.5.0/setup/setup
    Process exited with code: ExitFailure 1
    Logs have been written to: /home/cody/test-reactive-banana-wx/.stack-work/logs/reactive-banana-wx-1.1.0.0.log

    [1 of 1] Compiling Main             ( /tmp/stack11571/reactive-banana-wx-1.1.0.0/Setup.hs, /tmp/stack11571/reactive-banana-wx-1.1.0.0/.stack-work/dist/x86_64-linux/Cabal-1.22.5.0/setup/Main.o )
    
    /tmp/stack11571/reactive-banana-wx-1.1.0.0/Setup.hs:11:19:
        Couldn't match type ‘LocalBuildInfo’
                       with ‘Cabal-1.22.7.0:Distribution.Simple.LocalBuildInfo.LocalBuildInfo’
        NB: ‘LocalBuildInfo’
              is defined in ‘Distribution.Simple.LocalBuildInfo’
                  in package ‘Cabal-1.22.5.0’
            ‘Cabal-1.22.7.0:Distribution.Simple.LocalBuildInfo.LocalBuildInfo’
              is defined in ‘Distribution.Simple.LocalBuildInfo’
                  in package ‘Cabal-1.22.7.0’
        Expected type: Args
                       -> Distribution.Simple.Setup.BuildFlags
                       -> Distribution.PackageDescription.PackageDescription
                       -> LocalBuildInfo
                       -> IO ()
          Actual type: [String]
                       -> Cabal-1.22.7.0:Distribution.Simple.Setup.BuildFlags
                       -> Cabal-1.22.7.0:Distribution.PackageDescription.PackageDescription
                       -> Cabal-1.22.7.0:Distribution.Simple.LocalBuildInfo.LocalBuildInfo
                       -> IO ()
        In the ‘postBuild’ field of a record
        In the second argument of ‘($)’, namely
          ‘simpleUserHooks {postBuild = myPostBuild}’
```

Maybe I can specify to use Cabal-1.22.7.0 in my stack.yaml. I make this change and run again:

```
test-reactive-banana-wx:master* λ stack build 
cabal-macosx-0.2.3.4: unregistering
Cabal-1.22.7.0: configure
Cabal-1.22.7.0: build
Cabal-1.22.7.0: copy/register
cabal-macosx-0.2.3.4: configure
cabal-macosx-0.2.3.4: build
cabal-macosx-0.2.3.4: copy/register
reactive-banana-wx-1.1.0.0: configure
Progress: 3/4
--  While building package reactive-banana-wx-1.1.0.0 using:
      /home/cody/.stack/programs/x86_64-linux/ghc-7.10.3/bin/ghc --make -odir /tmp/stack11817/reactive-banana-wx-1.1.0.0/.stack-work/dist/x86_64-linux/Cabal-1.22.5.0/setup -hidir /tmp/stack11817/reactive-banana-wx-1.1.0.0/.stack-work/dist/x86_64-linux/Cabal-1.22.5.0/setup -i -i. -clear-package-db -global-package-db -package-db=/home/cody/.stack/snapshots/x86_64-linux/lts-5.2/7.10.3/pkgdb -package-db=/home/cody/test-reactive-banana-wx/.stack-work/install/x86_64-linux/lts-5.2/7.10.3/pkgdb -hide-all-packages -package=Cabal-1.22.5.0 -package-id=array-0.5.1.0-960bf9ae8875cc30355e086f8853a049 -package-id=base-4.8.2.0-0d6d1084fbc041e1cded9228e80e264d -package-id=bin-package-db-0.0.0.0-b99ff8351e6cad51a902f741b5afedb7 -package-id=binary-0.7.5.0-5784fd031a720c3b84e73006e444c7ca -package-id=bytestring-0.10.6.0-c60f4c543b22c7f7293a06ae48820437 -package-id=cabal-macosx-0.2.3.4-6b74c70a3c280c0115cbedb8aecacfb5 -package-id=containers-0.5.6.2-e59c9b78d840fa743d4169d4bea15592 -package-id=deepseq-1.4.1.1-614b63b36dd6e29d2b35afff57c25311 -package-id=directory-1.2.2.0-f8e14a9d121b76a00a0f669ee724a732 -package-id=filepath-1.4.0.0-f97d1e4aebfd7a03be6980454fe31d6e -package-id=ghc-prim-0.4.0.0-6cdc86811872333585fa98756aa7c51e -package-id=haskeline-0.7.2.1-ee66b80ab55ef13718feae46e4940f5d -package-id=hoopl-3.10.0.2-0f19d8f452f19e2befbe96868260767a -package-id=hpc-0.6.0.2-0ad027f63b3708216688ed6c3f70c62d -package-id=integer-gmp-1.0.0.0-3c8c40657a9870f5c33be17496806d8d -package-id=pretty-1.1.2.0-5cc412214ea63f61ee84c4fbabdbe0ec -package-id=process-1.2.3.0-78f206acb2330ea8066c6c19c87356f0 -package-id=reactive-banana-1.1.0.0-2c4674b67b4d86bcfae7cf1ee96e6f3f -package-id=template-haskell-2.10.0.0-3c4cb52230f347282af9b2817f013181 -package-id=terminfo-0.4.0.1-ff5b3d5838955b7711e16ccc720f06f4 -package-id=time-1.5.0.1-edbd1a50e7922b396ada189ab8e8523b -package-id=transformers-0.4.2.0-81450cd8f86b36eaa8fa0cbaf6efc3a3 -package-id=unix-2.7.1.0-343d4f566f30113da92e819f4a148640 -package-id=wx-0.92.2.0-3624885c0a63caf909846ff6b1900e2f -package-id=wxcore-0.92.2.0-c1c2229782d9c4b04aed9b823ca8d901 -package-id=xhtml-3000.2.1-e005917157f780654d68110616d034e8 /tmp/stack11817/reactive-banana-wx-1.1.0.0/Setup.hs -o /tmp/stack11817/reactive-banana-wx-1.1.0.0/.stack-work/dist/x86_64-linux/Cabal-1.22.5.0/setup/setup
    Process exited with code: ExitFailure 1
    Logs have been written to: /home/cody/test-reactive-banana-wx/.stack-work/logs/reactive-banana-wx-1.1.0.0.log

    [1 of 1] Compiling Main             ( /tmp/stack11817/reactive-banana-wx-1.1.0.0/Setup.hs, /tmp/stack11817/reactive-banana-wx-1.1.0.0/.stack-work/dist/x86_64-linux/Cabal-1.22.5.0/setup/Main.o )
    
    /tmp/stack11817/reactive-banana-wx-1.1.0.0/Setup.hs:11:19:
        Couldn't match type ‘LocalBuildInfo’
                       with ‘Cabal-1.22.7.0:Distribution.Simple.LocalBuildInfo.LocalBuildInfo’
        NB: ‘LocalBuildInfo’
              is defined in ‘Distribution.Simple.LocalBuildInfo’
                  in package ‘Cabal-1.22.5.0’
            ‘Cabal-1.22.7.0:Distribution.Simple.LocalBuildInfo.LocalBuildInfo’
              is defined in ‘Distribution.Simple.LocalBuildInfo’
                  in package ‘Cabal-1.22.7.0’
        Expected type: Args
                       -> Distribution.Simple.Setup.BuildFlags
                       -> Distribution.PackageDescription.PackageDescription
                       -> LocalBuildInfo
                       -> IO ()
          Actual type: [String]
                       -> Cabal-1.22.7.0:Distribution.Simple.Setup.BuildFlags
                       -> Cabal-1.22.7.0:Distribution.PackageDescription.PackageDescription
                       -> Cabal-1.22.7.0:Distribution.Simple.LocalBuildInfo.LocalBuildInfo
                       -> IO ()
        In the ‘postBuild’ field of a record
        In the second argument of ‘($)’, namely
          ‘simpleUserHooks {postBuild = myPostBuild}’
```
