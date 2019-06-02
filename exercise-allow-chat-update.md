# Exercise: Allow update of existing chat messages (10-20 minutes)

## Objective
Change a chat API server to allow update of existing chat messages using PUT method.

You can assume the edited messages are all submitted in the correct JSON format.

The route should be `/messages` and the HTTP method should be PUT.

Do *not* update the message's properties: `ID` or the `timeSent`

### Advanced (optional): 
* In addition to the above, reject updates which have a `from` property of longer than 20 characters, or a `text` property of longer than 100 characters.  Use a 400 status code in this case.

## What should I start with?
You should use your own chat server or (if you haven't done that homework yet) you can remix [our starting project: cyf-start-chat-put](https://glitch.com/~cyf-start-chat-put).

If you remix our starting project, immediately rename it as `cyf-joan-chat-v2` (but change it for YOUR name)

## What should I test with?

You should test with Postman

Once it's working in Postman, you can also use the React chat app here to test: https://cyf-chat-tester.netlify.com/
* You'll have to set the API to the base address of your chat server
* Remember to watch in the network panel of the dev tools, to see if any requests fail quietly.

## What should I test for?
* Check that your updated `text` or `from` fields are updated by `GET`ting all messages after the `PUT`.
* Submit a different `id` and `timeSent` property value in the request body and check that these are *not* updated (`GET` all the messages after, to check what has changed.)

## Getting help

* You can refer to [this small express cheatsheet](express-cheatsheet.md)

## When you are finished
* When you are finished (including testing), DM your URL via Slack to someone sitting next to you and they must test if your API works!
