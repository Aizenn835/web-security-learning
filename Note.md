1.Access-Control-Allow-Credentials: true - this allows the browser to send a cookie inside browser cookie jar , this should be turn off if am using a jwt since am not using a browser cookie jar and am storing it to a localstorage

2.Access-Control-Allow-Origin - its basically the allowed origin my backend will allow an api to send a response e.g(config.setAllowedOrigins(List.of("https://my-example-website.com")); so if this origin are in the list of my allowed origin, the backend will allow an api to make a response

Commands:
  pwd - shows the current directory
  
  ls - shows the list of directory or files
  
  ls -l - this shows the list in a long way or more detailed
  
  ~ - this gets back you from the default directory
  
  whoami - this shows the current username
  
  cd - this puts you in a directory you want for ex(cd Desktop)

Software commands:

  sudo apt update - checks for update
  
  sude apt upgrade -y - downloads the newer version
