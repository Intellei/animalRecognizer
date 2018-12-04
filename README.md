# Image Recognition Twitter Bot

Make a serverless, image-recognition-backed Twitter bot.
When a user tweets at the bot: `@YourBotName, what’s in this image?` The bot should reply with the name of the animal, `It’s a Cheetah!`

## Steps to complete this example:
 1. Fork this repository :)
 2. Deploy serverless application with integration with Twitter that tweets "Hello World" on `GET` request to the endpoint (Using the starter code in this repository)
 3. Add Twitter webhook to process incoming tweets to '@YourBotName'. (Can still respond with "Hello World" at this stage)
     Will need to register the webhook on Twitter by triggering `GET` request to a different endpoint to verify the webhook:
     https://developer.twitter.com/en/docs/accounts-and-users/subscribe-account-activity/guides/getting-started-with-webhooks
 4. Determine if incoming tweet has an image. If yes save to s3. (Can still respond with "Hello World" at this stage)
 5. Trigger another lambda upon `s3.ObjectCreated` event to process the image. Move the response of "Hello World" to this new lambda.
     Only people who tweet images at @YourBotName will receive a hello world response
 6. Analyze the image using `AWS.Rekognition` and tweet back the response of the name of the animal.

## Here are some links to get started:
- https://hackernoon.com/a-crash-course-on-serverless-with-node-js-632b37d58b44
- https://garywoodfine.com/twitter-wordpress-aws-lambda-bot/
- The two included files: `./handler.js` and `./serverless.yml` provide some starter code to tweet "Hello World" from a twitter bot.
- https://serverless.com/framework/docs/providers/aws/guide/intro/
- Twitter documentation: https://developer.twitter.com/en/docs/basics/apps

## Expectations:
- Completion of this entire exercise can be difficult, Please do your best to go as far as you can
- When finished, we expect to be able to tweet @YourBotName with an image of a Cheetah and @YourBotName responds appropriately telling us it is a Cheetah
