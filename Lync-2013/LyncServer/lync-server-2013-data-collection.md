---
title: 'Lync Server 2013: сбор данных'
description: 'Lync Server 2013: сбор данных.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1808a68081ee453a56eabdaf264eb53ab5a1ef4
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "49431311"
---
# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="4cc60-103">Сбор данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cc60-103">Data collection in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="4cc60-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="4cc60-104">

<span> </span></span></span>

<span data-ttu-id="4cc60-105">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="4cc60-105">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="4cc60-106">В коммуникационном программном обеспечении Microsoft Lync Server 2013 вы можете запустить средство Microsoft Lync Server 2013, планирование, не заполняя существующие и предложенные IP-адреса и полные доменные имена (FQDN), но это значительно сложнее, но это не повлияет на ошибки конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4cc60-106">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="4cc60-107">Например, если сосуществование требуется в течение определенного периода времени, распространенной ошибкой является повторное использование полных доменных имен из существующего развертывания пограничного сервера Lync Server 2013 Edge.</span><span class="sxs-lookup"><span data-stu-id="4cc60-107">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="4cc60-108">После того как существующие и предложенные IP-адреса и полные доменные имена записываются в электронную таблицу, таблицу или другую визуальную форму, вы помогаете предотвратить проблемы во время установки.</span><span class="sxs-lookup"><span data-stu-id="4cc60-108">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="4cc60-109">Если вы использовали предыдущие версии средства планирования, возможно, вы использовали это средство для создания топологии и экспортированный документ топологии для использования в построителе топологии для публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="4cc60-109">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="4cc60-110">Возможность экспорта топологии была удалена из средства планирования.</span><span class="sxs-lookup"><span data-stu-id="4cc60-110">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="4cc60-111">Использование предыдущей версии средства планирования для создания документа топологии для Lync Server 2013 настоятельно не рекомендуется, и это приводит к неожиданным результатам.</span><span class="sxs-lookup"><span data-stu-id="4cc60-111">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="4cc60-112">Поэтому рекомендуемый подход состоит в использовании следующего шаблона сбора данных, соответствующего топологии пограничного сервера, для сбора различных полных доменных имен и IP-адресов, которые нужно будет вводить в инструмент планирования.</span><span class="sxs-lookup"><span data-stu-id="4cc60-112">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="4cc60-113">Задокументируйте текущую и предложенную конфигурацию, вы можете разместить значения в правильном контексте для рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="4cc60-113">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="4cc60-114">Вы вынуждены думать о настройке сосуществования и функциональных возможностях, например простых URL-адресов, общих файловых ресурсов и балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="4cc60-114">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="4cc60-115">Для успешного развертывания Microsoft Lync Server 2013 необходимо понимать взаимодействие и зависимость от отдельных компонентов.</span><span class="sxs-lookup"><span data-stu-id="4cc60-115">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="4cc60-116">Собирая данные из существующей инфраструктуры сети и сервера и применяя руководство по планированию в этих разделах, вы можете интегрировать компоненты сервера Lync Server 2013 Edge Server в инфраструктуру.</span><span class="sxs-lookup"><span data-stu-id="4cc60-116">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="4cc60-117">Введенные в Выбери [топологию в Lync Server 2013](lync-server-2013-choosing-a-topology.md)существуют три основные архитектуры с двумя вариантами, общее количество пяти возможных сценариев развертывания.</span><span class="sxs-lookup"><span data-stu-id="4cc60-117">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="4cc60-118">Один из этих сценариев будет отправной точкой для сбора данных.</span><span class="sxs-lookup"><span data-stu-id="4cc60-118">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="4cc60-119">IP-адреса, имена серверов и доменные имена представляют собой примеры, совпадающие с соответствующими сертификатами, брандмауэрами и DNS-схемами, которые подробно изменяют сведения, необходимые для полного решения для планирования.</span><span class="sxs-lookup"><span data-stu-id="4cc60-119">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="4cc60-120">Эти схемы, а также заполнение необходимых сертификатов, DNS и брандмауэров особенно важны для межгрупповых коммуникаций, в которых Управление центром сертификации, Настройка брандмауэра и DNS управляются группами, отличными от команды, которая планирует развертывание.</span><span class="sxs-lookup"><span data-stu-id="4cc60-120">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="4cc60-121">На схемах представлены сведения о необходимых компонентах, которые можно использовать для обмена данными о требованиях для совместной работы в разных группах.</span><span class="sxs-lookup"><span data-stu-id="4cc60-121">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="4cc60-122">Предоставленные схемы являются преднамеренными, но позволяют получить набор всех нужных данных, которые необходимы для обмена данными о требованиях в рамках межпроектной ситуации, когда сеть, брандмауэр, создание и управление сертификатами, развертывание сервера и управление серверами обрабатываются разными группами.</span><span class="sxs-lookup"><span data-stu-id="4cc60-122">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="4cc60-123">Наличие необходимых сведений о настройке сети, брандмауэрах, портах и протоколах, сертификатах и серверах не является ценным при развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4cc60-123">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="4cc60-124">**Пул пограничного сервера и EDGE**</span><span class="sxs-lookup"><span data-stu-id="4cc60-124">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="4cc60-125">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="4cc60-125">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="4cc60-126">**Обратный прокси-сервер**</span><span class="sxs-lookup"><span data-stu-id="4cc60-126">**Reverse Proxy**</span></span>

<span data-ttu-id="4cc60-127">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="4cc60-127">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="4cc60-128">**Директор или пул директоров**</span><span class="sxs-lookup"><span data-stu-id="4cc60-128">**Director or Director pool**</span></span>

<span data-ttu-id="4cc60-129">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="4cc60-129">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

<span data-ttu-id="4cc60-130"></div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="4cc60-130"></div>

<span> </span>

</div>

</div>

</span></span></div>

