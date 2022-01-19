# VS Code

Hide `js` files when a TypeScript file exists.

```json
"files.exclude": {
  // Hide all .js files when have a .ts file
  "**/*.js": {"when": "$(basename).ts"},
  "**/*.js.map": true,
  "node_modules/": true // optional
}
```
