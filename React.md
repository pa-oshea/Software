### useEffect
Only use when synchronizing with an non-react external source. E.g: API call. database

example of not using effects to set data
```javascript
  let [entityNameId, setEntityNameId] = useState(null);
  let [inputValue, setInputValue] = useState("");
  let [multiItemValues, setMultiItemValues] = useState([]);

  let entityNames = useMemo(() => mapEntityNames(configData), [configData]);

  let entityNameValue = entityNameId || entityNames[0]?.value;

  let tableData = useMemo(() => getTokensTableData(entityNameValue, configData), [entityNameValue, configData]);
```

### useState

Updater function, if you do multiple updates within the same event, updaters can be helpful. They’re also helpful if accessing the state variable itself is inconvenient . 
```jsx
setState((prevState) => {
	return {
		...prevState,
		updatedValue: value
	}
})
```

#### Caveats[](https://react.dev/reference/react/useState#setstate-caveats "Link for Caveats")

- The `set` function **only updates the state variable for the _next_ render**. If you read the state variable after calling the `set` function, [you will still get the old value](https://react.dev/reference/react/useState#ive-updated-the-state-but-logging-gives-me-the-old-value) that was on the screen before your call.
    
- If the new value you provide is identical to the current `state`, as determined by an [`Object.is`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/is) comparison, React will **skip re-rendering the component and its children.** This is an optimization. Although in some cases React may still need to call your component before skipping the children, it shouldn’t affect your code.
    
- React [batches state updates.](https://react.dev/learn/queueing-a-series-of-state-updates) It updates the screen **after all the event handlers have run** and have called their `set` functions. This prevents multiple re-renders during a single event. In the rare case that you need to force React to update the screen earlier, for example to access the DOM, you can use [`flushSync`.](https://react.dev/reference/react-dom/flushSync)
    
- Calling the `set` function _during rendering_ is only allowed from within the currently rendering component. React will discard its output and immediately attempt to render it again with the new state. This pattern is rarely needed, but you can use it to **store information from the previous renders**. [See an example below.](https://react.dev/reference/react/useState#storing-information-from-previous-renders)
    
- In Strict Mode, React will **call your updater function twice** in order to [help you find accidental impurities.](https://react.dev/reference/react/useState#my-initializer-or-updater-function-runs-twice) This is development-only behavior and does not affect production. If your updater function is pure (as it should be), this should not affect the behavior. The result from one of the calls will be ignored.