# monorepo example - typescript+vite+react

explore intuitive way of using monorepo

features:
- directly run/build, no need to build lib first
- all code linked to source cross packages in IDE (at least vscode works)


## start

```
npm run start -w workspace-main

# or

cd workspacce-main && npm run start 
```

## build your own

```
# ---- npm part ----
# init root
cd /path/to/project_root
npm init -y

# init packages
npm init -w ./packages/a
npm init -w ./packages/b

# install new dependency for package
npm i {pkg_name} -w ./packages/a -S

# init dependency relation
npm i ./packages/b -w ./packages/a -S
# config main in package.json, example `src/index.tsx`

# ---- typescript part ----

# shared config for `baseUrl`,`paths`,`references` at root level, refer `./tsconfig.json`
vi tsconfig.json

# extend base config and add local config for packages, refer `./workspace-main/tsconfig.json`
vi ./packages/b/tsconfig.json

```