# mocha-browser-sample
一个使用了mocha，should, karma的单元测试示例


## 什么是Karma？

Karma是一个自动化的单元测试工具。
在没有Karma之前如果要在浏览器中执行mocha单元测试，需要在一个runner.html文件里引入各种js文件，然后用某个浏览器来打开这个html文件，使js在浏览器中运行起来。当测试内容发生变化时，需要刷新页面，并时不时地清空缓存。
使用karma可以把哪些些运行单元测试需要的手动工作变成自动化运行。


## 安装Karma
```npm install karma --save-dev```
```npm install karma-jasmine karma-chrome-launcher --save-dev```

执行上面两条命令会在当前工作目录中安装 karma、 karma-mocha 、karma-chrome-launcher 模块

# 创建Karma 配置文件
‘’‘karma init’‘’

根据命令提示选择单元测试框架，单元测试文件目录， 功能代码文件目录， 也可以使用默认值。

## 运行Karma

```./node_modules/karma/bin/karma start```


## 什么是Mocha？
Mocha是一个可以同时支持node环境和浏览器环境的单元测试框架，支持多种断言库,可以选择使用BDD还是TDD的API。


## 安装mocha
```$ npm install mocha -g```

## BDD

```
var assert = require("assert")
describe('Array', function(){
  describe('#indexOf()', function(){
    it('should return -1 when the value is not present', function(){
      assert.equal(-1, [1,2,3].indexOf(5));
      assert.equal(-1, [1,2,3].indexOf(0));
    })
  })
})
```


## TDD

```
var assert = require("assert")
suite('Array', function(){
  suite('#indexOf()', function(){
    test('should return -1 when the value is not present', function(){
      assert.equal(-1, [1,2,3].indexOf(5));
      assert.equal(-1, [1,2,3].indexOf(0));
    })
  })
})
```


## 什么是断言库
断言库用来验证代码的执行结果是否符合预期，nodejs自带的assert，第三方的should.js expect.js等

### 功能代码

```
utils = {

    add:function(a, b){
        return a + b;

    }
}

```
### should.js

```
describe('Untils', function(){
    describe('#add()', function(){
        it('add(1,2) should.equal(3)', function(){
            utils.add(1, 2).should.equal(3);
        })
    })
})

```
*utils.add(1, 2).should.equal(3)*

### expect.js

```
describe('Untils', function(){
    describe('#add()', function(){
        it('add(1,2) should.equal(3)', function(){
            expect(add(1,2)).to.equal(3)
        })
    })
})
```
*expect(add(1,2)).to.equal(3)*

## 参考文档
[http://mochajs.org/](mocha文档)
[https://mochacn.github.io](mocha中文文档)
[https://karma-runner.github.io/0.12/index.html][karma]










