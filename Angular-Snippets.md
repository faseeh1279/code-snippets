# Default Angular Stand-alone Behavior 
#### 1. Open `angular.json` file. 
#### 2. Find the schematics section. 
#### 3. Modify the `@schematics/angular:component` settings by setting `"standalone":false`. 
```bash 
{
    "schematics": {
        "@schematics/angular:component": { 
            "standalone":false
        }
    }
}

```