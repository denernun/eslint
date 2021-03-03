# eslint

## artigos

```code
https://github.com/angular-eslint/angular-eslint
https://dev.to/gsarciotto/migrating-and-configuring-eslint-with-angular-11-3fg1
https://dev.to/entangledcognition/migrating-from-tslint-to-es-lint-formating-with-prettier-vs-code-workspaces-4pgi
https://dev.to/dreiv/using-eslint-and-prettier-with-vscode-in-an-angular-project-42ib
https://medium.com/@kelmants/best-practices-angular-with-eslint-prettier-husky-50d12067831e
https://dev.to/bhargavmantha/the-secret-to-configuring-eslint-prettier-prettier-eslint-plugin-in-vscode-for-angular-ts-and-js-project-51la
https://indepth.dev/posts/1282/setting-up-efficient-workflows-with-eslint-prettier-and-typescript
```

## pacotes globais

```code
@angular-devkit/core
@angular-devkit/schematics
@angular-eslint/schematics
```

## converter

```code
ng add @angular-eslint/schematics
ng g @angular-eslint/schematics:convert-tslint-to-eslint app
npm rm tslint tslint-angular tslint-config-prettier tslint-plugin-prettier
```

## pacotes locais

```code
@typescript-eslint/eslint-plugin
@typescript-eslint/parser
prettier
eslint-plugin-prettier
eslint-config-prettier
```

## package

```json
"scripts": {
  "lint": "eslint --color --fix -c .eslintrc.json --ext .ts ./src/app",
  "lint-fix": "eslint --color --fix -c .eslintrc.json --fix --ext .ts ./src/app",
}
```

## .eslintrc.json

```
.eslintignore
node_modules
```

## .eslintrc.json

```json
{
  "root": true,
  "ignorePatterns": ["projects/**/*"],
  "overrides": [
    {
      "files": ["*.ts"],
      "parser": "",
      "parserOptions": {
        "project": ["tsconfig.eslint.json"],
        "createDefaultProgram": false
      },
      "plugins": [],
      "extends": [
        "plugin:@angular-eslint/recommended",
        "plugin:@angular-eslint/template/process-inline-templates",
        "plugin:@typescript-eslint/recommended",
        "plugin:@typescript-eslint/recommended-requiring-type-checking",
        "plugin:prettier/recommended"
      ],
      "rules": {
        "@angular-eslint/component-selector": [
          "error",
          {
            "type": "element",
            "prefix": "app",
            "style": "kebab-case"
          }
        ],
        "@angular-eslint/directive-selector": [
          "error",
          {
            "type": "attribute",
            "prefix": "app"
          }
        ],
        //
        // regras para ativar e verificar os erros e corrigir
        //
        "no-var": "off",
        "no-empty": "off",
        "no-restricted-syntax": "off",
        "no-alert": "off",
        "no-console": "off",
        "no-debugger": "off",
        "no-useless-constructor": "off",
        "no-useless-escape": "off",
        "eol-last": "off",
        "max-len": "off",
        "class-methods-use-this": "off",
        "no-case-declarations": "off",
        "semi": "error",
        "no-multi-spaces": "error",
        "space-in-parens": ["error", "never"],
        "no-multiple-empty-lines": "error",
        "prefer-const": "error",
        //
        // regras para ativar e verificar os erros e corrigir
        //
        "@typescript-eslint/require-await": "off",
        "@typescript-eslint/no-floating-promises": "off",
        "@typescript-eslint/promise-function-async": "off",
        "@typescript-eslint/no-misused-promises": "off",
        "@typescript-eslint/unbound-method": "off",
        "@typescript-eslint/no-extraneous-class": "off",
        "@typescript-eslint/no-explicit-any": [
          "off",
          { "fixToUnknown": false, "ignoreRestArgs": true }
        ],
        "@typescript-eslint/no-unsafe-member-access": "off",
        "@typescript-eslint/no-unsafe-assignment": "off",
        "@typescript-eslint/no-unsafe-call": "off",
        "@typescript-eslint/no-unsafe-return": "off",
        "@typescript-eslint/no-unused-vars": "off",
        "@typescript-eslint/explicit-module-boundary-types": "off",
        "@typescript-eslint/no-inferrable-types": "off",
        "@typescript-eslint/restrict-template-expressions": "off",
        "@typescript-eslint/interface-name-prefix": "off",
        "@typescript-eslint/explicit-function-return-type": "off",
        "@typescript-eslint/restrict-plus-operands": "off",
        "@angular-eslint/no-empty-lifecycle-method": "off",
        "@typescript-eslint/explicit-member-accessibility": [
          "off",
          {
            "accessibility": "explicit"
          }
        ],
        //
        // regras basicas do plugin
        //
        "arrow-parens": ["off", "always"],
        "brace-style": ["error", "1tbs"],
        "import/no-extraneous-dependencies": "off",
        "import/no-internal-modules": "off",
        "import/order": "off",
        "linebreak-style": "off",
        "newline-per-chained-call": "off",
        "no-duplicate-case": "error",
        "no-duplicate-imports": "off",
        "no-extra-bind": "error",
        "no-extra-semi": "off",
        "no-irregular-whitespace": "off",
        "no-new-func": "error",
        "no-redeclare": "error",
        "no-return-await": "error",
        "no-sequences": "error",
        "no-shadow": [
          "off",
          {
            "hoist": "all"
          }
        ],
        "no-sparse-arrays": "error",
        "no-template-curly-in-string": "error",
        "no-trailing-spaces": "off",
        "padding-line-between-statements": [
          "off",
          {
            "blankLine": "always",
            "prev": "*",
            "next": "return"
          }
        ],
        "prefer-object-spread": "error",
        "quote-props": "off",
        "space-before-function-paren": "off",
        //
        "@angular-eslint/use-component-view-encapsulation": "error",
        "@angular-eslint/use-pipe-decorator": "error",
        "@typescript-eslint/array-type": [
          "error",
          {
            "default": "array"
          }
        ],
        "@typescript-eslint/consistent-type-definitions": "error",
        "@typescript-eslint/dot-notation": "off",
        "@typescript-eslint/member-delimiter-style": [
          "off",
          {
            "multiline": {
              "delimiter": "none",
              "requireLast": true
            },
            "singleline": {
              "delimiter": "semi",
              "requireLast": false
            }
          }
        ],
        "@typescript-eslint/no-this-alias": "error",
        "@typescript-eslint/no-var-requires": "error",
        "@typescript-eslint/prefer-readonly": "off",
        "@typescript-eslint/semi": ["off", null],
        "@typescript-eslint/type-annotation-spacing": "off",
        //
        // eslint-config-prettier
        // https://github.com/prettier/eslint-config-prettier
        //
        "no-mixed-operators": "off"
      }
    },
    {
      "files": ["*.html"],
      "extends": ["plugin:@angular-eslint/template/recommended"],
      "rules": {}
    }
  ]
}
```

