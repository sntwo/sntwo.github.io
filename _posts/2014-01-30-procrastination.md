---
layout: post
title: procrastination
tags:
- useful functions
---
found on [stackoverflow](http://stackoverflow.com/questions/24034544/dispatch-after-gcd-in-swift/24318861#24318861)

```swift
func delay(delay:Double, closure:()->()) {
    dispatch_after(
        dispatch_time(
          DISPATCH_TIME_NOW,
          Int64(delay * Double(NSEC_PER_SEC))
        ),
       dispatch_get_main_queue(), closure)
}
```

used like this:

```swift
delay(1.0){
  delayedFunction() //runs after 1.0 seconds
}
```
