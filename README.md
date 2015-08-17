# Animating CALayer with spring effect in iOS with Swift.

This demo app shows how to do spring animation on CALayer. Animation is similar to UIView's method `animateWithDuration(_:delay:usingSpringWithDamping:...)`.

## Usage

1. Copy [SpringAnimation.swift](https://github.com/evgenyneu/SpringAnimationCALayer/blob/master/SpringAnimationCALayer/SpringAnimation.swift) file to your project.
1. Animate your CALayer's property by calling `SpringAnimation.animate` function.

For example, let's rotate a layer around its X axis in perspective:

```Swift
var transform = CATransform3DIdentity
transform.m34 = -1.0/100.0
myCALayer.transform = CATransform3DRotate(transform, CGFloat(M_PI), 1, 0, 0)

SpringAnimation.animate(myCALayer,
  keypath: "transform.rotation.x",
  duration: 2.0,
  usingSpringWithDamping: 0.7,
  initialSpringVelocity: 1.8,
  fromValue: 0,
  toValue: Double(M_PI),
  onFinished: nil)
```

Currently animation looks similar to UIView's method.
But the `duration`, `usingSpringWithDamping` and `initialSpringVelocity` values
are different from those in UIView's method.

## Formula

Here is the formula that I am currently using for animation. 

<img src='https://raw.githubusercontent.com/evgenyneu/SpringAnimationCALayer/master/graphics/graph/spring_with_damping_formula.png' width='473' alt='Spring animation formula'>


## The Goal

The goal of this project is to make this CALayer's animation work **exactly** like UIView's for the same arguments.

> Help me, Finn and Jake. You're my only hope.

## •ᴥ•

<img src='https://raw.githubusercontent.com/evgenyneu/SpringAnimationCALayer/master/graphics/calayer_animation.gif'  alt='Spring animation for CALayer in iOS with Swift'>
