# Postman

URL携带查询参数的GET请求
发送表单的POST请求：request type选择x-www-form-urlencoded，添加相应表单数据。
支持上传文件的表单POST请求： request type选择form-data,添加file类型的key，上传文件。
JSON类型的接口请求：选择Body->raw-JSON

## 
## 变量
## 断言
Postman在Pre-Script Test 和 Test中可以添加自定义逻辑，Test中可以通过断言来进行返回值验证，为自动化测试提供了条件。Postman内置了一些JS库，提供了许多基础的断言。

### 常用断言
- 断言Response状态
  - 断言Response Status Code<br/>
    `pm.test("status code is 200", function(){`<br/>
    `pm.response.to.have.status(200);`<br/>
    `})`<br/>
  - 断言Response Status Message<br/>
    `pm.test("status code is OK", function(){`<br/>
    `pm.response.to.have.status("OK");`<br/>
    `})`<br/>
  - 断言Response Time<br/>
    `pm.test("Response Time is less than 200ms", function(){`<br/>
    `pm.expect(pm.response.ResponseTime).to.be.below(200);`<br/>
    `})`
- 断言Response Header属性
  - 断言Header中包含特定属性，例如Content-Type<br />
    `pm.test("Content Type is present", function() {`<br/>
    `pm.response.to.have.header("Content-Type");`<br/>
    `})`<br/>
- 断言Response Body
  - 断言Body中包含xxx字符串<br />
    `pm.test("Body matches string", function(){`<br/>
    `pm.expect(pm.response.text()).to.include("xxx");`<br/>
    `})`<br/>
  - 断言Body等于xxx字符串<br />
    `pm.test("Body is correct", function(){`<br/>
    `pm.response.to.have.body("xxx");`<br/>
    `})`<br/>
  - 断言Body（JSON）中某个键名对应的值<br/>
    `pm.test("your test name", function(){`<br/>
    `var jsonData = pm.response.json();`<br />
    `pm.expect(jsonData.name).to.eql("tom");`<br/>
    `})`<br/>
    
### 常用断言实例
1. 状态响应码为200
2. 返回对象包含Scope所预先定义的属性
3. 返回对象中特定属性的值为期望值



# 软件测试类型
## 从测试设计方式分类
- Black Box 黑盒：把软件当成一个黑箱，从软件的行为而不是内部结构出发的测试。
- White Box 白盒：设计者可以看到软件的内部结构，根据对结构的掌握指导测试数据及方法的选择。
- Gray Box  灰盒：介于黑白盒之间。
白盒测试要求测试人员有很多的编程经验，对代码/结构有比较深的了解。

## 从测试是手动还是自动分类
- Manual Test
- Auto Test
对于项目来说，手动测试与自动化测试同样重要，都是保证软件质量的有利方法，缺一不可。自动化测试在业务流程清晰、界面/业务耦合性低的场景。例如Web Services、Web API都非常适合自动化测试。

## 从测试的目的分类

### 功能测试
- Unit Test: 在函数级别添加的test，确保函数功能的正确性（开发人员自己写）
- Functional Test：验证模块的功能（测试人员进行）
- Integration Test：验证相互依赖模块间的交互功能（测试人员进行）
- Scenario Test：验证几个模块是否能完成一个完整的场景（测试人员进行）
- System Test：对于整个系统功能的测试（测试人员进行）
- Alpha & Beta Test：测试人员及客户在真实客户环境（UAT/Stage/Prod)上进行的测试。

### 非功能性测试
- Stress Test: 验证软件在超过负载的情况下仍能返回结果，而不会崩溃。
- Load Test：测试软件在各种负载的情况下能否正常工作。
- Performance Test：测试软件的性能，是否能提供满意的服务。比如QTP、LoadRunner、Jmeter。Visual Studio也提供了很多性能测试的工具。
- Accessibility Test：软件辅助功能测试，VPAT（测试软件是否向残疾用户提供足够的辅助功能）
- Localization/Globalization Test: 本地化/国际化
- Compatibility Test：兼容性测试
- Configuration Test：配置测试，测试软件在各种配置下能否正常工作。
- Usibility Test：可用性测试。测试软件是否好用。
- Security Test：软件安全测试。覆盖面很广，一般由专业第三方负责。

## 按测试的时机分类
- Smoke Test: 冒烟测试。如果测试不通过，则不能进行下一步工作。
- Build Verification Test (BVT): 验证build是否通过验证。
- Acceptance Test: 验收测试，为了全面考核某功能/特性而做的测试。

## 按测试策略分类
- Regression Test（回归测试）: 对一个新的版本，重新运行以往的测试用例，以判断新版本在功能上是否退化。[最好是自动化的]
- Ad Hoc Test: 探索性测试
- Sanity Test: 粗略测试，只需要执行部分的测试用例。


