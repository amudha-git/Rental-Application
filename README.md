# Movie -Rental-Application
A node js application :)

In this application, user can create genres , update genres , retrieve genres and delete genres.
And also user can create movie name, update movie name, retreive movie name and delete movie name.
And possible to update movies's genre id. (Using embedding documents in mongoose)

User can post their movies with pricing details for rental purpose.

User can also purchase the movie that was published already.

User can also return the movie that was purchased already.

All this is possible only if the user logged in. (Authentication)

Only the admin user can delete the record. (Authorization)

REST API's

/api/users'
==============
/me/GET
-will return the logged in user details.

/POST {name:String,email:String,password:String,isAdmin:Boolean}
-will create a new user and set the jwt token in the header.

/api/auth
=============
/POST {email:String,password:String}
-will set jwt token in header if the credentials is correct.


/api/customers
===============
/GET
-will return all the customers created.

/GET:id
-will return the requested custome.

/POST {name:String,isGold:Boolean,phone:Number }
-will create a new customer.

/:id/PUT {name:String,isGold:Boolean,phone:Number }
-will update the customer if customerID is valid.

/:id/DELETE
-will delete the customer if user is admin user.

/api/genres
============

/GET
-will return all the genres created.

/GET:id
-will return the requested genre.

/POST {name:"genreName" }
-will create a new genre.

/:id/PUT {name:"updatedGenreName"}
-will update the requested genre.

/:id/DELETE
-will delete the requested genre if user is admin user.

/api/movies
============
/GET
-will return all the movies created.

/GET:id
-will return the requested movie.

/POST {title:"movieName",genre:"genreName",dailyRentalRate:Number, numberInStock: Number }
-will create a new movie.

/:id/PUT {title:"movieName",genre:"genreName",dailyRentalRate:Number, numberInStock: Number }
-will update the movie details.

/:id/DELETE
-will delete the requested movie if user is admin user.


/api/rentals
===============

/GET
- will return the list of movies available for rentals.

/POST {customerId:String, movieId:String }
-will return the rental details of the requested movie.

'
/api/returns'
================
/POST {customerId:String, movieId:String }
-will return the rental fee and other movie details.


