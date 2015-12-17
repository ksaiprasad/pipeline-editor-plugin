# Visual pipeline editor for Jenkins Workflow. 


This is the https://www.youtube.com/watch?v=CGAZOrXlEU0 editor work in progress. Using jenkins-js-lib and js tomfoolery.

To install: 

`npm install`
`npm install -g gulp`
`gulp bundle && gulp rebundle`

This will set up the js tooling needed and automatically build the changes to the source
js which is stored in main/js to the plugin directory (just reload the browser after that).

The magic happens in src/main/js/ (pipelineeditor.js is the main entry point for the plugin).

# How it works

Right now a json DSL is used (see `json.js`) (and stored in the jenkins config.xml) to keep the state of the UI and pipeline. On change events, a workflow script (via `toWorkflow`) is emitted and stored in the config.xml for actual execution. A longer term plan is native workflow storage support (for this quasi declarative/visual subset of the full power of workflow).

# JavaScript heavy plugins: Enabled by jenkins-js-libs

This is all possible because of https://github.com/tfennelly/jenkins-js-modules and libs made available by: https://github.com/tfennelly/jenkins-js-libs/
This means that namespaced, clean js libraries and css can be made available to any Jenkins plugin that needs it. Ideally, you use the common jQuery, or any library, but if you really need your own, this framework can support it. 
