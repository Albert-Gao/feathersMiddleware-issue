# feathers-middleware-issue

The repo re-produces the cases where you can't see the callstack when there is an error.

The code that should fail is at line `7` of `./src/middleware/index.js`

So, 2 cases here:

## Case 1

1. `npm run start`
1. open `http://localhost:3030/tryme`
1. Browser receive 500 page
1. Nothing shows at the console

## Case 2:

1. `DEBUG=* npm run start`
1. open `http://localhost:3030/tryme`
1. Browser receive 500 page
1. Can see the `feathers-errors GeneralError(500): Cannot read property 'say' of null +0ms` in the console, but no callstack has been shown.
