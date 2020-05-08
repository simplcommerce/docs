# How to add new payment providers

---

The first thing you need to do is create a new module. See [how to add new module](how-to-add-new-modules.md) for more details

Then, add a new record to the 'Payments_PaymentProvider' table

- Name: name of your payment method
- LandingViewComponentName: the name of a view component (you will create it) which will be invoked in the checkout page.
- ConfigureUrl: this is the AngularJS route which will route to the setting page of your payment provider.
- AdditionalSettings: a json string that hold the setting value needed for the provider to work.
- IsEnabled: a boolean value that will decide whether the provider is showed in the checkout page.

Create an AngularJS form for the admin to configure your provider. This form will be routed to by the "ConfigureUrl". You can see existing provider such as Stripe or Paypal Express as examples. Then to the Admin --> System --> Payment Providers, your provider will show there.

Create a view component, this view component view be invoked in the checkout page. This component act as the entry point of your new payment provider.

Add a Controller to handle call back from the gateway. When you need to create the order, just call `await _orderService.CreateOrder(currentUser, "PaymentMethodName");`
