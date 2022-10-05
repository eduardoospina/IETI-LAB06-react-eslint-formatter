# IETI-LAB06-react-eslint-formatter

## Part 1: VSCode

![](https://i.postimg.cc/QCTCfXYd/vs-code-lab-1.png)

    1) Install Prettier plugin

![](https://i.postimg.cc/0r1Q3Lhd/vs-code-lab-2.png)

![](https://i.postimg.cc/bYWmCpwc/vs-code-lab-3.png)

    2) Install Eslint plugin

![](https://i.postimg.cc/g2q42hqm/vs-code-lab-4.png)

![](https://i.postimg.cc/nL3kvtPW/vs-code-lab-5.png)


![](https://i.postimg.cc/Hs0bwgJt/vs-code-lab-6.png)

## Part 2: Eslint

    1) Open your package.json, go down there on the eslintConfig and leave it as the next is:

    "eslintConfig": {
    	"extends": [
    		"eslint:recommended",
    		"react-app",
    		"react-app/jest",
    		"prettier"
    	]
    },

![](https://i.postimg.cc/XNd5Wbg0/vs-code-lab-7.png)

    2) run npm i -D eslint

![](https://i.postimg.cc/Hst7J9KZ/vs-code-lab-8.png)


    3) add this 2 new scripts to the package.json

    "lint": "eslint --ext .js,.jsx .",
    "lint:fix": "npm run lint -- --fix"

![](https://i.postimg.cc/P53pyrd1/vs-code-lab-9.png)

    4) If you installed eslint plugin the eslint errors will popup when you hover on warning messages on your code, for instance:

## Part 3: Prettier

    go to your package.json
    1) add a new key down below eslintConfig, like this:

    "prettier": {}

![](https://i.postimg.cc/ZqW9Mtq2/vs-code-lab-10.png)

    2) Go to file/preferences/settings another alternative is pressing on windows ctrl + ,
    3) On the User configuration open Text Editor / Formatting
    4) Click on Format On Save checkbox.

![](https://i.postimg.cc/6qfTvBH2/vs-code-lab-11.png)

## Part 4: Husky

    1) run npm i -D husky

![](https://i.postimg.cc/sfYM8JVj/vs-code-lab-12.png)

    2) run npm set-script prepare "husky install"

![](https://i.postimg.cc/4Nwm4N7j/vs-code-lab-13.png)

    3) run npm run prepare

![](https://i.postimg.cc/kgpG81yc/vs-code-lab-14.png)

    4) run npm i -D prettier

![](https://i.postimg.cc/YSL9x6nw/vs-code-lab-15.png)

    5) run npm set-script format "prettier --write ."

![](https://i.postimg.cc/bJQw7zfC/vs-code-lab-16.png)

    6) run npx husky add .husky/pre-commit "npm run lint:fix && npm format"

![](https://i.postimg.cc/mkBgR0bb/vs-code-lab-17.png)

    7) Now, every time you try to run a commit it will validate there are no eslint Errors ( Not warnings ), and then it will format every file on your project using our prettier config.
