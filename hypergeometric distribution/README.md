# 超几何分布
* 主要用于富集分析。在总样本中（N），包含某一类型（type1）的样本（K），抽取部分样本（n）中，属于某一类型的样本数目（k）。
* 计算抽取的样本中，包含大于等于k个type1样本的所有情况的概率总和。（相当于小于k个样本的假阳性概率总和）
* R 语言实现

      phyper(k-1,K,(N-K),n)
      N：总体样本数
      K：type1样本数
      n：抽样数目
      k：抽取样品中type1数目
      
      phyper函数是计算小于指定数目的累积抽样概率
      若需计算富集分析错误概率，则需1-phyper
      
      dhyper函数是计算抽取样品中包含指定数目type1的概率
* Python实现

      from scipy import stats
      stats.hypergeom.sf(k-1,N,K,n)
      参数同上
      计算方法同上
      stats.hypergeom.sf等价于phyper，相当于1-cdf
      stats.hypergeom.cdf
      stats.hypergeom.pmf等价于dhyper函数是计算抽取样品中包含指定数目type1的概率
