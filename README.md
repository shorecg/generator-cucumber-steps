
> A package that generates step definitions in javascript based on cucumber feature files

![demo](http://i.imgur.com/Wh078Pu.gif)

## Installation

```bash
npm install -g yo
npm install -g generator-cucumber-step-definitions
```
OR

```bash
yarn global add yo
yarn global add generator-cucumber-step-definitions
```
## Executing

```bash
~/.yarn/bin/yo
```
Then select `Cucumber Step Definitions`
 
Select path to the feature-file (without file extension).
Next, select the location you want the step definitions file to be generated.

## Examples

```gherkin
Feature: title
  Scenario: title
    Given precondition with "1" and "2"
    When action
    And addition
    Then testable outcome equals "1"
```
If you have same feature with parameters, you'll recieve:

```javascript
const {defineSupportCode} = require('cucumber');

defineSupportCode(function ({Given, When, Then}) {
  Given(/^precondition with "(.*)" and "(.*)"$/, function (param1, param2) {
    return true;
  });
  When(/^action$/, function () {
    return true;
  });
  And(/^addition$/, function () {
    return true;
  });
  Then(/^testable outcome equals "(.*)"$/, function (param1) {
    return true;
  });
});
```

## License

MIT ©
