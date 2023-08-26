# For ts project

## step 1
run following command: 

``` yarn add -D jest ts-jest ts-node @types/jest @testing-library/jest-dom @testing-library/react jest-environment-jsdom ```

- `jest`: `test(), describe(), expect(), expect(value).toBe(4)` 
- `@testing-library/jest-dom`: `expect(element).toBeInTheDocument()`
  add custom matchers related to the dom
- `@testing-library/react`: `render(), screen()`
  query single element:
    - getBy
    - queryBy
    - findBy
  query multiple elements:
    - getAllBy
    - queryAllBy
    - findAllBy

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

## step 5
add following types to tsconfig.ts

```
{
    "types": ["node", "jest", "@testing-library/jest-dom"]
}
```
