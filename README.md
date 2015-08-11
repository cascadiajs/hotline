# Hotline - a Phone/SMS Hotline Application

## Intro

This application was initially built to give attendees of [CascadiaFest 2015](http://2015.cascadiajs.com) an easy way to contact staff in the event they needed assistance. 

## Requirements

* [Twilio](http://twilio.com) Account
* Provisioned Twilio phone number
* Provisioned TaskRouter Workspace

## Set-up (Initial)

1. Create a new TaskRouter Workspace. Use the `Fifo` template.
2. Create a Worker for each staff member that will help resolve issues. Make sure the following JSON is defined in the textbox: `{"contact-uri": "+1xxxyyyzzzz", "name": "First Last"}`.


## Deployment

Prior to running the app, make sure the following environment variables are configured in your production environment:

```
TWILIO_ACCOUNT_SID
TWILIO_AUTH_TOKEN
TWILIO_WORKSPACE_SID
TWILIO_WORKFLOW_SID
TWILIO_ACTIVITY_IDLE_SID
```

You can deploy this application to your Node hosting provider of choice. Please note sure fully-qualified URL for your hosted Node app. 

## Set-up (Final)

1. Select the phone number that you'd like to use and configure its `Messaging Request URL` to point at `https://yourserver:port/sms`.
2. Edit the Workflow in your Workspace. Set the `Assignment Callback URL` to `https://yourserver:port/assignment`.

That's it! 
