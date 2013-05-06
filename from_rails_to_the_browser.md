From Rails to the Web Server to the Browser
@dabit

- Life of a request
- Starts in browser, turns into http request
- Web server takes it, hands it to the framework
- Framework processes the request, hands it back to the server

- Rack
  - Library that acts as an interface between frameworks and servers

- Somewhere on the web server...
  - @app.call(env)

- Somewhere on the application side
  - returns http_code, headers, and body

- Requires config.ru

- Sidenote: Look up `$: << '.'`

- All Rails apps are Rack apps
  - Can start a rails app with rackup

dabit/rails-server-browser