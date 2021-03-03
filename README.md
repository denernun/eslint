# eslint

## artigos

<https://github.com/angular-eslint/angular-eslint>
<https://dev.to/gsarciotto/migrating-and-configuring-eslint-with-angular-11-3fg1>
<https://dev.to/entangledcognition/migrating-from-tslint-to-es-lint-formating-with-prettier-vs-code-workspaces-4pgi>
<https://dev.to/dreiv/using-eslint-and-prettier-with-vscode-in-an-angular-project-42ib>
<https://medium.com/@kelmants/best-practices-angular-with-eslint-prettier-husky-50d12067831e>
<https://dev.to/bhargavmantha/the-secret-to-configuring-eslint-prettier-prettier-eslint-plugin-in-vscode-for-angular-ts-and-js-project-51la>
<https://indepth.dev/posts/1282/setting-up-efficient-workflows-with-eslint-prettier-and-typescript>

## rules

<https://www.npmjs.com/package/@typescript-eslint/eslint-plugin>

## pacotes globais

```code
@angular-devkit/core
@angular-devkit/schematics
@angular-eslint/schematics
```

## pacotes locais

```code
eslint
@typescript-eslint/eslint-plugin
@typescript-eslint/parser
prettier
eslint-plugin-prettier
eslint-config-prettier
```

## converter

```code
ng add @angular-eslint/schematics
ng g @angular-eslint/schematics:convert-tslint-to-eslint app
npm rm tslint tslint-angular tslint-config-prettier tslint-plugin-prettier
```
