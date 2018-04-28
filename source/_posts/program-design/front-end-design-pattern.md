# MVC
## Life cycle

### Bootstrap

1. App Initial state
2. Create view object(which simultaneously call render view)

### MVC User interaction(For compare and contrast )
1. User interact(e.g click) view - **a action**
2. Controller analysis the action and called related model
3. Model changed
4. Controller get model newest state and passed necessary data to view to re-render

Disadv:

1. One Big Controller need to remember many view

2. Bad Programmer approach-(if the changing of model state occur only once && only one model related,they can direct change model state )
causing the data flow directly go to model **bypassing** the controller.Make **Bad Result Listed below**
  1. result in future related model and view don't know the state changed but they need to because the controller  by-passed(causing a bug)(Not OCP)
  2. hard to debug,the controller no longer only source that trigger model and view change(to many source,low readability and predictability)

3.Bad Programmer on renderView->the renderView will trigger app state on render ,it cause the container view loop forever.(that is really hard to debug)

### Good View in MVC

#### Must be stateless(At least never container the model state).

Adv:
1. increase predictability

Except
* if the view need some state
* controller calculate new state takes very long time and you can predict the new state without the model(temp view state)

#### Never effect model state when render
When render(newViewRelatedProps) is called

Adv:
1. Avoid infinite loop when app state changed.

#### Never direct change model state

Adv:
1. All another/future/related model can know the related state change.(OCP for new model and view)
2. Increase ease of debug,creating a single source of state change.

### P.S.

#### Terminology

Model state=>State that effect the business logic.

View state=>State that helps display

Model have zero or many view. View callback call the controller function.Not direct interacted with model

#### Converting jquery plugin to view component only by callback

1. Return false on plugin onchange event and called the controller.(By passing plugin model and disable it change value)
2. Ensure there is render view function and ensure it definitely don't trigger the model onchange event.
3. Some plugin really stop


## User interaction(Flux Perfect way)

1. a
2. s

## User interaction(Flux Inperfect way,view contains some state)





## MVVM User interaction(For compare and contrast )

1. User interact(e.g click) view - **a action**
2. Model changed
3. Observer render the model when it's state change and re-render

Disadv:

Data is bi-directional between model and view.It is very hard to predict the behaviour of application.E.g a view  
**Bad Result Listed below**
  1. nested view check dirty is hard to debug.very frequent to trigger infinite loop
