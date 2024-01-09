# swordpool rule beta
# before u swap check this https://dogim.gitbook.io/dogim/

# Liquidity Management Rules
* We tested two models and ultimately abandoned the model that generated interest from liquidity. Instead, we adopted another buy/sell model.
* For instance, if I have confidence in a certain token A and am less optimistic about token B in my possession, I will inject token B into the pool. This way, when the price of A increases, I will be able to acquire more A because I attract more people to buy B, and the pool does not charge a 1% fee at that time.
* The system sets a removal operation to be executed after 360 blocks.
* The calculation formula is x * (current_balance_a / current_balance_b). Compared to other models, this may result in uncompensated losses. Similarly, this type of model carries the risk of overselling but promotes the frequency of trading.
* When you decide to withdraw your earnings, it will be calculated based on the current balance and the formula mentioned above. However, there is a risk of overselling, for example, when the balance of token A in the pool is insufficient to provide the profits you could gain, at which point you will be unable to withdraw.
* Please remember that the liquidity you provide has a 360-block time limit, and you will only receive the opposing token. For example, if you add liquidity with token B to acquire token A.
* Please be aware that when you engage in trading, you are confirming your acceptance of our rules. In the event of any significant short-term fluctuations, you assume the risk.
* The system is still under adjustment. For example, if this model is not deemed reasonable, we will consider adjusting the rules and algorithms.
* When adding liquidity, in order to identify transactions, we will charge a fee of 10 Doge to add and 1.42 Doge for remove
* and min token doge liq it's 10000 doge and min other liq it's 100000

# 流动性管理规则
* 我们测试了两种模型，最终抛弃了添加流动性产生利息的模型。取而代之的是另外一种买/卖模型
* 例如 我看好某个代币 A 不看好我手中的 B ，为此我将代币 B 注入池子，这样当 A 的价格升高后，我将可以换得更多的 A，因为我让更多人去买B，并且此时池子不在收取 1% 手续费用。
* 此时系统设定了 360 个区块后执行移除操作。
* 计算公式为 x * (current_balance_a / current_balance_b) , 相比于其他模型会产生无偿损失，同样的这类模型也有超卖的风险，但会促进交易发生的频率
* 当你决定回收利益的时候，会按照当前余额及以上公式计算所得，但是会出现超卖的风险，例如池中的代币 a 余额不足以提供你所能获得的收益时，此时你将无法撤出
* 请记住你提供的流动性有360个区块时限并且只会收到对手代币，例如 你添加流动性 b 是为了获得 a
* 请注意当你进行交易时证明你同意了我们的规则，出现任何短期内的剧烈波动，请自担风险
* 系统仍然在调整中，例如如果这个模型不够合理，我们会考虑调整规则及算法。
* 添加流动性时为了识别交易我们会收取 5 个doge，移除时会收取1.42个doge

# swap rule
* 往池子规定的地址，转池子定义的drc20或者doge的交易会被识别为交易行为
* 由于drc20无法分割成小数，为此设置了粉尘交易类型，即交易数量小于最小交易数额的比如，2个doge以下或者10个drc20类型数量以下的会被认为是粉尘交易，将不计入交易会直接纳入池子。
* 单比交易不可超过池子的50%，超过会回滚交易也就是打回原地址，并扣除3%
* 单比手续费为1%
* 计算公式 以 doge swap dogim 为例 input_doge * (balance_b/(balance_a+input_doge)) //取整数，input_doge 等于扣掉手续费及 0.1或者0.3个gas
* 交易到账有几个区块延迟，beta测试期间可能会更严重，后期会优化到账时间
* 余额以区块计算，每个区块都会根据交易情况计算实时余额，兑换数量按交易的区块余额计算价格（公式参考uniswap的合约，但是要扣除doge网络的手续费也就是gas）
* 池子会初始化一定比例的余额（测试期间由社区志愿提供，提出时按当前池子余额和投入的比例计算），后期会加上自由加入池子的功能。
* 池子目前只用于beta测试，所以池子余额相对较少
* 请注意，余额是随区块变化的，而前台显示无法测算你的交易在哪个区块确认，所以价格显示会有差异，请注意，投资有风险！！！
* 因为索引不同，请注意如果你同时有dogim和dogi，dogim的tick和dogi的tick相当目前不支持区分，如果你想卖你不可能赢两次，所以你最好自己做决定。We neither recognize nor support Dogi.

# swap rule
## This rule is exclusively for the Swardpool beta testing. Pool transactions are intended solely for technical research and development testing purposes.
## Rule adjustments and maintenance may occur at any time during the testing period, so please pay attention to announcements (please be aware of the risks, as issues may arise during the testing phase).

* Due to development progress issues, front-end operations currently only support the exchange of DOGE for other assets. Other transactions involving the exchange of DRC20 tokens for DOGE must be manually completed by sending to the pool address. Your understanding is appreciated.Transactions sent to the designated pool address will be recognized as transaction activities and can be exchanged for the DRC20 or DOGE defined by the pool.
* Since DRC20 tokens cannot be divided into fractions, a dust transaction type has been set up. Transactions with quantities below the minimum transaction amount, for example, less than 2 DOGE or less than 10 DRC20 tokens, will be considered dust transactions and will be directly included in the pool without being counted as transactions.
Individual transactions cannot exceed 50% of the pool, and exceeding this limit will result in a rollback of the transaction to the original address, with a 3% deduction.
* The transaction fee for a single transaction is 1%.
* There may be a delay in transaction confirmation, especially during the beta testing period, but the confirmation time will be optimized in the later stages.
Balances are calculated based on blocks, with each block calculating the actual balance based on transaction activity. Exchange quantities are calculated based on the block balance of transactions.
* The pool will initialize a certain proportion of balances (provided by community volunteers during the testing period, calculated based on the current pool balance and the contribution ratio). Additional functionality for freely joining the pool will be added in the future.
* The pool is currently only used for beta testing, so the pool balance is relatively low.
* Please note that the balance fluctuates with the blocks, and the front-end display cannot determine the confirmation of your transaction in a particular block. Therefore, there might be discrepancies in price display. Please be aware, investment carries risks!!!
* Because of different indexer, Please note that if you have both Dogim and Dogi, the ticks for Dogim and Dogi are currently not distinguishable. If you intend to sell, you cannot profit twice, so it's advisable for you to make your own decision. We neither recognize nor support Dogi.

