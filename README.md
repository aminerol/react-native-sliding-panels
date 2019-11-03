# React Native Sliding panel - Android and IOS
An Awesome fully Customizable library of react native for sliding panels purely implemented in Javascript. Works exceptionally well on **android and ios**.

This repo is Forked from the react-native-sliding-up-down-panels and add ability to slide from right or the left

![Alt text](Example/screenshots/slidingpanelios.gif)

# Features (What makes this library different)

> #### *Easily Assemble itself into your react native project*
> #### *One library for both sliding up, down, right, left panel*
> #### *Customizable Animatable and Draggable.*
> #### *Extremely simple usage and implementation.*
> #### *Provides maximum methods for dealing with every scenarios in sliding panels.*
> #### *Constantly updating and improvizing to provide best experience to all the developers.*

# Installation

```
npm install react-native-sliding-panels --save
```

Copy and paste into the terminal in your project directory. For more information on npm install, please visit their [official page](https://docs.npmjs.com/getting-started/installing-npm-packages-locally)


# Minimal Example

#### Before start please note : 

 1. Always Put flex: 1 on the root container component style in which you are using < SlidingPanel />.
  2. if u sliding either from right or top Always use prop **headerLayoutHeight** to mention the height of the sliding panel header,
     and for sliding from right or left Always use prop **headerLayoutWidth** to mention the width of the sliding panel header

```
import React, { Component } from 'react';
import {
  StyleSheet,
  Text,
  View,
  Dimensions,
} from 'react-native';
const { width, height } = Dimensions.get('window');

import SlidingPanel from 'react-native-sliding-panels';


export default class App extends Component {
  render() {
    return (
      <View style={styles.container}>                      
        
        <View style={styles.bodyViewStyle}>
          <Text>Hello My World</Text>
        </View>
        
        <SlidingPanel
            headerLayoutHeight = {100}
            headerLayout = { () =>
                <View style={styles.headerLayoutStyle}>
                  <Text style={styles.commonTextStyle}>My Awesome sliding panel</Text>
                </View>
            }
            slidingPanelLayout = { () =>
                <View style={styles.slidingPanelLayoutStyle}>
                  <Text style={styles.commonTextStyle}>The best thing about me is you</Text>
                </View>
            }
        />
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
  },
  bodyViewStyle: {
    flex: 1,
    justifyContent: 'center', 
    alignItems: 'center',
  },
  headerLayoutStyle: {
    width, 
    height: 100, 
    backgroundColor: 'orange', 
    justifyContent: 'center', 
    alignItems: 'center',
  },
  slidingPanelLayoutStyle: {
    width, 
    height, 
    backgroundColor: '#7E52A0', 
    justifyContent: 'center', 
    alignItems: 'center',
  },
  commonTextStyle: {
    color: 'white', 
    fontSize: 18,
  },
});

```
If you are wrapping header layout inside a view, please make sure the height of that view is equal to headerLayoutHeight prop for sliding from up or bottom.

If you are wrapping header layout inside a view, please make sure the width of that view is equal to headerLayoutWidth prop for sliding from right or left.

# Props


| Property | Type | Description | Platform
| --- | --- | --- | --- |
| headerLayoutHeight | number | Header height of sliding panel | android, ios
| headerLayoutWidth | number | Header width of sliding panel | android, ios
| headerLayout| function | Header Layout of sliding panel | android, ios
| slidingPanelLayout | function | Panel Layout of sliding panel | android, ios
| AnimationSpeed | number | Animation speed, (in millisecond) | android, ios
| slidingPanelLayoutHeight |number | Panel height of sliding panel | android, ios
| slidingPanelLayoutWidth |number | Panel width of sliding panel | android, ios
| panelPosition | string | "top" or "bottom" or "left" or "right" | android, ios
| visible | booolean | to show/hide sliding panel | android, ios
| allowDragging | booolean | allow sliding panel to drag | android, ios
| allowAnimation | booolean | allow sliding panel to animate | android, ios
| onDragStart | function(event, gestureState) | returns event, gestureState | android, ios
| onDragStop | function(event, gestureState) | returns event, gestureState | android, ios
| onDrag | function(event, gestureState) | returns event, gestureState | android, ios
| onAnimationStart | function | triggers when panel animation starts | android, ios
| onAnimationStop | function | triggers when panel animation stops | android, ios


# Methods

| Method Name | Description | Platform
| --- | --- | --- |
| onRequestStart | panel animation starts, sliding panel opens | android, ios
| onRequestClose | panel animation stops, sliding panel stops | android, ios