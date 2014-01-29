angular-image-upload
====================

Upload images in an elegant way with this AngularJS directive.

how it works
------------
A form is hidden behind the image you choose to display. The user can click on the image, which 
allows them to select a new image file and upload to the url chosen. The image will automatically 
replace itself once the image has been uplaoded successfully. This is all done asynchronously. 

Developers can also set their own loading symbol and error handling if they so choose to.

install
-------

```
bower install angular-image-upload
```

usage
-----

Make sure you include the module in your application config

```
angular.module('myApp', [
  'imageUpload',
  ...
]);
```

Provide options in your controller.
```
angular.module('myApp').controller 'ImageCtrl', ($scope) ->
  $scope.imageOptions = {
    read: <url_to_read_image_from>,
    write: <url_to_write_image_to>,
    enabled: true,
    error: function (event, response) {
      console.log('error, ', response);
    }
  };
```

And use the directive
```
<div image-upload="imageOptions"></dic>
```

If you would like to have a loading symbol while the upload is happening, you can simply use css
```
.fileUpload .fileUpload-loading {
  background: ...
}
```
