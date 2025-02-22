---
layout:     post
header-img: img/post-bg-extremedax.jpg
catalog: true
tags:
    - Extreme DAX
---

公众号：PowerBI生命管理大师学谦，同步更新，敬请关注



# 第1章  商业智能中的DAX

毫无疑问，**信息**是当今世界上任何一个组织最宝贵的资产之一。作为消费者，我们随时随地都可以感受到各种企业和平台正费尽心机地获取我们的个人数据。不是因为我们每一个人都很有趣（尽管我们确信正在读这本书的您，一定是一个非常有趣的人！），而是一旦将大量消费者的个人数据组合在一起加以分析，组织便可以获得一系列有价值的见解来推动他们的业务向前发展。

这不仅适用于商业公司。公共机构、医院和大学也可以从信息中受益，以更好地运转核心流程。信息是当今世界进步和创新的基础，人们对此有着普遍的共识。

但是要从数据中获取有用信息，再将信息转化为见解和洞察却是一个枯燥乏味且技术性要求较高的过程。整个过程包括：将不同来源的数据进行整合，挖掘隐藏的结构和相关性，与此同时还需要考虑数据产生的实际环境。这就是为什么长期以来商业智能（Business Intelligence，BI）或数据分析领域只有专业IT人员才能胜任的原因。然而，一个需要扎实的业务能力和商业洞察力的过程，却只能由完全不懂业务的IT人员来实现，这显然是不合理的。矛盾就此产生。

本书讨论的核心是：**DAX**（**Data Analysis eXpressions**，数据分析表达式），它是当今数据分析领域最热门的工具之一，也是解决上述矛盾的有力武器。我们假定：作为本书的读者，您对 DAX 有一定的经验，并且希望提高自己的技能。需要特别强调的是，您必须得清楚DAX适合做什么，不适合做什么，这很重要。此外，如果某个过程可以用DAX做得更好，就要尽量避免用其他方式去做。

本章主要阐述一些基本概念，这些内容对您后续的阅读会起到帮助。本章涵盖以下主题。

•   商业智能的五层模型。

•   企业级BI 和最终用户 BI。

•   DAX的优势与使用位置。

•   用于DAX建模的工具。

•   由DAX驱动的可视化与交互式报告。

•   如何开发解决方案。

•   数字化转型循环。

 

## **1.1 商业智能的五层模型**

为了在探讨商业智能数据分析时能够更加系统全面与条理清晰，我们开发了一个简单的框架，用来阐述一套数据分析方案的主要组成部分和的各部分的主要作用，如图1.1所示。我们给它起了一个同样简单的名字：**五层模型**。

![image-20220409174132693](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220409174132693.png)

图1.1 商业智能的五层模型

“五层模型”的第一层也是最低层，**数据连接**层，是数据分析的起点。俗话说，巧妇难为无米之炊，想要对数据进行分析，首先您得先有数据。数据来源有很多：可以是 Excel 工作表、文本文件、大型业务数据库中或网络上的某个位置。

一般来说，这些原始的数据并不能直接进行分析，因为它们的格式往往不符合标准，尤其是当它们来自不同数据源时。因此，您需要先对数据进行一些基本准备工作，也就是第二层：**数据预处理**层。数据预处理有多种形式，像更改数据类型、转换数据、构建数据历史记录或基于“键”值合并查询数据等都是常见的方式。

在连接数据和数据预处理这两个过程中，创建出整齐干净、格式标准的数据集往往需要花费大量时间和精力。有些时候真的让人心力交瘁。在常规的IT领域，打造数据仓库是典型的数据预处理环节，而这，通常会导致开发项目持续多年才能完成。然而让人更加沮丧的是，当数据仓库终于完成时，世界早就不是原来的模样，多年的心血已无法满足当前的实际业务需求。

