# Javascript Functions.

Lets take a quick look at Javascript functions.

## Demo

* Log to the console

	```
	// logs to the chrome console
	console.log('simple logger');
	```
* Define a function. 

	```
	// Define a function.
	// simple function to say hello
	function sayHi() {
	    console.log('sayHi: hello');
	}
```
* Invoke the function

	```
	// Invoke or run the function
	// Need the parens.
	sayHi();
	```
* Just a hunk of code. And this hunk of code can be assigned to a variable, yep, yep, yep.	

	* Functions are just a block of code that can be assigned to a variable.  
	* Functions in javascript are 'first class objects'. They can be *more later on this*  : 
		- Assigned to a variable.
		- Passed to a function.
		- Returned from a function.

	```
	//Assign function to a variable.
	var sayHiAgain = function () {
    	console.log('sayHiAgain');
	}
	sayHiAgain();
	```
  
* Functions can be passed arguments, surprised? naaa.

	```
	// They can take arguments
	var saySomething = function (msg) {
	    console.log(msg);
	};
	saySomething('hello from tom');
	```

* ALWAYS use var when declaring a variable. **
And variables NOT defined with var are globals. WATCH OUT FOR THIS! **

	```

	var x = 22;

	var doItGlobal = function () {
      console.log('In doItGlobal: x = ' + x);
	};

	var doItGlobalAgain = function () {
      x = 33;
      console.log('In doItGlobalAgain: x = ' + x);
	};

    // See you didn't use the var keyword, bad, bad.
    doItGlobal();
    doItGlobalAgain();
    console.log('Global scope x = ' + x);
	```

* Did I say ALWAYS use a var enough? *we got it, OK*  

	```
	// Use the var keyword, ALWAYS
	var doItLocal = function(){
   	  var x = 88;
 	  console.log('In doItLocal: x = ' + x);
	}

	doItLocal();
	// Didn't change global in function. GOOD!!
	console.log('Global scope x = ' + x);

	```
	
	*Don't feel more happier, brighter and hey look at those unicorns, weeee*

* Multiple Arguments to a function.  

	```
	// multiple params are OK.
	var multiParamsFunc = function (x, y, z) {
      var result = "x = " + x + ", y = " + y + ', z = ' + z;
      console.log("multParamsFunct: " + result);
	};

	var result = multiParamsFunc('hey', 'foo', 'bar');
	console.log('Oops didnt return anything: result =  ' +  result);
	```

* Fix the above.

	```
	// multiple params are OK.
	var multiParamsFunc = function (x, y, z) {
      var result = "x = " + x + ", y = " + y + ', z = ' + z;
      return result;
	};

 	var result = multiParamsFunc('hey', 'foo', 'bar');
	console.log('Oops didnt return anything: result =  ' +  result);

	```
* Lets pass only two of three args.  

	```
	var result = multiParamsFunc('hey', 'foo');
	console.log('Only two args passed: result =  ' + result);

	// Can get all of the functions arguments.
	// Kind of like splat in Ruby?
	var funcArgs = function(arg1) {
      for(var i = 0; i < arguments.length; i++){
        console.log('argument[' + i + ']= ' +  arguments[i] );
    }

  };

	// Cool can get all the args
	funcArgs(77, 'hello', 'goodbye');
	```
	
