How to use
==========

1. Run app.js
2. Go to http://localhost:3000/
3. Execute this command on your JavaScript console, for example on your Google Chrome:
   a. Post
	* Use form "Add a new product" or execute this command on your console :    

	jQuery.post("/api/products", {
            "title": "Your Product Title",
            "description": "Your Product Description",
            "style": "Your Product style"
        }, function (data, textStatus, jqXHR) {
             console.log("Post resposne:"); console.dir(data); console.log(textStatus); console.dir(jqXHR);
        });
	
   b. Read all products

	jQuery.get("/api/products/", function (data, textStatus, jqXHR) {
    	   console.log("Get resposne:");
    	   console.dir(data);
    	   console.log(textStatus);
    	   console.dir(jqXHR);
	});

   c. Read single product depend on the _id for example 50fe4c6f9433c4bb05000002

	jQuery.get("/api/products/50fe4c6f9433c4bb05000002", function(data, textStatus, jqXHR) {
    	   console.log("Get resposne:");
    	   console.dir(data);
    	   console.log(textStatus);
    	   console.dir(jqXHR);
	});

   d. Update single product depend on the _id for example 50fe4c6f9433c4bb05000002

	jQuery.ajax({
    	   url: "/api/products/50fe4c6f9433c4bb05000002",
    	   type: "PUT",
    	   data: {
      	      "title": "Your New Product Title",
      	      "description": "Your New Description",
      	      "style": "Your New Product Style"
    	   },
    	   success: function (data, textStatus, jqXHR) {
              console.log("Post resposne:");
              console.dir(data);
              console.log(textStatus);
              console.dir(jqXHR);
    	   }
	});

    e. Delete single product depend on the _id for example 50fe4c6f9433c4bb05000002

	jQuery.ajax({
    	   url: "/api/products/50fe4c6f9433c4bb05000002", 
    	   type: "DELETE",
    	   success: function (data, textStatus, jqXHR) { 
        	console.log("Post resposne:"); 
        	console.dir(data); 
        	console.log(textStatus); 
        	console.dir(jqXHR); 
    	   }
	});

Reference :
http://www.pixelhandler.com/blog/2012/02/09/develop-a-restful-api-using-node-js-with-express-and-mongoose/