以上的两步工作结束时，理想的情况是：所有的数据都按照标准的格式存放在模型中，接下来便可以开始对数据进行恰当的分析，也就是第三层：**建模分析**层。这正是数据分析解决方案的核心。通过建模分析，您可以对数据进行切片和筛选，进行各类聚合，并添加各种计算以得到特定的见解。

第四层，**可视化**层，主要是创建报表和仪表板，将建模分析的成果可视化展示。我们将这一层称之为可视化，而不仅仅是“输出”，是因为虽然成果很重要，但是让用户关注到那些重要结论同样重要。可视化真正要实现的是提供见解，或者说“洞察”。由一页又一页的详细信息组成的传统报表并不能让人直观地得出结论，反而会让用户将整个报表导出到 Excel 中，然后自行聚合数据进行分析。真正提供洞察的可视化，往往是一针见血地揭示出核心问题，同时让使用者可以在更低粒度、更详细的指标上进行更深层次的分析，然后找到问题解决方案。

“五层模型”的顶层，**共享**层，由一系列平台与流程组成，旨在为相关人员提供对报表和仪表板的访问权限，同时阻止无关人员的访问。

在构建数据分析解决方案的过程中，无论你是使用 Excel、Power BI、自助开发的企业BI系统，还是根本不使用自动化系统，您都会以某种方式涵盖这五个层面的内容。一个优质的数据分析方案，它的每一层之间界限分明，各司其职。这样做有很多好处，比如可以避免大量的重复性逻辑工作。恰当地实施“五层模型”可以相对容易地应对各方面的变化，比如数据源系统的更改。

DAX 位于“建模分析”这一层，且与“数据预处理”和“可视化”层都有很强的联系，本章将详细展开说明。我们也会在单独的部分专门讨论可视化，但首先，让我们讨论一下这个问题：*谁在**BI**中做什么？*

 

## **1.2 企业级BI和最终用户BI**

企业和组织愈加受到数据的驱动。关键绩效指标（key performance indicators，KPI），几乎每一个组织和每一家企业都在使用，通过一系列仪表板来展现每一个KPI指标的完成情况，相当普遍。这些仪表板通常是高度标准化的：组织往往已经对业务战略、业务流程、如何衡量 KPI 以及如何报告它们非常明确。KPI自动化仪表板通常由IT部门或BI中心构建和维护，它们相对稳定，一般不会发生太大变化，

数据驱动型组织的更高层次是，组织做出的*每一项* 决策都是基于相关数据分析得出的结论。这意味着组织需要一个更加灵活动态的数据分析方法，可以随时随地回答各种临时问题，这种形式的数据分析被称作自助式商业智能（self-service BI，**自助式****BI**）。自助式BI旨在让每个人都能在无需IT中心部门帮助的情况下构建BI解决方案。不过，从五层模型中可以清楚地看出，这并不太现实：想要解决五个层面所有的复杂问题，需要同时具备足够的能力与充足的时间，满足这个条件的最终用户寥寥无几。理想的情况是IT中心部门和最终用户各自发挥自己的特长，彼此合作。

我们使用**企业级****BI**（enterprise BI）和**最终用户****BI**（End-user BI）这两个术语来区分数据分析的这两种形式。**企业级****BI**由IT部门构建和维护，使用大型服务器或云平台，并同时为众多用户提供服务。这通常是一个专业的管理项目，它更侧重于数据质量、平台的可用性和流程的明确定义。最终生成相关的解决方案。

**最终用户****BI**由参与实际业务的用户完成。他们希望在日常工作中可以快速通畅地获取见解，他们对此有强烈的需求。有相当多的人一开始是在Excel中建模分析，但是在复杂的Excel模型中，想要保持数据最新以及维护和扩展解决方案，需要用户投入的时间会越来越多。客观地讲，Excel无法从容应对不断增长的数据量。为了解决这个问题，微软扩展了Excel的功能，引入了Power Query和Power Pivot这两个数据预处理和分析的新工具。这两个强大的工具让Excel成为真正的最终用户BI平台。这些工具经过演变成为了现在的 **Power BI**。

