Notes about the Teradek API
===========================

Endpoints
---------

All enpoints seem to expect form formatted data with POST or query string with GET

Most endpoints allow for basic http auth.
Some only allow for authentication with session and cookie.

- /cgi-bin/api.cgi
    - Looks to be the main API endpoint, used for login en configuration settings
- /cgi-bin/json.cgi
    - Almost the same as api.cgi, but outputs json formatted instead of plain text
    - Also allows json formatted with POST
- /cgi-bin/system.cgi
    - Used to execute commands, instead of changing settings
    - Needs session cookie for authentication.

Actions
-------

### Login


- uri: api.cgi or json.cgi
- parameters
    - command=login
    - user=$USERNAME
    - passwd=$PASSWORD
- returns: Session=56232243

    Use number as value for cookie `serenity-session`

### Help
- uri: api.cgi, json.cgi, system.cgi
- parameters
    - command=help
- returns: plaintext description of endpoint

    Some endpoints have deeper levels of help like `help.cmdlist`
