# 介绍  
一个使用合约发送 ERC20 红包的小程序 

## 使用步骤  
- 配置环境环境变量  
```shell
cp .env.exmpale .env

## 在 .env 文件中配置 PRIVATE_KEY, INFURA_ID, PROJECT_ID, TARGET_ACCOUNT
## 其中 TARGET_ACCOUNT 为可以领取红包的账户地址 
```

- 安装依赖  
```shell
yarn
```

- 部署 ERC20 合约  
```shell
npx hardhat run scripts/deploySimpleToken --network kovan
```

- 部署 RedPacket 合约  
```shell
npx hardhat run scripts/deployHappyRedPacket --network kovan 
```

- 创建 红包  
```shell
npx hardhat run scripts/createRedPacket --network kovan 
```

- 进行签名   
```shell
npx hardhat run scripts/signMessage

## 得到的输出 "Sign Message:" 即为领取红包时需要输入的签名信息，防止恶意领取
```

- 领取红包  
在 Etherscan 上验证合约后，即可通过 Etherscan 调用 claim 方法进行领取