**Power BI**，作为微软的数据分析大杀器，其强大之处在于，将企业 BI 和最终用户 BI这两个矛盾的事物有机地结合在一起。Power BI的底层技术是实现这一目标的驱动力。正如图1.2所展示的那样，借助于Power BI，我们现在可以将企业BI和最终用户BI这两个以前对立的形式统筹到一个体系中，无论用户拥有哪种层次的自助分析能力。

![image-20220409174144030](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220409174144030.png)

图1.2 企业级BI与最终用户BI的结合

“五层模型”是定位不同自助分析能力的有效框架。那些对于自助式BI有需求的用户可以结合该模型的不同层级来认知自己的能力，从而实现他们的目的。他们可以选择在现有的（企业级）分析模型的基础上创建自己的可视化效果；可以使用企业已经预处理完毕的数据集来自助建模分析；或者自行收集数据，将其与企业数据相结合，并自助创建大部分解决方案。他们甚至可以基于其他最终用户创建的模型来进行建模分析。

应该清楚的是，沿着五层模型逐渐向下移动，需要自己承担的比重会越来越大，那么工作的复杂性也就会急剧增加。这样就导致了不仅需要更专业的知识，而且还增加了遵守公司准则和数据标准的责任。此时，就需要企业的IT或BI部门来帮助这些最终用户创建自己的解决方案。如果实施得当，理想的结果是组织中的所有人都能以最佳方式从见解中受益。我们将此愿景称之为**集体分析**。

为了实现集体分析这一美好的愿景，Power BI提供了多项功能，DAX就是其中之一。DAX凭借其强大的实力赋能业务人员，不仅可以使业务人员自助建模分析并找到解决方案，还可以让他们有能力积极参与到企业级解决方案的开发当中。对于后者，我们将在本章的*如何开发解决方案* 这一部分中展开讨论。首先，还是让我们一睹DAX的真容，以及在 BI解决方案中何处可以发现它的踪迹。

## 1.3 DAX的优势与使用位置

在微软的数据分析解决方案中，DAX主要被用于建模分析层面。它在数据分析模型中的作用，是作为公式语言来定义模型中的各种计算和其他逻辑。事实上，模型与DAX实际上是同一枚硬币的两面：模型的设计方式会影响DAX语句的复杂程度，反过来，您的DAX技能也决定着模型设计的难易程度（我们将在*第2章 模型设计*中详细阐述数据模型的核心概念）。

DAX的强大之处在于其高超的数据聚合能力。DAX语言包含众多函数和结构用于定义各种聚合，用户可以从聚合结果中获得所需的见解。长久以来，许多类型的聚合运算必须先通过一系列复杂而又专门的数据预处理来实现，而不能直接进行。比如，想要计算年初至今的销售总额，在 DAX 中仅仅使用一个函数（YTD）就可以实现，而在 Excel或传统报表工具中，需要一系列额外的指标来确定哪些销售交易属于年初至今这个期间，数据预处理环节耗费了大量的时间。后者不仅实现起来更加复杂，而且最终实现的成果还远不如使用DAX那样灵活，DAX不仅可以直接计算年初至今的销售额，还可以同时计算出以往年份的年初至今数据。

这意味着，相比于传统的 BI 解决方案，借助于DAX，我们在数据预处理环节上可以省去大量的时间与精力。由于 DAX 的语法和许多核心概念与Excel很相似，因此对于熟悉Excel的用户来说，DAX 语言学习起来相对比较容易。但是，这并不意味着您可以轻松地*掌握* DAX：在使用DAX的过程中，当您解决了一些稍微简单一些的问题之后，您会逐步将其用于解决更加复杂的问题，但同时您也将为之写出更复杂的 DAX 代码来解决这些问题。本书将为您提供许多 DAX 高级应用的示例，我们希望这些例子能够帮助您去解决遇到的 DAX 难题。

