# react-boilerplate
A basic boilerplate with some additional loaders and plugins

Loaders: Style, CSS, PostCSS, JSON, Babel

Plugins: HTMLWebpackPlugin, HMR

## react (quickly)
### components

```javascript
import React, { Component } from 'react';
import ChildComponent from './ChildComponentFile';

class ThisComponent extends Component {
  
  constructor() {
    super(...arguments);
    this.state = {
      aStateVar: false
    };
  }
  
  render() {
    var aVar = this.props.propPassedFromParentComponent.map((value) => {
      return <ChildComponent setAProp={value.property1}
                             setBProp={value.propertyb} />
    });
    
    let thisComponentDetails;
    if(this.state.aStateVar) {
      thisComponentDetails = (
        <divOrSomeElement className="someClass">
          {this.props.anotherPropFromParent}
          <ChildComponent setAnotherPropToPassToChild="more values" />
        </divOrSomeElement>
      )
    };
    
    return (
      <divOrSomeElement className="someOtherClass">
        <divOrSomeElement className="thisComponentsOtherProp" onClick={
          ()=>this.setState({aStateVar: !this.state.aStateVar})>
          {this.props.otherProp}
        </divOrSomeElement>
        {thisComponentDetails}
      </divOrSomeElement>
    );
  }
}

export default ThisComponent;
```
