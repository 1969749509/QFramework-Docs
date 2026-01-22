# QFramework 核心方法 API

## 1. 容器注册类
| 方法名 | 所属接口 | 功能说明 | 参数 |
| :--- | :--- | :--- | :--- |
| `RegisterModel<T>` | IArchitecture | 注册一个数据模型 | 实例对象 |
| `GetModel<T>` | ICanGetModel | 获取指定的模型实例 | 无 |

## 2. 命令执行类
| 方法名 | 所属接口 | 功能说明 | 参数 |
| :--- | :--- | :--- | :--- |
| `SendCommand<T>` | ICanSendCommand | 执行业务逻辑命令 | 命令实例 |

## 3. 事件与监听
| 方法名 | 所属接口 | 功能说明 | 参数 |
| :--- | :--- | :--- | :--- |
| `SendEvent<T>` | ICanSendEvent | 发送全局通知 | 事件对象 |
| `Register<T>` | BindableProperty | 监听变量数值变化 | 回调函数 |

## 4.数据绑定 (BindableProperty)

实现“数据驱动 UI”的核心，类似你截图中的状态监听。

| **成员/方法**           | **说明**               | **示例**                    |
| ----------------------- | ---------------------- | --------------------------- |
| `Value`                 | 属性的值（读写）       | `HP.Value = 100;`           |
| `Register`              | 监听数值变化           | `.Register(val => { ... })` |
| `UnRegister`            | 取消监听               | `.UnRegister(onHPChanged)`  |
| `RegisterWithInitValue` | 监听并立即执行一次回调 | 常用于 UI 首次初始化        |
