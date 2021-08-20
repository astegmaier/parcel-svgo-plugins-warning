# parcel-svgo-plugins-warning

This repo illustrates [an issue with `parcel` `2.0.0-rc.0`](https://github.com/parcel-bundler/parcel/issues/6744) where `parcel build` will output a deprecation warning.

## Repro steps

1. Clone the repo.
2. Run `yarn` to install dependencies
3. Run `yarn build`

### Result
You'll see this output:
```
console: 
"extendDefaultPlugins" utility is deprecated.
Use "preset-default" plugin with overrides instead.
For example:
{
  name: 'preset-default',
  params: {
    overrides: {
      // customize plugin options
      convertShapeToPath: {
        convertArcs: true
      },
      // disable plugins
      convertPathData: false
    }
  }
}
```
Note: you have to have a clean cache to see this - if you run `yarn build` again (with a `.parcel-cache` folder from the last build), you won't see it. Run `yarn clean` to remove the cache.