当前，在微软所有的核心数据产品中，我们都可以使用DAX来做建模分析。不过，让人感到疑惑的是，在不同的产品中，模型的命名方式却不太一样。下面，我们将对微软的不同产品中的模型和 DAX做一个基本的概述。

### 1.3.1 Excel中的DAX

Excel 自2010版开始，就以 **Power Pivot** 的形式提供分析数据建模功能。Power Pivot（在 Excel中也称为**Data Model，数据模型**）是基于 DAX 的分析模型。

### 1.3.2 Power BI中的DAX

Power BI是微软数据分析平台上近些年最闪耀的新星。它最初是作为Office 365的一个加载项被引入的，但在2015年升级为一个单独的服务。Power BI 中的分析模型称为 Power BI 数据集（一般简称为数据集），这是 DAX 的栖身之所。

Power BI 数据集和其他的 Power BI 项目是在Power BI 云服务中运行的，用户可通过 Power BI 网站进行访问。同时，其他一些方式也可以使用 Power BI 服务，例如 Power BI 移动应用、Microsoft Teams，甚至如果有能力自助开发，可以通过使用 Power BI Embedded 嵌入自助开发的应用程序来访问。除此之外，如果用户不想使用Power BI的云服务或者企业基于数据安全考虑而不能使用云服务，那么可以选择本地化的Power BI报表服务器。

### 1.3.3 SQL Server Analysis Services中的DAX

SQL Server是微软的数据服务器平台，它包含一个名为Analysis Services（SQL Server分析服务，SSAS）的分析组件。SSAS自2000年左右作为一项OLAP（Online Analytical Processing，联机分析处理）服务开始，多年来一直是一款经典的OLAP服务器，现在被称为**多维模型**（Multidimensional）。随着SQL Server 2012 的发布，SSAS引入了第二个分析功能，称为**表格模型**（Tabular），它是基于DAX的分析模型。

您可能很想知道SSAS中这两种技术之间的差异。本书不准备深入探讨这里所有的细节，但仍然需要指出的是SSAS 多维模型是基于“经典”关系型数据库技术而生。这项技术的设计初衷并非为了对大数据进行聚合与运算，多维模型或数据集只会在建模过程一开始就将所有这些聚合计算执行完毕。相反，在表格模型中，DAX能够即时聚合运算，这意味着用户可以更动态地分析，因为报表设计不会因为模型设计的聚合程度而受到限制。因此，多维模型的灵活多变程度远不如表格模型。

### 1.3.4 Azure Analysis Services中的DAX

Azure Analysis Services （Azure分析服务，AAS） 是一种完全托管的数据分析云服务，与SSAS一样，基于Tabular引擎。显然，与SSAS的不同之处在于，AAS运行在云上，这样您的组织不必担心硬件和数据库的维护。而且它也是一个灵活的解决方案，因为存储和计算资源可以动态扩展以满足当下的需求。

| ![image-20220409174155078](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220409174155078.png) | 综上，在不同的工具里，含DAX的分析模型以诸多不同的名称存在：Power Pivot、Data Model、dataset 或 Tabular Model。  所以当我们在谈论到“分析模型”这一概念时，很容易产生混淆，这对本书来说是一个挑战。由于本书着重于Power BI，因此我们将在本书中使用**Power BI模型**这个术语，或者在不会产生混淆时直接简称为**模型**。并且，本书中的“分析模型”这一术语仅用来表示“五层模型”中的建模分析层。 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

 

## 1.4 用于DAX建模的工具

根据建模平台的不同，您可以使用以下所列不同的工具来进行DAX建模。

•   对于 Power Pivot 模型，可以在Excel中使用Power Pivot加载项。

•   对于 Power BI 数据集，请使用 Power BI Desktop。

| ![](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220409174155078.png) | 有趣的是， Power BI Desktop 实际上有三个版本。一个是从 Power BI 网站下载。另一个是从 Windows 应用商店安装的，并且像应用商店中的任何其他应用一样自动更新。当你意识到 Power BI Desktop 几乎每个月都会发布新版本，那么自动更新肯定要方便一些，尽管有些时候新版本可能会更改一些令你意想不到的地方，确实会很烦人。如果需要，可以在同一台电脑上安装这两个版本。第三个版本的 Power BI Desktop（也可以从 Power BI 网站下载）是与 Power BI 报表服务器一起使用的特殊版本。 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |

 

