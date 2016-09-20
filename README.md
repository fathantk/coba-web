main_html = """
    <html>
        <head>
            <title> greetings Page </title>
        </head>
        <body>
            <p> Hello Google App Engine World </p>
            <form method="post">
                <br />
	        "what is your name"
	        <inout type = "text" name = "user" maxlength = "12"
                <br />
    	    </form>
        </body>
    </html>
"""

class MainPage(webapp2.RequestHandler):
    def get(self):
        self.response.write(main_html)

    def post(self):
        username = self.request.get('user')[0:11]
	self.response.write('greetings from your computer <string>' + username + '<strong>')

app = webapp2.WSGIApplication([('/', MainPage)], debug = True)
