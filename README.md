# Swift interpretation of VIPER

Please keep in mind the objective of Separation of Concern.

Below are described the responsibilities of all layers presents in the VIPER design pattern / architecture:


V for View
----

The view is responsible for:

- displaying info to the user
- detecting user interaction


The view controller is responsible for:

- holding all attached (IBOutlet) UIView from its storyboard counterpart
- responding to its view-ing protocol
- holding the presenter instance


P for Presenter
----

The presenter is responsible for:

- holding the interactor instance
- telling the view what to display
- handling user events (such as clicking on a button) and dispatches to the interactor
- act as an integrity checker, before the interactor runs its logic, such as checking for non-empty fields
- does not act as a logic validator, such as checking if the street matches the city


I for Interactor
----

The interactor is responsible for:

- handling presenter requests
- acting as a logic validator
- interacting with data provider/manager
- performing business logic



### Summary

<b>The view</b> tells <b>the presenter</b> when user interaction events happen.

- <b>The presenter</b> can tell <b>the view</b>: "ok now, I can tell <b>the interactor</b> that I need some information from my service!".

*or*

-  <b>the presenter</b> can tell to <b>the view</b>: "oops, the email argument you pass me is not a valid email address, so display this message: 'invalid email address'".
