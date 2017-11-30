# Weekly Meetings

* [20th October 2017](#date-20th-october-2017)
* [13th October 2017](#date-13th-october-2017)
* [6th October 2017](#date-6th-october-2017)
* [29th September 2017](#date-29th-september-2017)
* [22nd September 2017](#date-22nd-september-2017)
* [14th September 2017](#date-14th-september-2017)

### Date; 20th October 2017
#### What did I achieve?
* [Experiment planner](https://github.com/smpadhy/brainverse/tree/feature-kanban-board): Features implemented
  * Edit column header
  * Control for 'add item'
  * Automatic generation of form for each item add click with a Modal popup
  * Updated form generation module for input form
  * 'Assignee' field integrated with github users api
  * Template for item card
  * Item card add implemented
* SOBP abstract submission
* NIDM, ReproNim Training meeting

#### What did i struggle with?
* SOBP abstract - understanding the brainverse use case
* Typeahead feature for Assignee field while integrated with github users within alpaca form.
* Refreshing the alpaca view and kanban view after update/edit

#### Who help me this week?
* David and Satra on the SOBP abstract

#### Who did I help ths week

#### What would I like to work on next week?
* Experiment Planner - Column delete, Item Edits, Item delete, Item move
* REDCap to NDA Importer test

#### Where do I need help from Satra
* Review of implemented feature

#### What else did I do?

### Date: 13th October 2017
#### What did I achieve?
* Worked on NDA Editor
  * Added options to source select box - NDA, Repronim curated, user forked repo, local
  * Added corresponding routes and implementation for user forked repo and local to obtain the curated forms
  * Added refresh link to refresh the NDA editor page
  * Fixed pull request error. Added a setTimeout before creating a file in the forked repo.
  * Finished the first version of the NDA Editor, packaged it and released it.
  * Link to the [App](https://www.dropbox.com/s/c918cszw6oiaubr/BrainVerse-darwin-x64.zip?dl=0)
  * Link to the [demo](https://www.dropbox.com/s/8nhcjxgx8do7tnt/nda-editor.mov?dl=0)
  * Refactored the code and cleaned up
* Started working on Experiment Planner
* Started working on NIDM-Worflow pyNIDM requirement class
* Had meetings - NIDM, NIDM-Workflow
* Had meeting with Satra
* Agreed for SOBP abstract submission for DK
* Attended first 1 hr of Neuropsych/Behavioral Assessments Training

#### What did I struggle with?
* Looking into jqWidgets kanban and core minified code, unminified them and trying to access the amount of effort require to modify the header of the column to allow extra icons.
* Considering the option to design my own experiment planner css class given the limited flexibility of jqWidgets Kanban board.

#### Who helped me this week?
* Satra suggested some modifications with NDA Editor - having four sources
* Had Discussions on - how to infer two curated forms used for data acquistions are the same based on hash, abstract submission to OHBM, IEEE Big Data, generating GUID for NDA, automatic generation of constants.py in pyNIDM, creating pyNIDM workflow OWL file

#### Who did I help this week?

#### What would I like to work on next week?
* Experiment planner - editing column header, delete column, add and edit items
* SOBP abstract submission

#### Where do I need help from Satra
* SOBP abstract submission

#### What else did I do?
* Learning advanced Javascript
* Learning Machine Learning
* Meeting with Software-Defined Networking Team

### Date: 6th October 2017
#### What did I achieve?
* Worked on the NDA Form Editor
  * Added tansformation method to convert form edits to NDA data model and saved locally as json
  *  Using Github API v3, added relevant methods in controller and routes to:
    * [fork](https://developer.github.com/v3/repos/forks/#create-a-fork) [ReproNim/ni-terms](https://github.com/ReproNim/ni-terms) repository to user github account
    * [create a file](https://developer.github.com/v3/repos/contents/#create-a-file) in the forked repo and push the curated form (NDA data model) into the file with a default commit message.
    * [create a pull request](https://developer.github.com/v3/pulls/#create-a-pull-request) from the forked repo
    * [get the curated data dictionaries list in the ni-terms repo](https://developer.github.com/v3/repos/contents/#get-contents) and updates the select drop down box with new curated files
    * get the content of the curated file selected, save it and populate the terms in the table for selection.
  * Made changes to the UI - added another select box select between NDA and Repronim Curated NDA forms
* Had meeting -  NIDM-W, Repronim Training
* Looked into the details of Mavo github backend implementation
* Started looking into the RedCap to NDA exporter by Hauke.

### What did I struggle with
* Github API for create file: The content has to be base64 encoded in the body of the request. Even after the content is base64 encoded, in the github after push, the indentation in a JSON file was not being preserved. Later released that JSON.stringify has an optional parameter to set the indentation.
* Refreshing the select box list:  While using github contents api to obtain the files from the ni-terms repo, one has to wait till all individual files downloaded, extracting relevant information to send as reponse to the ajax call from the UI. It took me a while to figure out the interplay of request and promise api to make it work.
* Names and ids: I am still trying to figure out the best way to name the curated files. As per discussionwith Satra earlier, we could use 'username/title of the file' which I am currently using. However, in the interface we provide options for user to assign different name/title to the form. The 'shortname', which is unique to NDA data dictionaries is carried over to the curated form. So, need to assign new shortName to curated form to uniquely identify the form. As Satra mentioned, the shortname has a version number associated with it. So, still thinking on how to version the curated forms.
* Merging data-dictionaries list from three sources (NDA, curated forms from github, local): Still trying to figure out the best way. This is related to the previous problem of assigning/versioning the curated forms. In addition, the forms from NDA has some extra fields which we didn't carried over to curated forms in the earlier implementation. So, some modification to model for the curated forms required
* Conversion form edits to NDA model: To decide which field of a term can be carried over directly to the curated term and if a new term is added, how to assign ids and names.

#### Who helped me this week?

#### Who did I help this week?

#### What would I like to work on next week?
* Finish, polishing, testing, packaging  NDA Editor module
* Start working on project planner
* Mavo for term editor

#### Where do I need help from Satra
* Reviewing and Testing NDA editor
* Enable Mathias to give me access to RedCap database

#### What else did I do?
* Learning Javascript
* Vacation (2nd Oct 2017)

### Date: 29th September 2017
#### What did I achieve?
* Worked on the NDA form edit feature in Brainverse:
  * Reviewed and understood the alpaca form designer demo code
  * Adapted the demo code so we can use it within brainverse for NDA form editor
  * Integrated form editor with the NDA data dictionary import interface
  * Clear and Preview button button were reimplemented
  * Form generation module updated, specifically, using NDA field id as form field id and fixed radio button generation
  * Converted all 'select box' to radio buttons
  * code clean up
* Fixed nidm-term-search code to show DICOM owl file.
  * Did code clean up
* Explored Mavo to be used for nidm-term-search
* Attended NIDM, NIDM-W and Repronim-all call meetings
* Meeting with Satra on form edit feature and future steps

#### What did I struggle with?
* Understanding alpaca form designer demo code. The reason being: no local storage or global schema json were directly updated when any change/edit to the schema or options happens. The editors (schema, options, data, code) were updated with the internal json object (_schema, _options) and later the global schema and option objects were updated.
* nidm-term-search prefix - the dicom owl file when loaded to rdfstore was giving invalid IRI. This led me to think that the incorrect prefix for dicom was due to this. However, later found that there was a bug converting the IRI to prefix format.

#### Who helped me this week?
* Satra helped in reviewing the form edit feature and suggested next steps
* Satra pointed out that nidm-term-search prefix error may be due to some other reason rather than IRI invaid error
* Karl, Camille, Satra discussion on IRI invalid error and helped me understand the specification.

#### Who did I help this week?
* Tried to help Karl with IRI invalid error and initiated the discussion on this.

#### What would I like to work on next week?
* Form Edit feature
* Pushing the changes to github term repo
* Mavo
* Data crawler

#### What else did I do?
* Learning advanced HTML/CSS/Javascript from online courses
* Vacation on Fri (29th Sept 2017) and Mon(2nd Oct 2017)

### Date: 22nd September 2017
#### What did you achieve?
* Further reorganized UI modules in the brainverse repository. Now all modules files are moved from public folder to modules folder with eaach module having html, css and js sub-folders. This [pull request](https://github.com/ReproNim/brainverse/pull/69) is merged and closed now.
* Fixed and improvised the code for creation of directories and sub-directories (with the use of promise) when the brainverse app starts for the first time. The [pull request](https://github.com/ReproNim/brainverse/pull/70) corresponding to this is merged and closed.
* As discussed, I started working on the NDA form edit feature:
  * Imported the [alpaca form buider demo](http://www.alpacajs.org/demos/form-builder/form-builder.html) to brainverse.
  * Reorganized eapp/public/lib/
  * Created a [WIP pull request](https://github.com/ReproNim/brainverse/pull/71) for this feature.
* Presented 'Brainverse' in the DataBlitz

#### What did you struggle with?
* While working on the NDA form edit feature, the first approach I tried was to enable editing the preview form in-place. To do so, setting the contentEditable attribute of the alpaca form to true enabled labels and content of each HTML element of form editable except for the select box. However, I could not access each element with its ID as selector.
* Posted [this issue](https://stackoverflow.com/questions/46307840/accessing-html-element-in-an-alpacajs-generated-form-and-making-content-contente) in the stackoverflow and recieved one reply.
* Another issue that I struggled was adding action to the column custom header button. I posted this issue in jqWidgets Forum and details can be found [here](https://www.jqwidgets.com/community/topic/multiple-custom-button-in-the-column-header/) .

#### Who helped you this week?
* Had discussion with Aneesha and Satra on the form edit issue. Satra pointed to the alpaca form builder example. Revisiting the form builder example was insightful as now I have more clear understanding of the alpaca than when I first reviewd that example.
* As Aneesha tried to run Brainverse app, she got error for directories were not being created correctly due to async operation. So, it led me to fix and improvised the code using promise, which I had in mind for a long time.

#### Who did you help this week?
* Had a very quick discussion with Shilpa on data crawler with example from pybids BIDS validator

#### What would you like to work on next week?
* NDA form editor - Edit feature
* Exploring mavo
* Data crawler with BIDS validator

#### Where do you need help from Satra?
* On reviewing/discussing the NDA edit feature interface as it design and implementation progreses over the week. Probably through Slack or pull request.

#### What else did you do?
* Learning CSS, HTML, Machine Learning
* Attended a few seminars related to AI and machine learning


### Date: 14th September 2017
#### What did you achieve?
* Reorganized UI for modules in the Brainverse repository
* Started working on combining two interfaces  - create a plan and kanban board display- to one (similar to github project management ui). Finished the following UI components :
  * Add Plan
  * Edit Plann info
  * Add Column with customer header buttons
  * Updated form generator
* [Demo of new kanban board UI implemented so far](https://www.dropbox.com/s/nym6bl6uqzlpt12/newUI-14thSeptember2017.mov?dl=0)
* [GitHub repo](https://github.com/smpadhy/brainverse/tree/feature-kanban-board)

#### What did you struggle with?
* Mostly with CSS for Add Column and placing Column headers custom buttons and trying to make it more responsive

#### What would you like to work on next week?
* Column information editing, delete UI
* Add Item cards within a Column
* Item cards editing UI
* Reorganizing/reviewing modules API for consistency
* Basic Crawler with BIDS validator

#### Where do you need help from Satra?
* Review of the new UI implemented so far
* Discussion on the consistent modules API

#### What else did you do?
* Learning Machine Learning from lecture notes/online tutorial

--------

## Template (Copy template, add date link on top, and replace text, newest first)

### Date: [INSERT DATE OF MEETING]

#### Who did you help this week?

Replace this text with a one/two sentence description of who you helped this week and how.


#### Who helped you this week?

Replace this text with a one/two sentence description of who helped you this week and how.

#### What did you achieve?

* Replace this text with a bullet point list of what you achieved this week.
* It's ok if your list is only one bullet point long!

#### What did you struggle with?

* Replace this text with a bullet point list of where you struggled this week.
* It's ok if your list is only one bullet point long!

#### What would you like to work on next week?

* Replace this text with a bullet point list of what you would like to work on next week.
* It's ok if your list is only one bullet point long!
* Try to estimate how long each task will take.

#### Where do you need help from Kirstie?

* Replace this text with a bullet point list of what you need help from Kirstie on.
* It's ok if your list is only one bullet point long!
* Try to estimate how long each task will take.

#### Any other topics

This space is yours to add to as needed.
