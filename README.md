# swordpool rule beta

# before u swap check this https://dogim.gitbook.io/dogim/


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
* 请注意如果你同时有dogim和dogi，dogim的tick和dogi的tick相当目前不支持区分，如果你想卖你不可能赢两次，所以你最好自己做决定。We neither recognize nor support Dogi. Please help me translate into English.

# Swordpool Rule (Beta Version)
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
* Please note that if you have both Dogim and Dogi, the ticks for Dogim and Dogi are currently not distinguishable. If you intend to sell, you cannot profit twice, so it's advisable for you to make your own decision. We neither recognize nor support Dogi. Please help me translate into English.

