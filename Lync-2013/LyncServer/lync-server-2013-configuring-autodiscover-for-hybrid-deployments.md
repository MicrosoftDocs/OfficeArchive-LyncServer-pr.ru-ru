---
title: 'Lync Server 2013: Настройка автообнаружения для гибридных развертываний'
description: 'Lync Server 2013: Настройка автообнаружения для гибридных развертываний.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6797e3f6b77e3016f6cef87f2a930f5a7c1fce6
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "49433306"
---
# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a><span data-ttu-id="44b51-103">Настройка автообнаружения в Lync Server 2013 для гибридных развертываний</span><span class="sxs-lookup"><span data-stu-id="44b51-103">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="44b51-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="44b51-104">

<span> </span></span></span>

<span data-ttu-id="44b51-105">_**Тема последнего изменения:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="44b51-105">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="44b51-106">Гибридное развертывание — это конфигурация, использующая как облачную службу Microsoft Lync Online, так и локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="44b51-106">Hybrid Deployments are configurations that use both the Microsoft Lync Online cloud service and the on premises deployment.</span></span> <span data-ttu-id="44b51-107">В этом типе конфигурации Служба автообнаружения должна находить место, где пользователь фактически находится.</span><span class="sxs-lookup"><span data-stu-id="44b51-107">In this type of configuration, the Autodiscover service must be able to locate where the user is actually located.</span></span> <span data-ttu-id="44b51-108">Это означает, что средства автообнаружения помогают найти учетную запись пользователя и сервер, на котором размещена учетная запись пользователя, независимо от того, есть ли в локальном развертывании или в развертывании Lync Online.</span><span class="sxs-lookup"><span data-stu-id="44b51-108">That is to say, Autodiscover aids in finding the user account and where the server that hosts the user’s account is, regardless if it is in the on premises deployment or in the Lync Online deployment.</span></span>

<span data-ttu-id="44b51-109">Например, если учетная запись пользователя размещена на сервере в Lync Online, попытка найти пользователя будет выполняться следующим образом в процессе, известном как *обнаруживаемость*.</span><span class="sxs-lookup"><span data-stu-id="44b51-109">For example, if a user’s account is hosted on a server in Lync Online, the attempt to locate the user will happen as follows, in a process known as *discoverability*:</span></span>

  - <span data-ttu-id="44b51-110">Пользователь инициирует попытку подключения к локальному развертыванию **contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="44b51-110">User initiates a connection attempt to the on premises deployment, **contoso.com**.</span></span>

  - <span data-ttu-id="44b51-111">Предпринята попытка отправки в lyncdiscover.contoso.com, DNS-имя, связанное со службой автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="44b51-111">The attempt is sent to lyncdiscover.contoso.com, the DNS name associated with the Autodiscover service.</span></span>

  - <span data-ttu-id="44b51-112">Автообнаружения — это предполагаемый пул регистраторов в локальной среде развертывания contoso.com и получает сведения на основном сервере, размещенном на Lync Online.</span><span class="sxs-lookup"><span data-stu-id="44b51-112">Autodiscover refers to the assumed registrar pool at the contoso.com on premises deployment and is given information on the user’s actual home server hosted in Lync Online.</span></span> <span data-ttu-id="44b51-113">Затем служба автообнаружения отправляет пользователю ссылку на службу автообнаружения **Lync.com** Online.</span><span class="sxs-lookup"><span data-stu-id="44b51-113">Autodiscover then sends the user a referral to the **lync.com** online Autodiscover service.</span></span>

  - <span data-ttu-id="44b51-114">Пользователь инициирует попытку подключения к службе автообнаружения lync.com Online и может найти учетную запись пользователя и домашний сервер пользователя.</span><span class="sxs-lookup"><span data-stu-id="44b51-114">The user initiates a connection attempt to the lync.com online Autodiscover service and is able to locate the user’s account and the user’s home server.</span></span>

<span data-ttu-id="44b51-115">Чтобы разрешить клиентам определять развертывание, в котором находится домашний сервер пользователей, необходимо настроить службу автообнаружения с помощью нового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="44b51-115">To enable clients to discover the deployment where the user home server is located, you must configure the Autodiscover service with a new uniform resource locator (URL).</span></span> <span data-ttu-id="44b51-116">Чтобы настроить службу автообнаружения, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="44b51-116">Do the following to configure the Autodiscover service.</span></span>

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a><span data-ttu-id="44b51-117">Настройка автообнаружения для гибридных развертываний</span><span class="sxs-lookup"><span data-stu-id="44b51-117">Configuring Autodiscover for Hybrid Deployments</span></span>

1.  <span data-ttu-id="44b51-118">В теме, [требования к службе автообнаружения для Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), вы используете Get-CsHostingProvider для получения значения атрибута ProxyFQDN.</span><span class="sxs-lookup"><span data-stu-id="44b51-118">In the topic, [Autodiscover service requirements for Lync Server 2013](lync-server-2013-autodiscover-service-requirements.md), you use Get-CsHostingProvider to retrieve the value of the attribute ProxyFQDN.</span></span>

2.  <span data-ttu-id="44b51-119">В командной консоли Lync Server введите</span><span class="sxs-lookup"><span data-stu-id="44b51-119">From the Lync Server Management Shell, type</span></span>
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    <span data-ttu-id="44b51-120">Где \[ идентификатор \] заменяется доменным именем общего адресного пространства SIP.</span><span class="sxs-lookup"><span data-stu-id="44b51-120">Where \[identity\] is replaced with the domain name of the shared SIP address space.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="44b51-121">См. также</span><span class="sxs-lookup"><span data-stu-id="44b51-121">See Also</span></span>


[<span data-ttu-id="44b51-122">Get-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="44b51-122">Get-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[<span data-ttu-id="44b51-123">Set-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="44b51-123">Set-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

<span data-ttu-id="44b51-124"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="44b51-124"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

