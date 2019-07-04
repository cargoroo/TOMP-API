Events
Events are our way of letting you know when something interesting happens in your account. When an interesting event occurs, we create a new Event object. For example, when a charge succeeds, we create a charge.succeeded event; and when an invoice payment attempt fails, we create an invoice.payment_failed event. Note that many API requests may cause multiple events to be created. For example, if you create a new subscription for a customer, you will receive both a customer.subscription.created event and a charge.succeeded event.

Events occur when the state of another API resource changes. The state of that resource at the time of the change is embedded in the event's data field. For example, a charge.succeeded event will contain a charge, and an invoice.payment_failed event will contain an invoice.

As with other API resources, you can use endpoints to retrieve an individual event or a list of events from the API. We also have a separate webhooks system for sending the Event objects directly to an endpoint on your server. Webhooks are managed in your account settings, and our Using Webhooks guide will help you get set up.

When using Connect, you can also receive notifications of events that occur in connected accounts. For these events, there will be an additional account attribute in the received Event object.

NOTE: Right now, access to events through the Retrieve Event API is guaranteed only for 30 days.

https://resthooks.org/docs/
Method	Route	About
GET	/api/v1/subscription/	list subscriptions
POST	/api/v1/subscription/	create a subscription
GET	/api/v1/subscription/:id/	get a subscription
PUT	/api/v1/subscription/:id/	update a subscription
DELETE	/api/v1/subscription/:id/	delete a subscription

Must be renewed on each request?
Must be a POST method when sent
Must contain auth header to ensure validity
https://github.com/cloudevents/spec/blob/master/http-webhook.md
