# DropArea 1.0.x

Makes an easy and intuitive to upload upload files through drag and drop or select methods. 

[Live Demo](http://awin.com.br/droparea).

This plugin is inspired on the solution given by Ravishanker Kusuma (http://twitter.com/hayageek) 
at http://hayageek.com/drag-and-drop-file-upload-jquery/ where he describes how to create an easy way to 
drag and drop files and upload it to server. Many other enhancements were made.

## Getting started

Import required libraries and stylesheets.

DropArea requires jQuery.

```
  <link rel="stylesheet" type="text/css" href="../src/droparea.css" />
  <script type="text/javascript" src="js/jquery.1.7.1.js"></script>
  <script type="text/javascript" src="../src/droparea.js"></script>
```

Create the area where files would be dropped and the input file to a fallback.

```
  <div class="droparea" >
    <img src="http://placehold.it/200" id="file_preview" >
    <span >Drag and drop files here!</span>
  </div>
  <input type="file" name="file" id="file" accept="image/*" style="display: none;" >
```

Then, just initialize it.

```	
	<script type="text/javascript" >
	  $(document).ready(function(){
	    $('.droparea').droparea();
	  });
	</script>

```

That's all. :) Cool, don't you?

## Options

You also can pass some options when initializing it.

These options are:

Option          | Type            | Default         | Definition
--------------- | --------------- | --------------- | --------------------------------------------- 
url             | String          | N/A             | It's the path to the server side script which will upload your file.
upload          | Boolean         | true            | Whenever set to false, droparea won't upload the file to server, but set it into a local 'file' field instead. If false, a 'file_holder' is required
file_holder     | String          | #file           | It's the file holder to place files when 'upload' is set to false, and ignored when 'upload' is set to true.
file_preview    | String          | #file_preview   | Whenever uploading an image file, and file_preview is given, droparea tries to intercept the manual selection of files on 'file_holder' and display the selected image on 'file_preview' as soon as it is selected.
notification_delay | Integer      | 5000            | Delay to remove the 'complete' notification (milisenconds)
accepted        | String          | '.jpg|.png|.gif' | The accepted extensions for upload set null or false for all files
file_max_size   | Integer         | 2048            | The file max size allowed for upload
extra_data      | Array           | []              | The extra data that would be necessary to subimit with file it's supposed to be only html form elements, such as: input, select, etc. Must be an array with the id of elements (# is not required)
success         | Function        | NULL            | A success callback, called after upload is complete there are two arguments passed: server_response_obj and file_name whenever the server returns it 
i18n            | Object          | * See below     | The internationalization object containing all used strings.

* i18n Default Value
```

    {
        unable_to_upload: 'Unable to upload at this time.<br >Select a file.',
        wrong_file_type: 'Unacceptable file type!<br >Try: %s',
        abort: 'Abort',
        mb: ' MB',
        kb: ' KB',
        percent: '% ',
        dismiss: 'Dismiss',
        error: 'Err: '
    }
    
```

## Get involved

Fork me on github, or use fell free to suggest enhancements or bugfixes.

Happy coding! :)