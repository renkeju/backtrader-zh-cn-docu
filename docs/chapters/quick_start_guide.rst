=============
快速开始
=============

.. note:: 

    快速入门指南中使用的数据文件会不时更新，这意味着调整后的收盘会发生变化，收盘也会随之变化（以及其他组件）。 这也意味着实际输出可能与撰写本文时文档中的内容不同。

使用平台
==============

让我们通过一系列示例（从几乎空白的示例到完全成熟的策略），但在粗略解释使用 backtrader 之前，有2个基本概念需要提前了解。

1. 线

    数据流、指标和策略都有线。

    一条线是一连串点，当它们连接在一起形成这条线时。在谈论市场时，数据流通常每天具有以下一组点：

       * 开盘价、最高价、最低价、收盘价、成交量、未平仓。

    一连串的“开盘价”是一条线。因此，数据流通常有6行。如果我们还考虑“DateTime”（这是单个点的实际参考），我们可以数7行。

2. 索引0的方法

    访问一行中的值时，使用索引访问当前值：0

    “最后一个”输出值使用-1访问。这符合可迭代对象的Python约定（并且一行可以被迭代，因此是一个可迭代对象），其中索引-1用于访问可迭代对象/数组的“最后一个”项。

    在我们的例子中是被访问的最后一个输出值。

    因此，在索引-1之后即为索引0，它用于访问当前的时刻。

考虑到这一点，如果我们想象一个具有在初始化期间创建的简单移动平均线的策略：

.. code-block:: python3

    self.sma = SimpleMovingAverage(.....)

访问此移动平均线当前值的最简单和最简单的方法：

.. code-block:: python3

    av = self.sma[0]

因此无需知道已处理了多少k线/分钟/天/月，因为“0”唯一标识是当前时刻。

按照 pythonic 传统，使用 -1 访问“最后一个”输出值：

.. code-block:: python3

    previous_value = self.sma[-1]

当然更早的输出值可以用-2,-3,…依此类推。

从0到1，一个示例
========================

基本设置
--------------

让我们开始吧。

.. code-block:: python3

    from __future__ import (absolute_import, division, print_function,
                            unicode_literals)

    import backtrader as bt

    if __name__ == '__main__':
        cerebro = bt.Cerebro()

        print('Starting Portfolio Value: %.2f' % cerebro.broker.getvalue())

        cerebro.run()

        print('Final Portfolio Value: %.2f' % cerebro.broker.getvalue())