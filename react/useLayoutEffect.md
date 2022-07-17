To bring it down to a rule, you use `useEffect` almost all of the time, and you `useLayoutEffect` if the side effect that you are performing makes an observable change to the DOM that will require the browser to paint that update that you've made.

If you need to update DOM and you use `useEffect`, it will do its job after the browser already painted itself so it rerenders after it runs your `useEffect`.
To prevent that, use `useLayoutEffect` so it will do your changes before it even paints the DOM so there would be no unnecessary rerender.
