---
Status: "#knowledge-base"
tags:
  - "#knowledge-base"
  - javascript
  - "#formatting"
  - "#prettier"
  - linting
area: javascript
cover: https://gitlab.com/idahogurl/vs-code-prettier-eslint/-/raw/5b0d100df2eef87a3cb8ec7d8e125f6c5e5e6a9b/icon.png
type: article
progress: Idea
draft: "false"
title: Enhance Code Quality and make your code Pretty with ESLint and Prettier
---
![ESLintPrettierIcon](https://gitlab.com/idahogurl/vs-code-prettier-eslint/-/raw/5b0d100df2eef87a3cb8ec7d8e125f6c5e5e6a9b/icon.png)


# ESLint vs Prettier: Enhancing Code Quality and Consistent Formatting

#formatting #javascript #linting #prettier 


### Intro

In modern JavaScript development, tools like ESLint and Prettier play a crucial role in maintaining code quality and ensuring consistent code formatting. While they have overlapping functionalities, understanding when to use each tool and how they complement each other is essential. In this blog post, we will dive into the definitions of ESLint and Prettier, explore their use cases, and discuss how they can be used together to achieve optimal results.

### Context

We use ESLint and Prettier to easily format and lint our JavaScript based projects

## Overview
*What does this article consists of*

- [[ESLint Prettier#Intro|Introduction]]
- [[ESLint Prettier#Prettier Vs ESLint|ESLint Vs. Prettier]]
- [[ESLint Prettier#When to Use Each Tool|When To Use Each Tool]]
- [[ESLint Prettier#Using ESLint and Prettier with VSCode|Using with VSCode]]
- [[ESLint Prettier#Conclusions|Conclusions]]



### Prettier Vs ESLint
#### ESLint - Your Code Quality Guardian 
ESLint is a linter that analyzes your code, identifies potential errors, enforces coding conventions, and helps maintain best practices. It provides a customizable set of rules to catch common bugs and improve code quality. ESLint supports various plugins and configurations, making it adaptable to different frameworks like React and libraries like TypeScript. It can be integrated into your development workflow, running as a command-line tool or as a plugin in your code editor.

#### Prettier - Consistent Code Formatting Made Simple 
Prettier is a code formatter that automatically formats your code based on a specified code style. It simplifies the formatting process by parsing your code and reprints it according to its own rules. Prettier takes care of indentation, line breaks, spacing, and more, ensuring a consistently formatted codebase. It supports multiple programming languages, including JavaScript and TypeScript. Like ESLint, Prettier can be integrated into your workflow as a command-line tool or a code editor plugin.

#### When to Use Each Tool

- Use Prettier for Code Formatting: Prettier excels at ensuring consistent code formatting throughout your project. It allows you to define a set of code style rules, such as line length, indentation, and spacing. Prettier automatically formats your code, saving you the time and effort of manually adjusting code styling details. By adopting Prettier, you can enforce a unified and professional coding style across your entire team.

- Use ESLint for Code Quality: While Prettier focuses on code formatting, ESLint helps improve code quality and maintain best practices. ESLint identifies potential errors, catches bugs, and enforces coding conventions specific to your project. It can detect unused variables, incorrect imports, and other code issues that might not be related to code formatting. By incorporating ESLint into your development process, you can catch bugs and maintain a high level of code quality throughout your codebase.

**Using ESLint and Prettier Together** ESLint and Prettier can be used in conjunction to achieve maximum benefits for your codebase. By combining these tools, you can ensure both code quality and consistent formatting. Here are some tips for using ESLint and Prettier together:

1. Rule Configuration: 
	1.  **Compatibility**: Ensure that the rules in your ESLint configuration do not conflict with Prettier's code formatting rules. You can prevent conflicts by turning off ESLint formatting-related rules (e.g., indentation, spacing) and letting Prettier handle them.
	2. **Collaborative Configuration**: Set up an ESLint configuration that extends Prettier to ensure that both tools work well together. This way, ESLint catches code issues, while Prettier handles code formatting.

3. Running Order: 
	1. **Prettier First**: Configure your development environment to run Prettier before ESLint. This prevents any formatting changes made by Prettier from being reversed by ESLint. 
	2. **Integration into the Editor**: Install Prettier and ESLint extensions in your code editor, such as Visual Studio Code, to get real-time feedback, automatic formatting, and displays of code issues as you code.

By leveraging the power of ESLint and Prettier together, you can benefit from automated code formatting, enhanced code quality, and adherence to coding standards and conventions.



### Using ESLint and Prettier with VSCode
To use Prettier and ESLint in VSCode with React and Typescript projects, follow these steps:

1. Install the necessary dependencies:
    - Open your project in the terminal and run the following command to install ESLint, Prettier, and ESLint-config-prettier as dev dependencies: `npm install -D eslint prettier eslint-config-prettier` or `yarn add -D eslint prettier eslint-config-prettier`. 
2. Initialize ESLint in your project:
    - Run `npx eslint --init` or `yarn eslint --init` in the terminal.
    - Choose "To check syntax, find problems, and enforce code style" as the option for how you would like to use ESLint.
    - Select "JavaScript modules (import/export)" as the type of modules your project uses.
    - Choose "React" as the framework your project uses.
    - Select whether your project uses TypeScript or not. 

3. Install additional ESLint plugins (optional):
    - To control UI updates in React Hooks, install the eslint-plugin-react-hooks plugin by running `npm install -D eslint-plugin-react-hooks` or `yarn add -D eslint-plugin-react-hooks`.
    - Add the following configuration to your `.eslintrc.json` file:

```json
{ 
	"extends": [ "..some-other-config-you-use", "plugin:react-hooks/recommended", "prettier" ] }
```


4. Configure ESLint to work with Prettier:
    - Add "prettier" to the "extends" array in your `.eslintrc.*` file, ensuring it is the last item in the array. This allows Prettier to override other configurations.
```json
{ "extends": [ "..some-other-config-you-use", "prettier" ]
```



5. Set up Prettier:
    - Create a `.prettierrc.json` file at the root of your project.
    - Configure Prettier according to your preferences. Here's an example:

```json
{ "semi": true, "singleQuote": true, "trailingComma": "es5", "arrowParens": "avoid", "endOfLine": "lf" }
```

6. Configure VSCode to use Prettier as the default formatter:
    - Open your VSCode settings (JSON) by pressing `Cmd + Shift + P` or `Ctrl + Shift + P` and typing "Preferences: Open Settings (JSON)".
    - Add the following configuration:
```json
{ "editor.formatOnSave": true, "editor.defaultFormatter": "esbenp.prettier-vscode" }
```




### Conclusions


ESLint and Prettier are both essential tools in JavaScript development. ESLint helps maintain code quality by catching bugs and enforcing coding conventions, while Prettier ensures consistent code formatting with minimal effort. By combining these tools and configuring them intelligently, you can achieve codebases that are not only well-formatted but also maintain high code quality standards. The integration of ESLint and Prettier in your development workflow can lead to cleaner, more maintainable code and improved collaboration within your development team.








---
# References

Guides, docs, videos