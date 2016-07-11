# undertow-rs-static
Contains an overridden class from the UndertowJaxrsServer which allows serving static resources (web pages)

To use, use UndertowJaxrsWebServer in place of where you would use UndertowJaxrsServer:

        UndertowJaxrsWebServer undertowServer = new UndertowJaxrsWebServer();
        undertowServer.addStaticResourcePath( "/swagger/", resource( new ClassPathResourceManager( RestServer.class.getClassLoader(), "web" ) ) );
        undertowServer.addStaticResourcePath( "/favicon.ico", resource( new ClassPathResourceManager( RestServer.class.getClassLoader(), "favicon.ico" ) ) );
        undertowServer.start( Undertow.builder().addHttpListener( port, host ) );
