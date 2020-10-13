# Reproduce bug
## Run
```
npx lerna bootstrap
npx lerna exec npm run build
cd packages/myapp
npx cdk synth
```
## Output
```
unable to determine cloud assembly output directory. Assets must be defined indirectly within a "Stage" or an "App" scope
```


# Steps to recreate this setup

* Create a lerna project
* Create two new CDK projects, one `app` and one `lib` in `packages/`
* Create a `Function` instance in both CDK projects
* Instantiate the `lib` Construct in the `app` project
* Synth the cdk template in the `app` project