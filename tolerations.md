we can add tolerations for [[taint]] Under [[spec]] sections
```yaml
specs:
	tolerations:
	- key: "app"
	   operator :"equal"
	   value: "blue"
	   effect: "No Schedule"
```