•    对于 SSAS 或 AAS 中的 Tabular 表格模型，可以使用 Visual Studio，它为专业开发提供了许多功能，例如与版本控制系统的集成、脚本编写和兼容性。

•    对于 Power BI Premium 中的 Power BI 数据集，可以在 Power BI Desktop 和 Visual Studio 之间选择合适的方式。这可以通过 XMLA 终结点技术实现，XMLA 终结点是 Power BI Premium中实现的一种技术，可为 Power BI 数据集提供与 Tabular 表格模型完全相同的可视化效果。

•    此外，还有几种基于社区的工具，如 Tabular Editor和 DAX Studio。这些工具甚至可以集成到 Power BI Desktop 中。

在本书中，我们选择使用"朴实无华"的Power BI Desktop，因为这是一个你应该已经安装了的免费应用。本书的每一位读者都可以轻松下载 Power BI Desktop，并使用异步社区本书页面上存储的示例文件。

## 1.5 由DAX驱动的可视化与交互式报告

在讨论五层模型时，我们已经简要地谈到了可视化报告的重要性。通过以下几个示例您可以发现，想要得到有价值的可视化报告，还得借助于DAX建模来实现。

创建可视化报告的目的是为了得到可靠的分析结论，并提供给使用者直接的见解与解决方案，而不仅仅是大量信息的罗列堆积。我们来看看图1.3展示的这个例子。

![image-20220409174206888](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220409174206888.png)

图1.3 表中的部分销售数据

你能一眼就发现这家公司存在的问题或者机遇吗？如果能，那么您对于数字一定十分敏感！然而，大多数人更习惯于视觉的直观感受。图1.4是同一组数据以柱状图的形式展示。

![image-20220409174214160](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220409174214160.png)

图1.4 更直观地呈现相同的销售数据

从柱状图中可以很明显看出，其中一个SKU的销售表现明显优于其他SKU（Stock Keeping Unit，库存量单位，针对电商而言，指的是识别商品的品项）。这是一个值得注意而且很有价值的见解：如果我们能够使其他SKU达到相同的销售表现，那么公司的整体业绩必将大大改善。这个见解会让人情不自禁地继续往下想：是什么导致了这个SKU卖的这么好呢？是否有某个大客户专门订购了这个SKU？这个SKU是否只在某些特定的地区卖得特别好？它的利润情况怎样呢？它卖得这么好，会不会是因为我们的定价太低了？

以上反映了一个基本的因果关系：每当您通过可视化报告得到一些见解时，这些见解又会让您产生更多新的疑问；解答这些疑问的过程生成新的见解，反过来又产生了其他问题。如此循环。

如何解决这种影响？传统的方法是在一份报告中提供尽可能多的信息。原因很简单，提交一项报告需要花费不少时间。Power BI 却以一种完全不同的方式实现这一点，得益于DAX的强大功能，Power BI在报告报告中添加了交互功能，如图1.5所示。

![image-20220409174222530](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220409174222530.png)

图1.5 可视化-交互周期

交互功能允许报告的使用者深入挖掘初始见解并找到后续问题的答案，从而将一个简单直接的报告转变为有机的交互性报告。而想要实现交互功能，报表需要有能力实时生成新的可视化对象。对于一个Power BI可视化报表来说，它的所有内容全都来自于Power BI模型，这意味着模型在向报表提供结果时也必须同样迅速。而模型的性能是由其本身的结构和您实施的 DAX 代码共同决定。因此，您的 DAX 代码书写好坏会直接影响着报表的用户体验！

## 1.6 如何开发解决方案

