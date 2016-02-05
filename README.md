
####Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ngrok http 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!


### Steps undertaken to bring optimize online portfolio:
1. Converted <link href="css/style.css" rel="stylesheet"> to inline CS and minified the same
2. Added media="print" attribute to <link href="css/print.css" rel="stylesheet"> since it is only used for printing and not while rendering pages on load.
3. Added async attribute to <script src="http://www.google-analytics.com/analytics.js"></script> since it does not manipulate DOM.
4. Shifted the folowing code at the bottom of the page:
	<script>
      (function(w,g){w['GoogleAnalyticsObject']=g;
      w[g]=w[g]||function(){(w[g].q=w[g].q||[]).push(arguments)};w[g].l=1*new Date();})(window,'ga');
      // Optional TODO: replace with your Google Analytics profile ID.
      ga('create', 'UA-XXXX-Y');
      ga('send', 'pageview');
    </script>


### Steps undertaken to bring frame rate to 60fps:
1. Removed determineDx function since it used layout properties before style in every loop. Modified chchangePizzaSizes function based on it.
2. Created a variable randomPizzaContainer so that the element is not referred multiple times by its jQuery selector.
3. Added requestAnimationFrame function

### Steps to run the application'
1. Open index.html in any browser.
2. From the main page, you can go to Cam's Pizzeria where other optimizations have been done 
