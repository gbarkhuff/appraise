# Appraise

### Painless visual test automation 

![](templates/assets/logo.png)

This is a (research) project aimed at prototyping a tool for visual approval testing. The goals of the project are to build a tool that helps delivery teams with the following tasks:

- Review and approve changes to web pages, visual layouts and browser components quickly through visual inspection 
- Start Spec by Example/BDD from a hand-drawn sketch or a wireframe,  easily compare actual outcomes, then just approve the final result to make a regression test
- Automate acceptance/regression tests for visual look and feel in a visual language, rather than xUnit style code
- Speed up visual exploratory testing by making it easier to rebuild visual components from example data/configuration
- Publish easily maintainable/verifiable developer docs with visual examples to Github easily (markdown) or as a static site (html)
- Run visual tests quickly/in parallel using AWS Lambda

## In action

![](screenshot.png)

## Status

too early to use (pre-alpha)


### Tasks

- [x] Choose a markdown rendering system (https://github.com/markdown-it)
- [x] Choose a Node DOM manipulation system (https://github.com/cheeriojs/cheerio)
- [x] Build local screenshots (using Chrome Headless and https://github.com/cyrus-and/chrome-remote-interface)
- [x] Choose an image comparison system (https://github.com/mapbox/pixelmatch)
- [x] generate a combined image if dimensions do not match, showing both images with alpha
- [x] Add a generic layout to HTML when converting from MD 
- [x] Add a generic template for result files
- [x] Create an index with all test results
- [x] Clean up templates and provide a nice layout
- [ ] Make it easier to inspect/approve
  - [x] CLI Approval instructions on the results page
  - [x] CLI Approval instructions on the rendered page (for all examples)
  - [x] Overview/Overlay/Inspect on the results page
    - [x] set view/opacity/zoom for actual/expected/diff separately
    - [ ] scale down large images so they are easier to see on the overview 
      - [ ] checkbox for original size/size to fit
- [x] Run examples without expected outcomes (fail + show actual)
- [ ] Distinguish between a failure and error
  - [x] record errors from fixtures
  - [x] display error as status when listing results
  - [ ] format/test error messages
    - [x] thrown as exceptions
    - [ ] thrown as strings
    - [ ] rejected from a promise
- [ ] Fixture execution
  - [x] inside node
    - [x] detect and parse example format (eg json or yaml)
    - [ ] pass fixture parameters as the second argument
    - [ ] pass temporary working dir
    - [ ] allow fixtures to return a file
  - [ ] URL fixture execution (eg test the same site in various resolutions)
  - [ ] in-browser fixture execution
    - [ ] custom event to signal finished rendering
    - [ ] webpack fixture packaging
    - [ ] inject css/js
    - [ ] AWS Lambda fixture engine
- [ ] Extend example properties
  - [ ] Configurable clip area for screenshots
  - [ ] Configurable initial size for html windows
  - [ ] Configurable image matching precision and anti-aliasing
- [ ] Extract configuration/enable overrides
  - [x] Configurable source and work directories (don't just dump stuff to temp)
  - [x] Configurable clip area for screenshots
  - [x] Configurable initial size for html windows
  - [x] Configurable image matching precision 
  - [ ] + and anti-aliasing
  - [x] Configurable HTML attributes (`data-example`)
  - [ ] Configurable HTML classes for success/failure
  - [x] Configurable screenshot engine
  - [x] Configurable fixture engines (via NPM modules)
  - [ ] Config file to set all options quickly
- [ ] Server for interactive work
  - [ ] render example folder structure + README.md for folders
  - [ ] render markdown from the examples folder 
  - [ ] offer running the spec if the MD contains any examples
  - [ ] approving changes
  - [ ] Running tests by directly reading specs from github (eg public site, connect to a gitub repo)
  - [ ] Approving by directly committing to github? (eg for specs stored in github repos)
- [ ] AWS Lambda screenshots 
- [ ] Result formatters 
  - [x] JSON
  - [ ] junit
  - [ ] tap
- [ ] Reporters
  - [ ] ASCII console
  - [ ] ANSI color console
  - [ ] Summary (dot)
- [ ] CLI/NPM tasks
  - [ ] executing tests
   - [x] run all tests 
   - [ ] run a specific page
   - [ ] run a specific example
   - [x] exit with -1 in case of errors/failures
  - [ ] approving changes
   - [x] approve a whole page
   - [x] approve a specific example
   - [ ] approve all failed examples


## Before alpha

- [ ] record timestamp when a page started executing, use in the result template
- [ ] use pageObj.sourcePath when approving with new result instead of hard-coding the path
- [x] put example name into the example object/results object for easier templating
- [x] use timestamps for executed and started in result template
- [x] test with multiple examples in a single file
- [x] test with multiple files
- [x] test with files in subfolders
- [ ] test with large images
- [ ] test with complex page and example names
- [ ] test with exceptions thrown throughout the test process
- [x] breadcrumbs on rendered page -> links
- [ ] directory summaries for page folders
- [ ] tabs in summary (pages/examples)
- [x] navigation on results page (breadcrumbs and page links)
- [x] Retina screen sizing
- [ ] Solve cross-linking (eg replace .md in local links to .html when generating html)
- [ ] detect examples with the same name on a page
- [x] Start/stop chrome once per run, not once per page
- [x] change sync FS operations to async

