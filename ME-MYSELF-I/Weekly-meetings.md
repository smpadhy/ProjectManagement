# Weekly Meetings

*[22 September 2017](#date-22nd-september-2017)
* [14th September 2017](#date-14th-september-2017)

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
