== Welcome to Rails

Rails is a web-application framework that includes everything needed to create
database-backed web applications according to the Model-View-Control pattern.

This pattern splits the view (also called the presentation) into "dumb"
templates that are primarily responsible for inserting pre-built data in between
HTML tags. The model contains the "smart" domain objects (such as Account,
Product, Person, Post) that holds all the business logic and knows how to
persist themselves to a database. The controller handles the incoming requests
(such as Save New Account, Update Product, Show Post) by manipulating the model
and directing data to the view.

In Rails, the model is handled by what's called an object-relational mapping
layer entitled Active Record. This layer allows you to present the data from
database rows as objects and embellish these data objects with business logic
methods. You can read more about Active Record in
link:files/vendor/rails/activerecord/README.html.

The controller and view are handled by the Action Pack, which handles both
layers by its two parts: Action View and Action Controller. These two layers
are bundled in a single package due to their heavy interdependence. This is
unlike the relationship between the Active Record and Action Pack that is much
more separate. Each of these packages can be used independently outside of
Rails. You can read more about Action Pack in
link:files/vendor/rails/actionpack/README.html.


== Getting Started

1. At the command prompt, create a new Rails application:
       <tt>rails new myapp</tt> (where <tt>myapp</tt> is the application name)

2. Change directory to <tt>myapp</tt> and start the web server:
       <tt>cd myapp; rails server</tt> (run with --help for options)

3. Go to http://localhost:3000/ and you'll see:
       "Welcome aboard: You're riding Ruby on Rails!"

4. Follow the guidelines to start developing your application. You can find
the following resources handy:

* The Getting Started Guide: http://guides.rubyonrails.org/getting_started.html
* Ruby on Rails Tutorial Book: http://www.railstutorial.org/


== Debugging Rails

Sometimes your application goes wrong. Fortunately there are a lot of tools that
will help you debug it and get it back on the rails.

First area to check is the application log files. Have "tail -f" commands
running on the server.log and development.log. Rails will automatically display
debugging and runtime information to these files. Debugging info will also be
shown in the browser on requests from 127.0.0.1.

You can also log your own messages directly into the log file from your code
using the Ruby logger class from inside your controllers. Example:

  class WeblogController < ActionController::Base
    def destroy
      @weblog = Weblog.find(params[:id])
      @weblog.destroy
      logger.info("#{Time.now} Destroyed Weblog ID ##{@weblog.id}!")
    end
  end

The result will be a message in your log file along the lines of:

  Mon Oct 08 14:22:29 +1000 2007 Destroyed Weblog ID #1!

More information on how to use the logger is at http://www.ruby-doc.org/core/

Also, Ruby documentati
