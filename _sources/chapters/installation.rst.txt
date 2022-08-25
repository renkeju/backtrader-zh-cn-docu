================
安装
================

要求和版本
===============

`backtrader` 是独立的安装包，没有外部依赖项（除非您想绘制视图）。

基本要求是：

* Python 2.7
* Python 3.2/3.3/3.4./3.5
* pypy/pypy3

如果您希望有绘图的附加要求：

* Matplotlib >= 1.4.1

.. note:: 这个版本可能也适用于以前的版本，但这个版本用于最新的开发的版本。

Python 2.x/3.x 兼容性
==============================

开发在 Python 2.7 下进行，有时在 3.4 下进行。两个版本都在本地运行测试。

通过 Travis 下的持续集成检查 3.2/3.3/3.5 和 pypy/pyp3 的兼容性。

从 Pypi 安装
===================

例如使用 pip:

.. code-block:: bash

    pip install backtrader

也可以使用具有相同作用的easy_install语法。

从 Pypi 安装（包括 matplotlib）
=========================================

如果需要绘图功能，请使用此功能：

.. code-block:: bash

    pip install backtrader[plotting]

这会引入 matplotlib，而 matplotlib 又会引入其他依赖项。

同样，您可能更喜欢（或只能通过……）`easy_install`

源代码安装
================

首先从 github 站点下载一个版本或最新的压缩包：

* https://github.com/mementum/backtrader

解压后运行命令：

.. code-block:: bash

    python setup.py install

Github 项目仓库安装
=======================

从 github 站点仓库下载源代码：

.. code-block:: bash

    git clone https://github.com/mementum/backtrader
    cd backtrader
    python setup.py install

请记住，随后需要您手动安装 `matplotlib` 进行绘图。