# IETI-LAB06-react-eslint-formatter

## Part 1: VSCode

    Install Prettier plugin

    Install Eslint plugin

## Part 2: Eslint

    Open your package.json, go down there on the eslintConfig and leave it as the next is:

    "eslintConfig": {
    	"extends": [
    		"eslint:recommended",
    		"react-app",
    		"react-app/jest",
    		"prettier"
    	]
    },

    run npm i -D eslint
    add this 2 new scripts to the package.json

    "lint": "eslint --ext .js,.jsx .",
    "lint:fix": "npm run lint -- --fix"

    If you installed eslint plugin the eslint errors will popup when you hover on warning messages on your code, for instance:

## Part 3: Prettier

    go to your package.json
    add a new key down below eslintConfig, like this:

    "prettier": {}

    Go to file/preferences/settings another alternative is pressing on windows ctrl + ,
    On the User configuration open Text Editor / Formatting
    Click on Format On Save checkbox.

## Part 4: Husky

    run npm i -D husky
    run npm set-script prepare "husky install"
    run npm run prepare
    run npm i -D prettier
    run npm set-script format "prettier --write ."
    run npx husky add .husky/pre-commit "npm run lint:fix && npm format"
    Now, every time you try to run a commit it will validate there are no eslint Errors ( Not warnings ), and then it will format every file on your project using our prettier config.
