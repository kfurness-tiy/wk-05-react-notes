# Install react
  * React Single File:  [react-<version>.js][reactDown]
  * React DOM library: [react-dom-<version>.js][reactDown]

# Instal including JSX
  * Babel library
    * Download Babel
    * Change <script type="text/javascript"> to <script type="text/babel">

# What is react
  * react is a way to integrate html into your javascript to help create the view

# render
  * function that must be implemented
  * provides the output that the user sees (the "view")

# Components
  * reusable
  * can be nested
  * what you use to break your interface into its most basic parts
  * DOM component = in HTML
  * CompositeComponent = create by React.createClass()
  * controlled components: Have value property
    value = value
    component's state = event handler
  * uncontrolled components: do NOT have value property
    value = application (in render)
    component's state = application (in render via defaultValue)

# Component Creation
  1. getDefaultProps()  //Do not use with ES6
    * prop values returned will be used as DEFAULTS
    * ES6 Alternative:
      * use .defaultProps property in class
      ```js
      MyReactClass.defaultProps = {
        name: 'Bob',
        initialCount: 0
        };
      ```
  2. getInitialState()  //Do not use with ES6
    * return value = intial state of React component
    * ES6 Alternative:
      * use this.state in constructor
      ```js
      constructor(props){
        super(props);

        this.state = {
          count: this.props.initialCount
        };
        }
      ```
  3. componentWillMount()  
    * used to make final changes to the component before add to DOM
  4. render()  
    * returns a single element that represents the component
  5. componentDidMount()
    * component mounted and can now access component's DOM nodes
    * used for: preparing times, fetching data, adding event listeners

# Component Modification
  * componentWillUnmount()
    * used before a component is unmounted from DOM
    * Good for: removing event listeners
  * componentWillReceiveProps(nextProps)
    * FIRST function for property changes
    * for property changes!
      * access old = this.props
      * access new = nextProps.
      * Can compare these props
  * shouldComponentUpdate(nextProps, nextState)
    * SECOND function for property changes
    * FIRST function for state changes
    * returns true if prop/state changes made to render new version of your component
  * componentWillUpdate(nextProps, nextState)
    * Changes not made in DOM yet
  * componentDidUpdate(prevProps, prevState)

# component states
  * Anytime a component's state changes, its 'render' function is called
  * represented as js object on a component level scope
  * it is like private data for your component
  * has properties in it
  * setState() : primary way to make UI updates, does shallow merge btwn new and previous state & trigger a re-render of component


# props
  * [Components pass properties to their children components through props][resource]
    * Property ex. Address, Price, etc.
  * <Component title={prop}/>   // is a prop
  * Can use props to nest
  * used to pass data and methods from a parent component to a child component
  * immutable
  * allow to create reusable components
  * Default props
    * Set default values for your component props
    * Component.defaultProps = {...}  //ES6
  * Prop Types
    * Specify what props your component needs and the type they should be
      ```js
      MyClass.propTypes = {
      randomObject: React.PropTypes.object,
      callback: React.PropTypes.func.isRequired,
      };
      ```

  React.PropTypes.whatTypeItShouldBe = {...} //ES6


[reactDown]:https://facebook.github.io/react/docs/installation.html
[resource]:https://html5hive.org/react-tutorial/