在Power BI 模型和 DAX 的帮助下，业务人员可以更加深入地参与开发 BI 解决方案，这与传统BI很大的区别。很显然，这样的解决方案能够提供深入的洞察，从而更好地提升业务价值。

传统的由IT部门来牵头创建的BI解决方案，首先要着手准备连接到数据源并进行数据预处理。如图1.6所示的那样，循序渐进，没有任何问题。毕竟，如果想得到好的并且有价值的见解，高质量的数据是先决条件。

![image-20220409174233662](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220409174233662.png)

图 1.6 传统的 BI 解决方案开发过程

此过程常见于企业数据仓库的开发中。拥有数据仓库背后的思想是将组织的所有数据集中存储在一个固定的位置，以此为基础去开发所有的报告。

应该清楚的是，这将会是一个大工程，因为组织中有许多不同部门，不同的部门有不同的系统，不同的系统又会有各种类型的数据。根据传统，数据仓库是以关系型数据库系统作为基础实现的，这意味着企业所有的数据都必须符合数据仓库的数据库结构或模式。

数据的多样性会导致数据仓库的架构高度复杂。此外，每当数据源系统更改或引入新系统时，新系统中的数据必须与数据仓库的架构相匹配，如果不匹配，那么就必须更改数据仓库以适应新数据。而每一次更改都会消耗大量的时间和金钱，因此，数据仓库项目经常因其持续时间太长和成本高昂而广为诟病。以往的许多职业都是建立在数据仓库之上的，不幸的是，许多职业也因为数据仓库而被打破了。真是成也萧何败也萧何。

传统的方法还存在一个更致命的缺陷。当您从接入数据源系统开始，然后沿着五层模型向上逐步开展工作，等到建模分析结束出报告得出结论的时候，您已经错过了实际业务场景需要这些见解的黄金时间。尽管大多数数据仓库项目都**想**把业务需求和对应的实际业务场景包含在流程中，但是实际上，如果以这种方式来实现，在众多的开发项目（也许是绝大多数项目）中，实际业务需求往往会被束之高阁。我们要知道，在整个数据仓库的开发过程中，技术的复杂性实在是太大了，根本无法让业务深入参与其中。经常出现的情况是，当数据仓库最终完成（或者更确切地说，第一次投入生产）时，它已经落后于当时的实际业务需求。

在焦躁地等待企业报告可用的同时，公司内部一些部门往往已经按捺不住急切的心情，部署了“影子IT”来获取所需的见解。他们利用手头现有的工具（通常是Excel）和可以获取的任何数据，自己动手建模分析并得到解决方案。虽然这能在一定程度上满足部门和员工对于分析见解的急切需要，但这对于企业的长足发展并没有利。一旦数据的质量无法保证，那么由此得出的结论是否可靠就值得商榷了。基于可靠性不足的结论做出决策，我想，没有哪一家企业愿意冒这个风险。

### 1.6.1 使用 Power BI 模型加速开发BI解决方案

在五层模型中，Power BI 不仅支持通过自下而上的方式进行开发，而且还支持通过自上而下的方式，图1.7很好地说明了这一点。

![image-20220409174242037](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220409174242037.png)

图1.7 Power BI支持的解决方案开发方式

通过这种方式，我们不仅可以将 Power BI 用作建模分析得到解决方案的平台，还可以将其作为一个工具来简化项目本身。在这个过程中，您可以充分利用Power BI的这些特定功能：快速创建报表并提供切实的见解，并且无论数据来自于哪里，您都可以从容连接并获取。Power BI模型和DAX发明的初衷就是为了实现上述的功能。

该方式基于两个基本定律如下。

（1）我们并不知道我们到底需要什么。

（2）我们的数据并不规范。

基于这些原则产生的结果是，您不可能在第一次就把它做好。相反，您应该部署一种迭代的工作方式，快速试错并快速改进，然后建立正确的模型。

#### 1.我们并不知道我们到底需要什么

