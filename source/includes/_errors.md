# Errors

The Miora API is pretty incosistent on returning errors. We are trying to fix this, but in the meantime you can check if a request has gone wrong on the following scenarios:


Error Code | Meaning
---------- | -------
200 | Sometimes an error returns a 200 code with {'status':error,'message': 'Error message'} 
400 | Error on the request
500 | Internal Server Error -- Contact Mario!
