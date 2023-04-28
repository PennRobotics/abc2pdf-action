# abc2pdf

_[Github Action for Engraving Sheet Music from ABC](https://github.com/marketplace/actions/abc-to-pdf)_

> **Warning**  
> Currently, the correct workflow needs to be _de-commented-out_ and run manually through the "Actions" tab.  
> Some of these steps need to move to **action.yml**


## TODO

- [X] `Error: PennRobotics/abc2pdf-action/first-nonworking-draft/action.yml (Line: 18, Col: 7): Required property is missing: shell`
- [X] `converter/abctopdf: could not find a javascript interpreter - abort`
- [X] `Could not open file: default.abc` \
      `Could not open file: format/test.abc` \
      `Could not open file: ../in/format/test.abc` \
      `../in/multisong-test.abc Error: Cannot read file 'format/test.abc'`
- [ ] On last run (after fixing relative directories) the scale of the music is significantly larger than before, and \
      the **default.abc** error is still present. Figure out whether **format/test.abc** is being called and \
      how the defaults are different from what exists in the format file.
- [ ] Fix any blockers in the [Eventual quick start](#eventual-quick-start) and delete the other two quick start sections
- [ ] If we're already using JavaScript, might as well try _abcjs_


## Quick start

* Upload **.abc** files into `in/`
* Create a new workflow
* Go to the Marketplace link and click the big button to use the latest version of the Action
* Add the displayed code snippet as a step in your workflow
* Run the workflow, making sure the output is saved as an artifact or committed to the repository


## Eventual quick start

* Fork, clone, or import the [abc2pdf-template repository](https://github.com/PennRobotics/abc2pdf-template.git)
* Upload **.abc** files into `in/`
* The upload should automatically trigger a workflow using this GitHub Action
* Monitor the status of the document conversion in the GitHub _Actions_ tab
* If an error occurs, [open an issue](https://github.com/PennRobotics/abc2pdf-action/issues/new/choose)
* Generated PDF output shall upload after a short delay into `out/` with the same filename base as each input


## Legacy quick start

* Fork, clone, or import the [abc2pdf-action repository](https://github.com/PennRobotics/abc2pdf-action.git)
* Upload **.abc** files into `in/`
* The upload should automatically trigger the GitHub Actions for compiling the latest converter source and converting each input document
* Monitor the status of the document conversion in the GitHub _Actions_ tab
* If an error occurs, [open an issue](https://github.com/PennRobotics/abc2pdf-action/issues/new/choose)
* Generated PDF output shall upload after a short delay into `out/` with the same filename base as each input


## Sample ABC

```
X: 1
T: Good King Wenceslas
M: 4/4
L: 1/4
C: Traditional
K: F
|: FFFG | FF C2 | DCDE | F2 F2 :|
   cBAG | AG F2 | DCDE | F2 F2 |
   CCDE | FF G2 | cBAG | F2 B2 | F4 ||
```


## Notes

The output size of _abc2svg_ is about twice as large as _abcm2ps_ for a single tune (173%). This size difference narrows to nearly the same size for three tunes (105%). This probably has to do with individual font differences as well as missing glyphs, such as the time signature icons&mdash;present in _abc2svg_ but not _abcm2ps_.
