# Errors
The Proxyclick API uses HTTP responses to indicate the success or failure or an error of API requests. While not all codes listed below are used, some may be used in the future. 
Note that 4xx and 5xx responses may be returned for any request and clients should cater for them.

Error Code | Meaning
---------- | -------
400 | Bad Request -- The server cannot or will not process the request due to something that is perceived to be a client error (e.g., malformed request syntax, invalid request message framing, or deceptive request routing).[14]
401 | Unauthorized -- Similar to 403 Forbidden, but specifically for use when authentication is required and has failed or has not yet been provided.
403 | Forbidden -- The request was a valid request, but the server is refusing to respond to it.
404 | Not Found -- The requested resource could not be found but may be available again in the future.
405 | Method Not Allowed -- A request was made of a resource using a request method not supported by that resource; for example, using GET on a form which requires data to be presented via POST, or using PUT on a read-only resource.
406 | Not Acceptable -- The requested resource is only capable of generating content not acceptable according to the Accept headers sent in the request.
410 | Gone -- Indicates that the resource requested is no longer available and will not be available again.
412 | Precondition Failed -- The server does not meet one of the preconditions that the requester put on the request.
500 | Internal Server Error -- A generic error message, given when an unexpected condition was encountered and no more specific message is suitable.
503 | Service Unavailable -- The server is currently unavailable (because it is overloaded or down for maintenance).
