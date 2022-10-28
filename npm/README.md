# NPM Snippets

##### Run an NPM Audit against a specific registry

```
npm audit --registry=https://registry.npmjs.org
```

##### Update all packages (dependencies & devDevpendencies)

```
npm update --save/--save-dev
```

##### Outdated packages (dependencies & devDevpendencies)

```
npm outdated
```

##### Update all packages to latest (dependencies & devDevpendencies) - NOTE: this will include breaking changes, so be sure to check the package.json

```
npm outdated | awk 'NR>1 {print $1"@"$4}' | xargs npm install
```

