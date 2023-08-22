# For ts project

## yarn add -D jest @testing-library/jest-dom @testing-library/react @types/jest ts-jest ts-node

## create a file `setup-jest.ts`, put the following to it

``` import "@testing-library/jest-dom" ```

## create a file `jest.config.cjs`, put the following to it

```
/** @type {import('ts-jest').JestConfigWithTsJest} */
module.exports = {
  preset: "ts-jest",
  testEnvironment: "jsdom",
  // setupFilesAfterEnv: ["<rootDir>/setup-jest.js"],
  setupFilesAfterEnv: ["<rootDir>/setup-jest.ts"],
};
```
