#Module的语法

>   模块功能主要由两个命令构成：**export**和**import**。
export命令用于规定模块的对外接口，import命令用于输入其他模块提供的功能。

##export命令
>   一个模块就是一个独立的文件。该文件内部的所有变量，外部无法获取。如果你希望外部能够读取模块内部的某个变量，就必须使用export关键字输出该变量。

 1. **export输出变量**

    ```
    // profile.js
    var firstName = 'Michael';
    var lastName = 'Jackson';
    var year = 1958;
    export {firstName, lastName, year};
    ```

 2. **export输出函数或类（class）**
    ```
    // profile.js
    export function multiply(x, y) {
        return x * y;
    };
    ```

 3. **重命名**

    通常情况下，export输出的变量就是本来的名字，但是可以使用as关键字重命名。
    ```
    function v1() { ... }
    function v2() { ... }

    export {
      v1 as streamV1,
      v2 as streamV2,
      v2 as streamLatestVersion
    };
    ```
    上面代码使用as关键字，重命名了函数v1和v2的对外接口。重命名后，v2可以用不同的名字输出两次。
##import命令

使用export命令定义了模块的对外接口以后，其他 JS 文件就可以通过import命令加载这个模块。
```
// main.js
import {firstName, lastName, year} from './profile.js';

function setName(element) {
  element.textContent = firstName + ' ' + lastName;
}
```
上面代码的import命令，用于加载profile.js文件，并从中输入变量。import命令接受一对大括号，里面指定要从其他模块导入的变量名。大括号里面的变量名，必须与被导入模块（profile.js）对外接口的名称相同。

import后面的from指定模块文件的位置，可以是相对路径，也可以是绝对路径，.js后缀可以省略。如果只是模块名，不带有路径，那么必须有配置文件，告诉 JavaScript 引擎该模块的位置。