## tsconfig.eslint.json

```json
{
  "extends": "./tsconfig.json",
  "include": ["src/**/*.ts"]
}
```

## .prettierrc

```json
{
  "printWidth": 120,
  "tabWidth": 2,
  "singleQuote": true,
  "bracketSpacing": true,
  "endOfLine": "auto",
  "arrowParens": "always",
  "trailingComma": "es5",
  "semi": true,
  "overrides": [
    {
      "files": "*.html",
      "options": {
        "parser": "html"
      }
    },
    {
      "files": "*.css",
      "options": {
        "parser": "css"
      }
    },
    {
      "files": "*.scss",
      "options": {
        "parser": "scss"
      }
    },
    {
      "files": "*.json",
      "options": {
        "parser": "json"
      }
    },
    {
      "files": "*.ts",
      "options": {
        "parser": "typescript"
      }
    }
  ]
}
```

## settings

```
{
  "[html]": {
    "editor.defaultFormatter": "vscode.html-language-features",
    "editor.formatOnSave": true,
    "editor.formatOnPaste": false,
    "editor.formatOnType": false
  },
  "[css]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true,
    "editor.formatOnPaste": false,
    "editor.formatOnType": false
  },
  "[scss]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true,
    "editor.formatOnPaste": false,
    "editor.formatOnType": false
  },
  "[json]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true,
    "editor.formatOnPaste": false,
    "editor.formatOnType": false
  },
  "[jsonc]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true,
    "editor.formatOnPaste": false,
    "editor.formatOnType": false
  },
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true,
    "editor.formatOnPaste": false,
    "editor.formatOnType": false
  },
  "[typescript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true,
    "editor.formatOnPaste": false,
    "editor.formatOnType": false,
    "editor.suggest.showClasses": false
  },
}
{
  "eslint.format.enable": true,
  "eslint.alwaysShowStatus": true,
  "eslint.validate": [
    "typescript",
    "javascript",
    "html"
  ],
}
```

## settings formatter

```json
dbaeumer.vscode-eslint
esbenp.prettier-vscode
```

## novo aplicativo

```json
ng new --collection=@angular-eslint/schematics
```