这个定律告诉我们，压根不要指望实际业务人员甚至连你自己都不要指望，能够从一开始就为报告提供标准的规范。如果你曾经接触过并承担了BI项目，那么你会对此深有感触。哪怕是那些拍着胸脯说一切尽在掌握之中的人也会忽略很多细节。

即便他们真的有能力做到面面俱到，不放过任何一个细节，但是只要他们在开发过程中没有完全处于实际业务场景中，那么一定会导致部分解决方案的实施产生偏差。

结果就是，花费大量时间去收集需求或者整理出规范然后再去想尽办法通过审批是徒劳的。你可以确定的是：报告的雏形一定是有问题的。所以更好的方法是尽快将带着问题的报告做出来，然后，马上去改。事实证明，相比于一开始就绞尽脑汁写下所有的细节，指出现有模型中的问题和缺陷然后修修补补要轻松得多。

如图1.8所示，您可以通过多次迭代来将此方法变得正式一些，并在最后使用联合会话来显示原型并收集反馈。（我们喜欢称之为**业务设计会话**来突出它们的本质：它们不是反馈会议或演示，而是共同努力实现正确的结果。）取决于您的Power BI 和 DAX 技能，可能需要两天或更长时间来建立雏形。业务设计会话的结果将作为下一次迭代的输入。

![image-20220409174250032](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220409174250032.png)

图 1.8 迭代需求捕获

这样，我们就得到了一份真正联合开发的且与业务需求完美契合的报告。更重要的是，此报告和模型是充分利用了五层模型当中的较低层提供的数据而得到的标准规范。

#### 2.我们的数据并不规范

第二个定律对你来说一定并不陌生。我们的数据不可能是规范的！原因很简单，实际业务流程往往异常混乱且复杂，再强大的建模能力也无法模拟出完全相同的流程。

而且，当您考虑到IT系统在设计时考虑到了业务流程应该是什么样子的形象时，很明显，自动化业务流程的系统面临着一个根本性的困境。系统实施严格的数据质量策略，即只能输入符合设计流程的数据（因此无法捕获该流程中的每一个案例），或者该系统提供了捕获业务流程所有实例的灵活性，并且必须允许不适合设计的理想流的数据。

后一种选择是大多数时候选择的。这意味着典型的业务系统允许异常、用户用来输入自定义信息的自定义字段以及不同类型的绕过。因此，来自业务系统的数据并不总是符合您的期望。当您的业务数据位于电子表格或其他文件中时，情况会变得更糟！

在传统的BI解决方案中，凌乱的数据很难检测和解决。原因是，通常，BI系统仅包含聚合数据，或者技术不支持业务用户在详细级别上探索数据。这就是Power BI的用武之地：Power BI 模型的技术非常强大，在许多情况下，数据可以加载到模型中而无需聚合。可视化和交互式报表通过复杂的（DAX）聚合提供见解，同时允许你放大到最深层次的细节。

在 BI 解决方案开发的迭代方法中，前几次迭代后的结果通常充满错误。知识渊博的商人通常能够很容易地发现这些错误。首先，以这种方式发现实现的聚合中的缺陷;但在后来的迭代中，数据的质量会显现出来。能够在Power BI报表中查看详细数据对于推动采用和信任新的BI解决方案有很大的帮助。

## 1.7 数字化转型循环

到目前为止，我们重点介绍了从原始数据到见解所需的内容，以及有DAX强大能力加持的Power BI模型在此过程中的作用。正如我们看到的那样，连接到数据源并准备好数据是获取商业价值的基础，但是更多的商业价值来自于可视化与交互式报表提供的直接见解。

然而，没有哪个组织会因为天天盯着漂亮的报表而变得更好。纸上谈兵是万万不能的，实践才是检验真理的唯一标准。换句话说：想要真正知道BI解决方案到底能带来什么好处，您需要结合报表中的分析见解去指导实际的业务。这还不够，您肯定还需要衡量这些操作到底效果如何，要么是以自动的方式，要么是让用户在某个系统里进行输入反馈。这个过程会再次产生数据。

