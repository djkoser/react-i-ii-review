### Remember

Answer these on your own, then compare answers as a group

1.  What are props?

Props is an object containing  data passed from parent to child. They can be any data type, function or method. A parent component can add a key:value pair to the props object. 

1.  How do you pass props from a parent to a child?

props are passed from parent to child by assigning the value of the prop in the child's JSX tag. We set up the props on the child's component tag using curly braces.  

1.  How do you access props from a class based child component?
props are accessed using the this keyword, specifying this.props.myProps

2.  How do you access props from a functional component?

Props are accessed by including the props parameter in the function then referencing this as you would any other variable

1.  How do you bind a function to a parent component so that it can be passed to a child?

Within the constructor function, one would specify this. followed by the name off the function = this. name of the function .bind(this)

You can also use an arrow function in leiu of bind when the function is defined below the constructor. 

### Understand

Discuss this question in pairs if you have a 4-person group

6.  What's happening in this component?

This component is passing an askQuestion function to the Student component, and a answerQuestion function to the Mentor component. The askQuestion function allows the student component to update the parent's questions state. The answer Questions function allows the Mentor component to remove a question from its specified index from within the parents' questions state array. 

```jsx
import React, { Component } from "react";

class Queue extends Component {
  constructor(props) {
    super(props);

    this.state = {
      questions: []
    };

    this.askQuestion = this.askQuestion.bind(this);
    this.answerQuestion = this.answerQuestion.bind(this);
  }
  askQuestion(newQuestion) {
    const questions = [...this.state.questions, newQuestion];
    this.setState({ questions });
  }
  answerQuestion(index) {
    const questions = [...this.state.questions];
    questions.splice(index, 1);
    this.setState({ questions });
  }
  render() {
    <div className="queue-container">
      <h1>The Queue</h1>
      <h3>{this.state.questions.length}</h3>
      <h3>questions need answers</h3>
      <Student askQuestion={this.askQuestion} />
      <Mentor answerQuestion={this.answerQuestion} />
    </div>;
  }
}
```

### Apply

Try these on your own, but work together if you start to get stuck.

7.  Using the `Queue` component above, create a `Student` component that can add a question as a string and a `Mentor` component that can remove a question from the array.

```jsx
import React, { Component } from "react";

export default class Student extends Component {
  constructor () {
    super(props);
    this.state={
      studentInput:""
    }
  this.handleInput = this.handleInput.bind(this)
  }
    handleInput(value) {
      this.setState({
        studentInput:value
      })
    }
  return (
    <Input type ="text" value={this.state.studentInput} onChange={e=>this.handleInput(e.target.value)}></input>
  )
}
```
### Analyze, Evaluate, Create

Discuss these questions as a group

8.  In the Queue component above, why are we holding state in the Queue component instead of Mentor or Student?

Because this data can be easily passed to the student and mentor elements wihout triggering an event. 
