
## Why Do We Write super(props) in Class based Component ?
     
      https://overreacted.io/why-do-we-write-super-props/






##
 -  never ever update the state variables directly these can only   be updated with the help of setState() which is Intoduced in Class Based components.
 - if I put a lot of state variables in this.state then setState will only change those which are used in this.setState to be changed. 
 ** when a functional component is reloaded if there is class based component then the constructor of that class is called first, and then render() is called.

 - when the class  Component is loaded first of all Constructor will be called then render methed,after that if there is any class based Component inside the render() method then the Constructor will be called (which is Child Component) then render () method after that componentDidMount() method will be called of that child class ,in the end 
 componentDidMount() method will be called of parent class.

  - in short ->
           parent constructor will be called first then
           parent render() method will be called then
           child constructor will be called then
           child render() method will be called then
           componentDidMount() of child will be called first 
           and then componentDidMount() of parent will be called in the end.
## benefit of componentDidMount() is to make APIs calls.
 but we make API call over here to componentDidMount() why?
  because React does not wait for the API to be called and return the data,so React wants to quickly render the component and then  API call is made via componentDidMount(). so that React component can be loaded fast, instead of waiting for the API call's data.


## componentWillUnmount()
   it helps to clean the mess in the component.
   suppose there is the setInterval() function in the componentDidMount() then componentWillUnmount() helps 
   to avoid the working of setInterval() by writting clearInterval()
   in componentWillUnmount(),even if I change the pages.
   because it is not reloading the pages ,it is just changing the components.
