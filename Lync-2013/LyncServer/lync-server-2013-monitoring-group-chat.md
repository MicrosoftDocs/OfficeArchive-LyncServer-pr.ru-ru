---
title: 'Lync Server 2013: отслеживание группового чата'
description: 'Lync Server 2013: отслеживание группового чата.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625e45f455e8dba50a5fa64240b62cb010623d16
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425425"
---
# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="7065b-103">Мониторинг группового чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7065b-103">Monitoring group chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="7065b-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="7065b-104">

<span> </span></span></span>

<span data-ttu-id="7065b-105">_**Тема последнего изменения:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="7065b-105">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="7065b-106">Мы настоятельно рекомендуем использовать последнюю версию [общего установщика обновлений на сервере](https://support.microsoft.com/kb/968802) , доступную в центре загрузки Майкрософт, для повышения производительности.</span><span class="sxs-lookup"><span data-stu-id="7065b-106">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="7065b-107">Предполагается, что вы используете Последнее накопительное обновление, для метрики, чтобы понять, работают ли серверы группового чата в оптимальной работоспособности, используйте следующую таблицу с нагрузочным тестированием.</span><span class="sxs-lookup"><span data-stu-id="7065b-107">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="7065b-108">Тестовая среда и пользовательская модель</span><span class="sxs-lookup"><span data-stu-id="7065b-108">Test environment and user model</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7065b-109">Три сервера группового чата в пуле группового чата, каждый из которых имеет 8 ГБ памяти и 8 процессоров.</span><span class="sxs-lookup"><span data-stu-id="7065b-109">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7065b-110">Два внешних сервера Lync Server 2013 в выпуске Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="7065b-110">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7065b-111">60 000 одновременные пользователи на трех серверах группового чата.</span><span class="sxs-lookup"><span data-stu-id="7065b-111">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7065b-112">каналы 25 000, размещенные по группе группового чата.</span><span class="sxs-lookup"><span data-stu-id="7065b-112">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7065b-113">Размер канала:</span><span class="sxs-lookup"><span data-stu-id="7065b-113">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="7065b-114">Размер мелкого канала: 30</span><span class="sxs-lookup"><span data-stu-id="7065b-114">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="7065b-115">Средний размер канала: 150</span><span class="sxs-lookup"><span data-stu-id="7065b-115">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="7065b-116">Размер большого канала: 2500</span><span class="sxs-lookup"><span data-stu-id="7065b-116">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7065b-117">Число каналов:</span><span class="sxs-lookup"><span data-stu-id="7065b-117">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="7065b-118">Число малых каналов: 24 000</span><span class="sxs-lookup"><span data-stu-id="7065b-118">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="7065b-119">Число средних каналов 800</span><span class="sxs-lookup"><span data-stu-id="7065b-119">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="7065b-120">Число больших каналов 24</span><span class="sxs-lookup"><span data-stu-id="7065b-120">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="7065b-121">Всего каналов 24 824</span><span class="sxs-lookup"><span data-stu-id="7065b-121">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7065b-122">Пригласите каналы:</span><span class="sxs-lookup"><span data-stu-id="7065b-122">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="7065b-123">Половина каналов согласитесь с каналами</span><span class="sxs-lookup"><span data-stu-id="7065b-123">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7065b-124">Количество каналов, к которым пользователь присоединяется:</span><span class="sxs-lookup"><span data-stu-id="7065b-124">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="7065b-125">Мелкий: 12</span><span class="sxs-lookup"><span data-stu-id="7065b-125">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="7065b-126">Средний: 2</span><span class="sxs-lookup"><span data-stu-id="7065b-126">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="7065b-127">Крупный: 1</span><span class="sxs-lookup"><span data-stu-id="7065b-127">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7065b-128">Скорость соединения:</span><span class="sxs-lookup"><span data-stu-id="7065b-128">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="7065b-129">10 всего за секунду, с 3,33 на сервер</span><span class="sxs-lookup"><span data-stu-id="7065b-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7065b-130">Скорость выхода:</span><span class="sxs-lookup"><span data-stu-id="7065b-130">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="7065b-131">10 всего за секунду, с 3,33 на сервер</span><span class="sxs-lookup"><span data-stu-id="7065b-131">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7065b-132">Ставка чата:</span><span class="sxs-lookup"><span data-stu-id="7065b-132">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="7065b-133">20 всего в секунду, 6.66/сек на сервер</span><span class="sxs-lookup"><span data-stu-id="7065b-133">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="7065b-134">Указанные ниже номера счетчиков производительности, как правило, зависят от конфигурации разных аппаратных спецификаций или профилей пользователей.</span><span class="sxs-lookup"><span data-stu-id="7065b-134">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="7065b-135">Счетчик производительности для наблюдения</span><span class="sxs-lookup"><span data-stu-id="7065b-135">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7065b-136">Счетчик производительности</span><span class="sxs-lookup"><span data-stu-id="7065b-136">Performance Counter</span></span></th>
<th><span data-ttu-id="7065b-137">Пороговые значения</span><span class="sxs-lookup"><span data-stu-id="7065b-137">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7065b-138">Процесс (ChannelService)- &gt; % Processor Time</span><span class="sxs-lookup"><span data-stu-id="7065b-138">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="7065b-139">Минимум: 0</span><span class="sxs-lookup"><span data-stu-id="7065b-139">Min: 0</span></span></p></td>
</tr>
</tbody>
</table><span data-ttu-id="7065b-140">


</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="7065b-140">


</div>

<span> </span>

</div>

</div>

</span></span></div>

