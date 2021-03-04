### Remember

Answer these on your own, then compare answers as a group

1.  What is React?
React is a Javascript library from the developers of Facebook for building user interfaces leveraging  component-based architecture and a virtual DOM. 
1.  What is create-react-app?
Create-react-app is a tool created by Facebook that allows one to quickly obtain and install the components necessary to build apps in React.js and sets up a developer server that will autorefresh on change. 
3.  What is Component Based Architecture?
Component-based architecture is the seaparation of website elements into seperate reusable compoenents, each with their own functionality and state. It allows for easier debugging, code reuse and team collaboration.
4.  What is JSX?
JSX is a syntax extension of Javascript that allows one to write HTML-like code from within JavaScript. Classes and events are camelCased and curly braces denote JavaScript code.  It is eventually transpiled into regular JavaScript function calls. In additino to React, it is used in a number of other languages.   
1.  What is the virtual DOM?
The virtual DOM is a component of React.js that allows changes made to site HTML to be buffered into a lightweight copy of the actual DOM prior to applying only the changes that need to be made to the viewing window every time changes are made to a component. 
1.  What is unidirectional (one-way) data flow?
Unidirectional data flow denotes a pattern in React.js whereby information can only be passed from parent components to child components in the form of props. This ensures we have a 'single source of truth', i.e there is only one instance of the value (email, etc.) within the webserver.   
### Understand

Discuss these questions in pairs if you have a 4-person group

7.  Summarize what happens when you run `create-react-app my-app`
This command creates a new react app boiler plate named my-app and installs the necessary components in into a folder within the current working directory named my-app.
1.  Explain what this code does:
This code creates a parent <div> a <h1> and two unordered list items within an unordered list container

```jsx
import React from "react";

const Mentor = props => (
  <div className="mentor-container">
    <h1 className={props.title === "Lead Mentor" ? "lead" : ""}>Tim Biles</h1>
    <ul>
      <li>Fort Worth, TX</li>
      <li>My email address is timbilestimbiles@gmail.com</li>
    </ul>
  </div>
);

export default Mentor;
```

1.  Explain how data is passed from a parent component to a child component.

Data is passed from parent components to child components by passing props
### Apply

Try these on your own, but work together if you start to get stuck.

10.  Use `create-react-app` to create a new React application called `student-directory`



11.  Use the code from `Mentor` above to create a new functional, stateless component called `User` with a list of friends. Hard code the list of friends, do not use state or props.

### Analyze, Evaluate, Create

Discuss these questions as a group

1.  What are the benefits and drawbacks of using a tool like create-react-app?
Pros
You don't need to configure anything, you can just focus yourself on building the app.
Saves a lot of time and energy as it provides a lot of common things out of the box.
Training a newcomer about your project is easy. You just need to train them about the project and point them to the create-react-app documentation for setup and configuration.
As it is maintained by Facebook, support for new features of React will be available immediately.
Updating to a new version is super easy. Just replace the version of react-scripts in package.json and run npm install. That's it.
Speaking of updating, as create-react-app takes care of handling under the hood things, updating things like webpack and babel will be taken care by them. We don't need to hassle with it again.
Cons
It provides an opinionated option for building a react app. Not everyone will like that.
It helps only if you are starting a project from scratch. It won't help on the case of your existing application where you need to partially migrate to react.

2.  Compare and contrast JSX with other templating options, such as those used in Angular or Vue
3.  

4.  Compare and contrast one-way data flow with two-way data binding.
