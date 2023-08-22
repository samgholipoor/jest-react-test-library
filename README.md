# For ts project

## step 1
run following command: 

``` yarn add -D jest @testing-library/jest-dom @testing-library/react @types/jest ts-jest ts-node ```

## step 2
create a file `setup-jest.ts`, put the following to it:

``` import "@testing-library/jest-dom" ```

## step 3
create a file `jest.config.ts`, put the following to it:

```
/** @type {import('ts-jest').JestConfigWithTsJest} */
module.exports = {
  preset: "ts-jest",
  testEnvironment: "jsdom,
  setupFilesAfterEnv: ["<rootDir>/setup-jest.ts"],
};
```

## step 4
add following script to package.json:

```
"test": "jest"
```
