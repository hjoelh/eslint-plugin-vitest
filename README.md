## eslint-plugin-vitest

![npm](https://img.shields.io/npm/v/eslint-plugin-vitest)
[![ci](https://github.com/veritem/eslint-plugin-vitest/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/veritem/eslint-plugin-vitest/actions/workflows/ci.yml)

Eslint plugin for vitest

### Installation

You'll first need to install [ESLint](https://eslint.org/):

```sh
npm i eslint --save-dev
```

Next, install `eslint-plugin-vitest`:

```sh
npm install eslint-plugin-vitest --save-dev
```

### Usage

Add `vitest` to the plugins section of your `.eslintrc` configuration file. You can omit the `eslint-plugin-` prefix:

```json
{
  "plugins": ["vitest"]
}
```

Then configure the rules you want to use under the rules section.

```json
{
  "rules": {
    "vitest/max-nested-describe": [
      "error",
      {
        "max": 3
      }
    ]
  }
}
```

#### Recommended

Make sure you're running eslint `v9.0.0` or heigher `eslint.config.js`

```js
import vitest from "eslint-plugin-vitest";

export default [
  {
    files: ["tests/**"], // or any other pattern
    plugins: {
      vitest,
    },
    rules: {
      ...vitest.configs.recommended.rules,
    },
    languageOptions: {
      globals: {
        ...vitest.environments.env.globals,
      },
    },
  },
];
```

#### Enabling with type-testing

Vitest ships with an optional [type-testing feature](https://vitest.dev/guide/testing-types), which is disabled by default.

If you're using this feature, you should also enabled `typecheck` in the settings for this plugin. This ensures that rules like [expect-expect](docs/rules/expect-expect.md) account for type-related assertions in tests.

```js
import vitest from "eslint-plugin-vitest";

export default [
  {
    files: ["tests/**"], // or any other pattern
    plugins: {
      vitest,
    },
    rules: {
      ...vitest.configs.recommended.rules,
    },
   settings: {
      vitest: {
        typecheck: true
      }
    },
    languageOptions: {
      globals: {
        ...vitest.environments.env.globals,
      },
    },
  },
]
```

### Rules

<!-- begin auto-generated rules list -->

💼 Configurations enabled in.\
⚠️ Configurations set to warn in.\
🌐 Set in the `all` configuration.\
✅ Set in the `recommended` configuration.\
🔧 Automatically fixable by the [`--fix` CLI option](https://eslint.org/docs/user-guide/command-line-interface#--fix).\
💡 Manually fixable by [editor suggestions](https://eslint.org/docs/latest/use/core-concepts#rule-suggestions).\
❌ Deprecated.

| Name                                                                                                                     | Description                                                           | 💼 | ⚠️ | 🔧 | 💡 | ❌  |
| :----------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------- | :- | :- | :- | :- | :- |
| [consistent-test-filename](docs/rules/consistent-test-filename.md)                                                       | require .spec test file pattern                                       |    | 🌐 |    |    |    |
| [consistent-test-it](docs/rules/consistent-test-it.md)                                                                   | enforce using test or it but not both                                 |    | 🌐 | 🔧 |    |    |
| [expect-expect](docs/rules/expect-expect.md)                                                                             | enforce having expectation in test body                               | ✅  |    |    |    |    |
| [max-expects](docs/rules/max-expects.md)                                                                                 | enforce a maximum number of expect per test                           |    | 🌐 |    |    |    |
| [max-nested-describe](docs/rules/max-nested-describe.md)                                                                 | require describe block to be less than set max value or default value |    | 🌐 |    |    |    |
| [no-alias-methods](docs/rules/no-alias-methods.md)                                                                       | disallow alias methods                                                |    | 🌐 | 🔧 |    |    |
| [no-commented-out-tests](docs/rules/no-commented-out-tests.md)                                                           | disallow commented out tests                                          | ✅  |    |    |    |    |
| [no-conditional-expect](docs/rules/no-conditional-expect.md)                                                             | disallow conditional expects                                          |    | 🌐 |    |    |    |
| [no-conditional-in-test](docs/rules/no-conditional-in-test.md)                                                           | disallow conditional tests                                            |    | 🌐 |    |    |    |
| [no-conditional-tests](docs/rules/no-conditional-tests.md)                                                               | disallow conditional tests                                            |    | 🌐 |    |    |    |
| [no-disabled-tests](docs/rules/no-disabled-tests.md)                                                                     | disallow disabled tests                                               |    | 🌐 |    |    |    |
| [no-done-callback](docs/rules/no-done-callback.md)                                                                       | disallow using a callback in asynchronous tests and hooks             |    | 🌐 |    | 💡 | ❌  |
| [no-duplicate-hooks](docs/rules/no-duplicate-hooks.md)                                                                   | disallow duplicate hooks and teardown hooks                           |    | 🌐 |    |    |    |
| [no-focused-tests](docs/rules/no-focused-tests.md)                                                                       | disallow focused tests                                                |    | 🌐 | 🔧 |    |    |
| [no-hooks](docs/rules/no-hooks.md)                                                                                       | disallow setup and teardown hooks                                     |    | 🌐 |    |    |    |
| [no-identical-title](docs/rules/no-identical-title.md)                                                                   | disallow identical titles                                             | ✅  |    | 🔧 |    |    |
| [no-import-node-test](docs/rules/no-import-node-test.md)                                                                 | disallow importing `node:test`                                        | ✅  |    | 🔧 |    |    |
| [no-interpolation-in-snapshots](docs/rules/no-interpolation-in-snapshots.md)                                             | disallow string interpolation in snapshots                            |    | 🌐 | 🔧 |    |    |
| [no-large-snapshots](docs/rules/no-large-snapshots.md)                                                                   | disallow large snapshots                                              |    | 🌐 |    |    |    |
| [no-mocks-import](docs/rules/no-mocks-import.md)                                                                         | disallow importing from __mocks__ directory                           |    | 🌐 |    |    |    |
| [no-restricted-matchers](docs/rules/no-restricted-matchers.md)                                                           | disallow the use of certain matchers                                  |    | 🌐 |    |    |    |
| [no-restricted-vi-methods](docs/rules/no-restricted-vi-methods.md)                                                       | disallow specific `vi.` methods                                       |    | 🌐 |    |    |    |
| [no-standalone-expect](docs/rules/no-standalone-expect.md)                                                               | disallow using `expect` outside of `it` or `test` blocks              |    | 🌐 |    |    |    |
| [no-test-prefixes](docs/rules/no-test-prefixes.md)                                                                       | disallow using `test` as a prefix                                     |    | 🌐 | 🔧 |    |    |
| [no-test-return-statement](docs/rules/no-test-return-statement.md)                                                       | disallow return statements in tests                                   |    | 🌐 |    |    |    |
| [prefer-called-with](docs/rules/prefer-called-with.md)                                                                   | enforce using `toBeCalledWith()` or `toHaveBeenCalledWith()`          |    | 🌐 | 🔧 |    |    |
| [prefer-comparison-matcher](docs/rules/prefer-comparison-matcher.md)                                                     | enforce using the built-in comparison matchers                        |    | 🌐 | 🔧 |    |    |
| [prefer-each](docs/rules/prefer-each.md)                                                                                 | enforce using `each` rather than manual loops                         |    | 🌐 |    |    |    |
| [prefer-equality-matcher](docs/rules/prefer-equality-matcher.md)                                                         | enforce using the built-in quality matchers                           |    | 🌐 |    | 💡 |    |
| [prefer-expect-assertions](docs/rules/prefer-expect-assertions.md)                                                       | enforce using expect assertions instead of callbacks                  |    | 🌐 |    | 💡 |    |
| [prefer-expect-resolves](docs/rules/prefer-expect-resolves.md)                                                           | enforce using `expect().resolves` over `expect(await ...)` syntax     |    | 🌐 | 🔧 |    |    |
| [prefer-hooks-in-order](docs/rules/prefer-hooks-in-order.md)                                                             | enforce having hooks in consistent order                              |    | 🌐 |    |    |    |
| [prefer-hooks-on-top](docs/rules/prefer-hooks-on-top.md)                                                                 | enforce having hooks before any test cases                            |    | 🌐 |    |    |    |
| [prefer-lowercase-title](docs/rules/prefer-lowercase-title.md)                                                           | enforce lowercase titles                                              |    | 🌐 | 🔧 |    |    |
| [prefer-mock-promise-shorthand](docs/rules/prefer-mock-promise-shorthand.md)                                             | enforce mock resolved/rejected shorthands for promises                |    | 🌐 | 🔧 |    |    |
| [prefer-snapshot-hint](docs/rules/prefer-snapshot-hint.md)                                                               | enforce including a hint with external snapshots                      |    | 🌐 |    |    |    |
| [prefer-spy-on](docs/rules/prefer-spy-on.md)                                                                             | enforce using `vi.spyOn`                                              |    | 🌐 | 🔧 |    |    |
| [prefer-strict-equal](docs/rules/prefer-strict-equal.md)                                                                 | enforce strict equal over equal                                       |    | 🌐 |    | 💡 |    |
| [prefer-to-be](docs/rules/prefer-to-be.md)                                                                               | enforce using toBe()                                                  |    | 🌐 | 🔧 |    |    |
| [prefer-to-be-falsy](docs/rules/prefer-to-be-falsy.md)                                                                   | enforce using toBeFalsy()                                             |    | 🌐 | 🔧 |    |    |
| [prefer-to-be-object](docs/rules/prefer-to-be-object.md)                                                                 | enforce using toBeObject()                                            |    | 🌐 | 🔧 |    |    |
| [prefer-to-be-truthy](docs/rules/prefer-to-be-truthy.md)                                                                 | enforce using `toBeTruthy`                                            |    | 🌐 | 🔧 |    |    |
| [prefer-to-contain](docs/rules/prefer-to-contain.md)                                                                     | enforce using toContain()                                             |    | 🌐 | 🔧 |    |    |
| [prefer-to-have-length](docs/rules/prefer-to-have-length.md)                                                             | enforce using toHaveLength()                                          |    | 🌐 | 🔧 |    |    |
| [prefer-todo](docs/rules/prefer-todo.md)                                                                                 | enforce using `test.todo`                                             |    | 🌐 | 🔧 |    |    |
| [require-hook](docs/rules/require-hook.md)                                                                               | require setup and teardown to be within a hook                        |    | 🌐 |    |    |    |
| [require-local-test-context-for-concurrent-snapshots](docs/rules/require-local-test-context-for-concurrent-snapshots.md) | require local Test Context for concurrent snapshot tests              | ✅  |    |    |    |    |
| [require-to-throw-message](docs/rules/require-to-throw-message.md)                                                       | require toThrow() to be called with an error message                  |    | 🌐 |    |    |    |
| [require-top-level-describe](docs/rules/require-top-level-describe.md)                                                   | enforce that all tests are in a top-level describe                    |    | 🌐 |    |    |    |
| [valid-describe-callback](docs/rules/valid-describe-callback.md)                                                         | enforce valid describe callback                                       | ✅  |    |    |    |    |
| [valid-expect](docs/rules/valid-expect.md)                                                                               | enforce valid `expect()` usage                                        | ✅  |    |    |    |    |
| [valid-title](docs/rules/valid-title.md)                                                                                 | enforce valid titles                                                  | ✅  |    | 🔧 |    |    |

<!-- end auto-generated rules list -->

#### Credits

- [eslint-plugin-jest](https://github.com/jest-community/eslint-plugin-jest)
	Most of the rules in this plugin are essentially ports of Jest plugin rules with minor modifications

### Licence

[MIT](https://github.com/veritem/eslint-plugin-vitest/blob/main/LICENSE) Licence &copy; 2022 - present [veritem](https://github.com/veritem)
