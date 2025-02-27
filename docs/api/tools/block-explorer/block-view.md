# 浏览区块

![Browse blocks!](../../../assets/images/block-tx.png "View blocks on zkSync")

默认情况下，区块浏览器的主页显示链上的最近 10 个区块。
查看所有区块以获得最近区块的更完整概述，或单击特定的区块编号以获取有关该区块的详细信息。
区块页面也可以通过顶部菜单访问。

![Access the block page](../../../assets/images/block-menu.png "Blocks menu")

## 查看所有区块

您可以单击区块编号以查看该特定块的所有详细信息。如果您想浏览更多区块，请点击导航菜单中的 [区块](https://explorer.zksync.io/blocks/)。使用分页导航到下一页。

然而，如果您已经离开主页，您可以随时通过输入区块编号来搜索任何区块。

![Browse all blocks](../../../assets/images/view-block.png "Browse all blocks")

一个区块内有两个主要部分：

1. 区块头
- 这显示了有关此特定区块的简要信息，以及指向链上前一个区块的链接。
2. 交易
- 由包含在此区块中的所有交易的列表组成。

![Single block page!](../../../assets/images/single-block.png "View a single block")


### 区块头

下表应该有助于解释您在区块中看到的内容。
有关区块的更多详细信息，请参阅 [区块](../../../dev/developer-guides/transactions/blocks.md)。

| 值    | 描述                           |
| ---- | ---------------------------- |
| 区块编号 | 此区块的唯一序号。                    |
| 区块大小 | 区块的大小。                       |
| 出块时间 | 以 Unix 格式开始算起区块的生成时间（以秒为单位）。 |
| 根哈希  | 区块头的加密哈希。                    |
| 状态   | 区块的状态，可能是“封闭”，“已完成”或“未完成”。   |

### 交易

该部分列出了该区块中包含的所有交易。
交易是以先进先出的方式提供的，但在未来，我们将引入“优先堆”（priority heap），允许对交易进行排序。

| 值    | 描述                                                     |
| ---- | ------------------------------------------------------ |
| 区块   | 一个区块中的交易数量。                                            |
| 出块时间 | 以 Unix 格式开始算起区块的生成时间（以秒为单位）。                           |
| 哈希   | 交易的哈希值作为交易的 ID。                                        |
| 从    | 发送交易的账户或智能合约。                                          |
| 至    | 交易对象的账户或智能合约。                                          |
| 费用   | 处理该交易的费率。                                              |
| 代币转移 | 交易中涉及的代币细节（包括 `to` 和 `from` 地址），包括资产，钱包地址余额和代币地址等详细信息。 |
| 合约地址 | 网络收取的费率。                                               |

