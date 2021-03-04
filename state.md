### Remember

Answer these on your own, then compare answers as a group

1.  What is state?
State is private data stored on individual components that is managed by that component. This state is data that might change, and should help the component do its job. 
1.  Where do you set initial state?
The initial state is set within the constructor function within the state object. 
2.  What method do you use to update state?
this.setState() using an object as an argument that specifies our targeted properties that need to be changed, along with their new values

### Understand

Discuss this question in pairs if you have a 4-person group

4.  Explain what's happening in this component.
A component named LeadMentor is defined which renders the number of questions answered by Tim Biles with an increase answers button to add to this questionsAnswered state and reflect this change in the dom. 
```jsx
import React, { Component } from "react";

class LeadMentor extends Component {
  constructor(props) {
    super(props);

    this.state = {
      questionsAnswered: 0
    };

    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    this.setState({ questionsAnswered: this.state.questionsAnswered + 1 });
  }
  render() {
    <div className="lead-mentor-container">
      <h1>Tim Biles</h1>
      <h3>{this.state.questionsAnswered}</h3>
      <h3>questions answered today</h3>
      <button onClick={this.handleClick}>Increase Answers</button>
    </div>;
  }
}
```

### Apply

Try these on your own, but work together if you start to get stuck.

5.  Create a `Student` component that keeps track of the number of questions the student has asked, with a button that adds 1 to the total when it's clicked

Same as above. 

6.  Now add a text input where the student can type in their questions with a button to add them to a list of questions that is displayed below the number of questions asked.

import React, { Component } from "react";

class Student extends Component {
  constructor(props) {
    super(props);

    this.state = {
      questionsAnswered: 0,
      questionsArray: [],
      userInput: ""
    };

    this.handleClick = this.handleClick.bind(this);
  }
  handleClick() {
    let temp
    this.setState({ 
      questionsAnswered: this.state.questionsAnswered + 1,
      questionsArray: });
  }
  render() {
    <div className="lead-mentor-container">
      <h1>Tim Biles</h1>
      <h3>{this.state.questionsAnswered}</h3>
      <h3>questions answered today</h3>
      <h3>Question</h3>
      <input placeholder = 'Please add your question'></input>
      <button onClick={event=>this.handleClick(event.target.value)}>Add Question</button>
    </div>;
  }
}

### Analyze, Evaluate, Create

Discuss these questions as a group

7.  Could your `Student` component be refactored into a functional component? Why or why not?

No because functional components cannot keep track of state. 

8.  What are the pros and cons of using a class method for an event handler vs. using an arrow function inline?



9.  The render() method is called every time a component's state is updated. For a text input, that means the render method is called for every keypress. Why isn't this bad for performance?
