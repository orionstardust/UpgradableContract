# UpgradableContract
How to upgrade contracts?

const proxy = await ethers.getContractAt("OwnableProxy", proxyAddr);
let newDeployedContract = await (await contractFactory.deploy()).deployed();
await proxy.upgradeTo(newDeployedContract.address);
await newDeployedContract.setProxy(proxy.address);
