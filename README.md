# MQToMQ

This is an MQToMQ message flow Application based on the framework from HttpJsonToHttpJson at https://github.com/sanketsw/HttpJsonToHttpJson.git
For the Application to deploy you must also include the common framework components anz-iib-commons from https://github.com/sanketsw/anz-iib-commons.git. You will also need to have your own MQ application, for this application to call. This can be as simple as creating a message flow with an MQ Input node connected to an MQ Reply node.

To test the message flow you must create a number of Websphere MQ message queues. These include: 
 -The Input queue for the MQ application you want to access, default name: PROVIDER 
 -The Response Queue, default name: RESPONSE

You can either create queues with these default names or change their default values in IBM Integration Bus to match your own queue names. To do the latter, open the Main.msgflow message flow in IIB and open the User Defined Properties tab. Click on each of providerQueue, replyQueue, and change the default values to your own queue names. Then open properties for the MQ Input node called Read Request and under Basic, change the Queue Name to your own value.

Use the following messages to test the message flow using the flow excerciser:

For a pass:

{ "left" : 7, "right" : 5 }

For a fail:

(empty)
