# Real time

Let's build a chat-app today. 

Requirements:
- A user needs to be able to post new messages
- A user needs to be able to see old messages from the chat when they first connect
- A user needs to be able to see their own messages
- A user needs to be able to see new messages posted by other people

## Long Polling

This strategy is to make lots of requests, we will keep making requests over and over again. It's just making AJAX call on some interval. 

We need to make an endpoint that can take a lot of calls. We couldn't use the `setInterval` to run a function on every X seconds as it doesn't account for the time that server takes to process a requests. eg: we make a request every 3 secs but API takes 4 secs to respond.

Instead, need to start a timer for the next requests as soon as the current one completes.