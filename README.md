# grunt-base
Base setup for build-first workflow using Grunt as the build tool.

* Preconfigured `package.json` file.  Use npm install to install all the 
  dependencies.

* Dependencies installed includes...

    `babel-cli`, our main transpiling tool convert es6 code to es5 compatible code.
    Allows us to use the command `babel -o output.file input.file`. This is a local
    install of the cli tools, which means access to the command is either done 
    through ./node_modules/.bin/babel[-][xxx] or through the scripts defined 
    inside package.json.

    `babel-plugin-transform-runtime`, used to give babel access to external helpers
    and libraries that ultimately makes up the es6 environment. This is use in
    conjunction with `babel-runtime`.  Think of this transform plugin as the 
    enabler of the actual runtime(`babel-runtime`).  We enable babel to use this
    plugin by specifying the `plugins` property in the `.babelrc` file.

    `babel-preset-es2015`, a set of transformations to be applied when babel is
    run. Like the transform-runtime plugin, it is enabled through the `.babelrd`
    file under the `presets` key.

    `eslint, eslint-config-standard etc,,`, linting service. `eslint-config-
    standard` contains a set of predefined linting rules targeted at es6 development.

    `grunt, grunt-contrib-*`, local install of Grunt, `grunt-cli` assumed to be
    installed globally(via npm install -g grunt-cli).

*  There is a `./bootstrap.sh` script, which when executed will create 2 
   directories: `src` and `build`.