这会产生一个**数字化转型循环**，或者叫数据驱动的业务改进循环，如图1.9所示。

![image-20220409174259416](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220409174259416.png)

图1.9 数字化转型循环

图1.9所展示的这个循环的左侧，由数据产生见解的过程，Power BI的确能够一展风采，但是对于右侧的由行动到评估和反馈，它可能就无能为力了。这个部分需要其他的功能来实现，例如通过某些组件来实现数据的输入或更新，以及通过相关技术来实现人员与系统的连接。

正是出于这个原因，微软将Power BI作为一个更广阔平台的一部分，这个更大的平台叫做**Power Platform**。Power Platform为了覆盖整个数字化转型循环，采用了同样的基本设计原则：业务人员处于核心地位，易于进入，并且完全有能力满足苛刻的业务需求。

如图1.10所示，Power Platform由Power BI和它旁边的三个主要组件构成。

![image-20220409174307421](https://picgo-1301351990.cos.ap-beijing.myqcloud.com/markdown/image-20220409174307421.png)

图1.10 Power Platform组成部分[[1\]](#_ftn1)

•   Power Apps 提供了一个低代码的环境，以便开发一些可以在智能手机或Web浏览器上使用的应用。这些应用可用于编辑或添加数据。

•   Power Automate 允许在各种系统、服务和面向用户的应用程序之间实现各种流程的自动化。举个例子，可以由收到的电子邮件触发流（flow），然后请求业务所有者确认，并自动更新数据，紧接着触发 Power BI 模型和相关报表的刷新。

•   Power Virtual Agents提供了一个平台，可以通过一些AI聊天机器人实现与Power Platform的良好交互。有了这些AI机器人，用户可以通过对话式的交互来输入数据或进行相关操作，而不必去学习特定的应用程序界面。

尽管以上这些都是 Power Platform 这个大平台上的独立应用，但它们是紧密结合在一起的。比如，可以在Power BI报表中嵌入Power Apps 应用，这样用户就可以在获取见解的位置直接对数据进行修改，完美符合商业智能要紧随业务环境的要求。同样地，我们可以将Power Automate流嵌入到 Power BI报表当中，以便根据报表提供的见解来采取相应的措施。

## 总结

在本章中，我们讨论了商业智能领域以及分析模型在现代 BI 解决方案中的核心作用。基于DAX的强大功能，Power BI非常适合用作此类模型。

您已经了解了 DAX 的两项功能，它们对 BI 解决方案的设计和开发方式产生了深远的影响。

•   DAX支持对各种数据直接进行复杂的聚合运算；过去，在进行聚合运算之前需要先对数据进行一系列的预处理使之规范化。因此，DAX让我们免于被数据（涉及所有繁琐的工作）所困扰，可以专注于生成业务见解的逻辑上。

•   DAX作为一门编程语言被创建的初衷，就是让那些熟悉Excel的业务人员能够在不同层次上自行开发BI解决方案。这意味着商业智能可以更好地与业务保持一致，确保业务的优先级。

由于 Power BI 模型和 DAX 是同一枚硬币的两面，因此，如何平衡这两者，很考验建模者的水平。有个简单的秘诀是，让DAX去做那些它擅长的工作，而不是在数据中解决这些问题，反之亦然，也就是说，不要使用DAX来进行数据预处理或生成数据。

接下来的几章将详细阐述这些主题：在第2章 “模型设计”中，我们将讨论设计 Power BI 模型的注意事项。第3章 “使用 DAX”将重点介绍如何使用 DAX 获得最佳结果。第4章 “上下文和筛选”将继续讨论此主题，探讨了编写 DAX 计算时要了解的最重要的概念。本书的第二部分包含许多示例，其中大部分都来自实际客户项目，这些示例将带您领略 DAX 的强大功能以及如何在 DAX 和 Power BI 模型之间找到最佳平衡点。



------

[[1\]](#_ftnref1) 原书无此图，中文版译者添加