objective-c-lambda-events
=========================

C# Lambda Events for Objective-c


C# Events with Lambdas are just so damned elegant at hooking up dynamic code to fire upon an event...and it turns out
we can have almost the same thing in objective-C with this library!

My hope is that this will spare developers from having to use the previous methods of 
 - NSNotificationCentre (pain to setup)
 - Delegate pattern (pain to setup, and file bloat)
 - Selectors (Pain to setup)

 

Usage:
- Declare property in model
    @property (nonatomic, strong) CCEventHandler* somethingChanged;
- initialize property in model
    _somethingChanged = [[CCEventHanlder alloc] init];
- Lambda style Hook to EventHandler in ViewController 

// Lambda style hookup event
## FooViewController
- (void) hookupToModel {

  [_model.somethingChanged addListener:self andExecute:^(id sender, CCEventArgs *args){
    // ** START Code that executes upon event goes here
    
    
    // ** END code that executes upon event
  }];


}





-Clint Johnson
cjohnson223@gmail.com
