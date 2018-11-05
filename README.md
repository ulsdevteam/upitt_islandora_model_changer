# Islandora Model Changer
Allows the fedora model of some objects to be changed.

Currently supports only three Islandora models.
1. islandora:bookCModel
2. islandora:sp_large_image_cmodel
3. islandora:manuscriptCModel

This module will render a link on those three types of objects' Manage page that reads "Change model".  Clicking this will allow you to select the new model for this object.

Changing to a bookCModel means that all of the pages are converted to pageCModel objects and the parent object is converted to a bookCModel.

Changing to a manuscriptCModel means that all of the pages are converted to manuscriptPageCModel objects and the parent object is converted to a manuscriptCModel.

*In the case of changing an object to an image, this only works when the paged content is a single page.*


It should be possible to change the object back to the original type if the change was not intended or desirable.

### REST uri for changing models
For a group of object that need to be changed from Book to Manuscript (for example), the code will handle the model name as a $_GET parameter when passed into the islandora/object/[PID]/manage/changemodel handler with ?model=manuscriptCModel.  Either the long name such as "islandora:bookCModel" or the islandora-implied short model name such as "bookCModel" can be supplied.


*NOTE:* Newspaper Issue can not be supported unless the parent newspaper object (as is related in the RELS-EXT with the `isMemberOf` relationship) is manually related after the fact.
A full analysis of the values related to Newspaper Issues has not been done, so there may be other requirements if this is attempted.


## Author / License

Written by Willow Gillingham for the [University of Pittsburgh](http://www.pitt.edu).  Copyright (c) University of Pittsburgh.

Released under a license of GPL v2 or later.

