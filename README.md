# mies-node-template

A minimal ClojureScript Node.js template.

## Usage

Run the following to create a project and start auto building.

```
lein new mies-node hello-world
cd hello-world
lein npm install
lein cljsbuild auto
```

Changes to your source files will trigger incremental compilation. To
run your code use the provided loader file in the project directory:

```
node run.js
```

If you would like your program to run upon build completion you can
change your build settings to look like the following:

```clojure
{:id "hello-world"
 :source-paths ["src"]
 :notify-command ["node" "run.js"] ;; << ADD THIS
 :compiler {
   :output-to "out/hello_world.js"
   :output-dir "out"
   :target :nodejs
   :optimizations :none
   :source-map true}}
```

To get source map support simply run the following in your project directory:

```
npm install source-map-support
```

`node run.js` will automatically load source map support for
you and you will get accurate stack traces.

## License

Copyright © 2014 David Nolen

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
