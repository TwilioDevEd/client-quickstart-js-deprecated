<a href="https://www.twilio.com">
  <img src="https://static0.twilio.com/marketing/bundles/marketing/img/logos/wordmark-red.svg" alt="Twilio" width="250" />
</a>


This application should give you a ready-made starting point for writing your
own voice web applications with Twilio Client. Before we begin, we need to collect
all the config values we need to run the application:

| Config&nbsp;Value  | Description |
| :-------------  |:------------- |
TwiML&nbsp;App&nbsp;SID | The TwiML application with a voice URL configured to access your server running this app - create one [in the console here](https://www.twilio.com//console/phone-numbers/dev-tools/twiml-apps). Also, you will need to configure the Voice "REQUEST URL" on the TwiML app to point to a Twilio Function you will create.
Twilio&nbsp;Phone&nbsp;# | A Twilio phone number in [E.164 format](https://en.wikipedia.org/wiki/E.164) - you can [get one here](https://www.twilio.com/console/phone-numbers/incoming)

## Creating the quickstart functions

To get you up and running with this quickstart, you can use a template to create your functions. Start by going to the [Twilio Functions](https://www.twilio.com/console/runtime/functions/manage) page in the Twilio Console.

You can add new functions with the plus button on that screen. Look for the *Twilio Client Quickstart* template, and create it. You'll need the two values you gathered above as the configuration settings for this template.

After you successfully put in the configuration, you'll have two Twilio Functions - one for the capability token, and one for the TwiML web application's voice response.

## Configuration and setup

[Configure your TwiML app](https://www.twilio.com/console/phone-numbers/dev-tools/twiml-apps)'s
Voice "REQUEST URL" to be your Twilio Function URL - you can copy and paste the URL directly from the voice calls function page. For example:

![screenshot of twiml app](https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/ClientJSCopyVoiceURL.width-500.png)

Also, you'll need to modify the function URL in quickstart.js to point to your capability token Function - go ahead and copy the capability token URL like you did for the voice calls URL, and put that into quickstart.js, replacing this line:

```
https://YOUR_FUNCTION_SUBDOMAIN_HERE.twilio.io/capability-token
```

The subdomain you use for Twilio Functions will be the same for any functions you create - including the capability token and voice call functions.

### Warning

NOTE: You should not use Twilio Functions to generate capability tokens for your app in production. Each function has a publicly accessible URL which a malicious actor could use to obtain tokens for your app and abuse them.

[Visit our guide](https://www.twilio.com/docs/voice/client/capability-tokens) to learn how to generate capability tokens in your own C#, Java, Node.js, PHP, Python, or Ruby application.

## Setting up a local HTTP server

You'll need to load the front end of your web application from a web server for Twilio Client to connect successfully from Chrome (it should work in Firefox if you load it from the file system). The easiest way to do that is to install a local HTTP server like [http-server](https://github.com/indexzero/http-server)

```bash
npm install http-server -g
```

or 

```bash
sudo npm install http-server -g
```

on macOS or Linux


## Run the local server

```bash
http-server
```

## Have some fun

 You should now be ready to rock! Make some phone calls.
   Open it on another device and call yourself. Note that Twilio Client requires
   WebRTC enabled browsers, so Edge and Internet Explorer will not work for
   testing. We'd recommend Google Chrome or Mozilla Firefox instead.

   ![screenshot of chat app](https://s3.amazonaws.com/com.twilio.prod.twilio-docs/images/TwilioClientQuickstart.original.png)

## Meta

* No warranty expressed or implied. Software is as is. Diggity.
* [MIT License](http://www.opensource.org/licenses/mit-license.html)
* Lovingly crafted by Twilio Developer Education.
