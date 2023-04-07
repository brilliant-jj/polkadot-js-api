#用Polkadot JS API订阅事件
1. 安装Polkadot JS API
```bash
npm install --save @polkadot/api
```
2. 导入 Polkadot JS API
```js
const { ApiPromise, WsProvider } = require('@polkadot/api');
```
3. 连接到一个 Polkadot 节点
```js
const wsProvider = new WsProvider('wss://kusama-rpc.polkadot.io');
const api = await ApiPromise.create({ provider: wsProvider });
```
4. 订阅事件
```js
api.query.system.events((events) => {
    events.forEach((record) => {
        console.log(record.event.data.toString());
    });
});
```
