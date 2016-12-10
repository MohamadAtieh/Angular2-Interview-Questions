#### What would you consider a thing you should be careful doing on onNgInit()?

* https://angular.io/docs/ts/latest/guide/router.html#!#route-config (OBSERVABLE PARAMS AND COMPONENT RE-USE)

#### What is the possible order of lifecycle hooks?

1. ngOnChanges - Whenever Angular (re)sets data-bound input properties. It repeats whenever a data-bound property chnages.
2. ngOnInit - Initializes the directive after Angular displays the data-bound properties and sets the directive/components input properties. This hook is called only once.
3. ngOnCheck - Detect and act upon changes that Angular can't or won't detect on its own. This hook is called after every change detection (ngOnChanges).
4. ngAfterContentInit - Called after content is initialized into the view. This is called once after ngOnCheck.
5. ngAferContentChecked -  Responds after Angular checks the content projected into the component.
6. ngAfterViewInit - Responds after components views and child views initialized.
5. ngAfterViewChecked - Responds after Angular chcks the view and child views.
6. ngOnDestroy - Cleanup before ANgular destroys the directive/component. A good place to unsubscribe from observables/event listeners to avoid memory leaks.

https://angular.io/docs/ts/latest/guide/lifecycle-hooks.html#!#lifecycle-sequence


#### When will ngInit be called?

Called once, after the first ngOnChanges


#### How would you make use of onNgInit()?

Subscribing to an event emitter which can be used from child to parent communication, where the subscriber is the parent component handling the onNgInit hook and the child component being the emitter of the event. 