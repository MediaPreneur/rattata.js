
----------
03.06.2012

Introduced the support for caching AJAX results (GET only) in localStorage. Simply add both the entries 'cache: true' and 'expiration: 24' to your model description (not obersevedModels yet!) to enable the caching. The expiration number is the number of hours until which the cached entry expires. The framework automatically will test for localStorage support in the browser. If the feature is not supported, the AJAX request will be triggered directly.

	{
		type: 'GET',
		cache: true,
		expiration: 24,
		url: (...)
	}
	
----------
13.02.2012

Introduced the *extend()* method to extend existing controllers. You can use it just as you are used to define new controllers:

	app.controllers.extend('existingController', {
		newMethod: function(){},
		'click refresh': function(){
			// new binding
		}
	});

----------
13.02.2012

Modified controller UI binding: You can now bind multiple events to one selector at once using a comma separated list, which is useful, as an example, if you want to bind both 'touchstart' and 'click' to the same handler:
	'touchstart,click openLoginDialogue': function(event,element) { ... }


----------
05.02.2012

Modified simple model definition to support three (more excactly four) ways to define a model:
	(1) string,
	(2) enhanced string with type as prefix,
	(3) array with two (simple or complex url + processor) or three elements or
	(4) object which additionaly can contain an error handler (type, url, processor, error)
