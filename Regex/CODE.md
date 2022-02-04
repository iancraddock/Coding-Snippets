# RegEx Snippets

##### Strong Password (1 lowercase, 1 uppercase, 1 numeric, 1 special, at least 8 characters)

```
const example = new RegExp('^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9])(?=.*[!@#\\$%\\^&\\*])(?=.{8,})');
```
