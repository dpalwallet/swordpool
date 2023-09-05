# swordpool rule beta

## 该规则仅用于 swardpool 池子 beta 测试，池子交易只用于技术研发测试
## 测试期间会随时调整维护，请注意公告（请注意风险，测试期间可能会出现问题）
## 由于开发进度问题，目前前台操作只支持 doge 换 其他的页面操作，其他drc20类型的换doge的交易，只能通过往池子地址手动转完成。请谅解

* 往池子规定的地址，转池子定义的drc20或者doge的交易会被识别为交易行为
* 由于drc20无法分割成小数，为此设置了粉尘交易类型，即交易数量小于最小交易数额的比如，2个doge以下或者10个drc20类型数量以下的会被认为是粉尘交易，将不计入交易会直接纳入池子。
* 单比交易不可超过池子的20%（为提高可持续性调整为5%），超过会回滚交易也就是打回原地址，并扣除3%
* 单比手续费为1% （为提高测试持续性提高为5%）
* 交易到账有几个区块延迟，beta测试期间可能会更严重，后期会优化到账时间
* 余额以区块计算，每个区块都会根据交易情况计算事实余额，兑换数量按交易的区块余额计算价格
* 池子会初始化一定比例的余额（测试期间由社区志愿提供，提出时按当前池子余额和投入的比例计算），后期会加上自由加入池子的功能。
* 池子目前只用于beta测试，所以池子余额相对较少

# Swordpool Rule (Beta Version)
## This rule is exclusively for the Swardpool beta testing. Pool transactions are intended solely for technical research and development testing purposes.
## Rule adjustments and maintenance may occur at any time during the testing period, so please pay attention to announcements (please be aware of the risks, as issues may arise during the testing phase).

* Due to development progress issues, front-end operations currently only support the exchange of DOGE for other assets. Other transactions involving the exchange of DRC20 tokens for DOGE must be manually completed by sending to the pool address. Your understanding is appreciated.Transactions sent to the designated pool address will be recognized as transaction activities and can be exchanged for the DRC20 or DOGE defined by the pool.
* Since DRC20 tokens cannot be divided into fractions, a dust transaction type has been set up. Transactions with quantities below the minimum transaction amount, for example, less than 2 DOGE or less than 10 DRC20 tokens, will be considered dust transactions and will be directly included in the pool without being counted as transactions.
Individual transactions cannot exceed 20% of the pool (adjusted to 5% for sustainability), and exceeding this limit will result in a rollback of the transaction to the original address, with a 3% deduction.
* The transaction fee for a single transaction is 1% (increased to 5% for improved testing sustainability).
* There may be a delay in transaction confirmation, especially during the beta testing period, but the confirmation time will be optimized in the later stages.
Balances are calculated based on blocks, with each block calculating the actual balance based on transaction activity. Exchange quantities are calculated based on the block balance of transactions.
* The pool will initialize a certain proportion of balances (provided by community volunteers during the testing period, calculated based on the current pool balance and the contribution ratio). Additional functionality for freely joining the pool will be added in the future.
* The pool is currently only used for beta testing, so the pool balance is relatively low.

