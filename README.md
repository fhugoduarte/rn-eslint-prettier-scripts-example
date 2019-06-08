# Eslint && Prettier Config Example

Sample project for eslint and prettier configuration in a React Native project.

#### Dependencies ####

I recommend installing these dependencies as developer dependencies, you will not need them in production.

* [babel-eslint](https://github.com/babel/babel-eslint)
* [babel-preset-react-native](https://www.npmjs.com/package/babel-preset-react-native)
* [eslint](https://github.com/eslint/eslint)
* [eslint-config-airbnb](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb)
* [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier)
* [eslint-plugin-import](https://github.com/benmosher/eslint-plugin-import)
* [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier)
* [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react)
* [eslint-plugin-react-native](https://github.com/intellicode/eslint-plugin-react-native)
* [husky](https://github.com/typicode/husky)
* [lint-staged](https://github.com/okonet/lint-staged)
* [prettier](https://github.com/prettier/prettier)

#### Installation ####

You can run these commands on your terminal.

##### npm ######

```npm install babel-eslint babel-preset-react-native eslint eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-prettier eslint-plugin-react eslint-plugin-react-native husky lint-staged prettier --save-dev```

##### yarn ######

```yarn add --dev babel-eslint babel-preset-react-native eslint eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-prettier eslint-plugin-react eslint-plugin-react-native husky lint-staged prettier```

#### Eslint Rules ####


  To configure the eslint rules you must create a [.eslintrc](https://github.com/fhugoduarte/rn-eslint-prettier-scripts-example/blob/master/.eslintrc) file at the root of your project. This file will have the rules you want to add to your project. I'm using airbnb standards but feel free to add your own rules.
 
 Obs: You can verify that I have disabled some rules in my configuration file, so feel free to customize it however you want.
 
 #### Prettier ####
 
To format and facilitate in an incredible way your life, we can configure some format preferences with the prettier, I particularly use the following settings:

```
{
  "printWidth": 80,
  "singleQuote": true,
  "arrowParens": "always",
  "trailingComma": "all"
}
```

But you are free to add your settings to prettier, just create a [.prettierrc](https://github.com/fhugoduarte/rn-eslint-prettier-scripts-example/blob/master/.prettierrc) file at the root of your project and add your preferences.

#### Pre-Commits Scripts ####

If your project has other developers, I recommend adding pre-commit scripts. 
It's very easy, just add these lines in your package.json

```
{
  ...,
 "scripts": {
  ...,
  "precommit": "lint-staged",
  "pretty": "prettier --write \"src/**/*.js\"",
  "lint": "eslint src"
  },
  ...,
  "lint-staged": {
    "*.js": [
      "yarn pretty",
      "yarn lint",
      "git add"
    ]
  },
  ...
}
```

Therefore, whenever the user adds a commit, the prettier will automatically format all .js files that have been modified and eslint will check to see if they all follow the configured patterns. If any code does not fit in these settings the eslint will show the error in a very clear way.

#### Contact ####

**Email:** h.duarte222@gmail.com <br />
[LinkedIn](https://www.linkedin.com/in/hugo-duarte-3392bb153/)
