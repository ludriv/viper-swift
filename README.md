# Swift interpretation of VIPER

Please keep in mind the separation of concern.

Below, the responsibilities of all layers presents in the VIPER design pattern / architecture:


V for View
----

The view is responsible to:

- display info to the user
- detect user interaction


The view controller is responsible to:

- hold all attached (IBOutlet) UIView from its storyboard part
- respond to its view-ing protocol
- hold the presenter instance


P for Presenter
----

The presenter is responsible to:

- tell the view what to display
- handle user events (like clicking on a button for example) and translate to interactor instruction
- hold the interactor instance
- act as (soft) form validator: before the interactor work: checks for non-empty fields for example


I for Interactor
----

The interactor is responsible to:

- handle presenter request
- interact with data provider/manager
- perform business logic



In other words:

<b>The view</b> tells to <b>the presenter</b> tap/click events happen.

<b>The presenter</b> can tell to <b>the view</b>: "ok now, I can tell to <b>the interactor</b> that I need some info from my service!".

Or <b>the presenter</b> can tell to <b>the view</b>: "oops, the email argument you pass me is not a valid email address, so display this message: 'invalid email address'".
