---
title: 'Lync Server 2013: новые возможности высокой доступности и аварийного восстановления'
description: 'Lync Server 2013: новые возможности аварийного восстановления и обеспечения высокой доступности.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New disaster recovery and high availability features
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48184130
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92816f61b66d9eed76c16286aaa6c7392dca7708
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "49425116"
---
# <a name="new-disaster-recovery-and-high-availability-features-in-lync-server-2013"></a><span data-ttu-id="3cbf4-103">Новые возможности высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cbf4-103">New disaster recovery and high availability features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="3cbf4-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="3cbf4-104">

<span> </span></span></span>

<span data-ttu-id="3cbf4-105">_**Тема последнего изменения:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="3cbf4-105">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="3cbf4-106">Как и в Lync Server 2010, основная схема высокой доступности для Lync Server 2013 основывается на избыточности сервера посредством группировки.</span><span class="sxs-lookup"><span data-stu-id="3cbf4-106">As in Lync Server 2010, the main high availability (HA) scheme for Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="3cbf4-107">При сбое сервера с определенными ролями остальные серверы в пуле с такими же ролями берут на себя нагрузку этого сервера.</span><span class="sxs-lookup"><span data-stu-id="3cbf4-107">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="3cbf4-108">Это касается серверов переднего плана, пограничных серверов, серверов-посредников и Директоров.</span><span class="sxs-lookup"><span data-stu-id="3cbf4-108">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="3cbf4-109">Lync Server 2013 добавляет новые показатели аварийного восстановления, позволяя связывать пулы интерфейсов, расположенные в двух центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="3cbf4-109">Lync Server 2013 adds new disaster recovery measures by enabling you to pair Front End pools located in two datacenters.</span></span> <span data-ttu-id="3cbf4-110">Если один из сопоставленных пулов выходит из строя, администратор может перенести пользователей из этого пула в другой пул в паре для предоставления возможности продолжения обслуживания.</span><span class="sxs-lookup"><span data-stu-id="3cbf4-110">If one of the paired pools goes down, an administrator can fail over the users from that pool to the other pool in the pair, to provide continuation of service.</span></span> <span data-ttu-id="3cbf4-111">Эта функция не требует дорогостоящих сетевых и аппаратных решений, таких как сети хранения данных или общие диски.</span><span class="sxs-lookup"><span data-stu-id="3cbf4-111">This functionality does not require expensive network or hardware solutions such as storage networks or shared disks.</span></span>

<span data-ttu-id="3cbf4-112">Lync Server 2013 также добавляет полную доступность сервера для серверной части.</span><span class="sxs-lookup"><span data-stu-id="3cbf4-112">Lync Server 2013 also adds Back End Server high availability.</span></span> <span data-ttu-id="3cbf4-113">Это необязательная топология, в которой развертывается два серверных сервера для пула переднего плана, а также синхронное зеркальное отображение SQL для всех баз данных Lync, запущенных на серверном сервере.</span><span class="sxs-lookup"><span data-stu-id="3cbf4-113">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL mirroring for all the Lync databases running on the Back End Servers.</span></span> <span data-ttu-id="3cbf4-114">Вы можете выбрать, нужно ли развертывать следящий сервер для зеркала.</span><span class="sxs-lookup"><span data-stu-id="3cbf4-114">You may choose whether to deploy a witness for the mirror.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="3cbf4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3cbf4-115">See Also</span></span>


[<span data-ttu-id="3cbf4-116">Планирование высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cbf4-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

<span data-ttu-id="3cbf4-117"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="3cbf4-117"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

