---
title: 'Lync Server 2013: настройка директора'
description: 'Lync Server 2013: Настройка режиссера.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b917000dec6d30fdec2963ff1e464fbb9a70805
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "49423906"
---
# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="b01e9-103">Настройка директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b01e9-103">Setting up the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="b01e9-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="b01e9-104">

<span> </span></span></span>

<span data-ttu-id="b01e9-105">_**Тема последнего изменения:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="b01e9-105">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="b01e9-106">Если вы разрабатываете доступ для внешних пользователей, развертывая пограничные серверы, один из вариантов — развернуть директорию.</span><span class="sxs-lookup"><span data-stu-id="b01e9-106">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="b01e9-107">Режиссер — это сервер, на котором работает Microsoft Lync Server 2013, который проверяет подлинность запросов пользователей, но не имеет домашних учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="b01e9-107">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="b01e9-108">Теперь это не является требованием, но очень полезно, если вы беспокоитесь о производительности и хотите упростить запросы на проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="b01e9-108">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="b01e9-109">Если вы решите, что это хорошая идея для вашей организации, действия, которые необходимо выполнить для настройки режиссера или режиссера, похожи на настройку пула переднего плана Enterprise Edition или стандартного сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b01e9-109">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="b01e9-110">После определения режиссеров в построителе топологии вам потребуется выполнить действия, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b01e9-110">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b01e9-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="b01e9-111">In This Section</span></span>

  - [<span data-ttu-id="b01e9-112">Установка локального хранилища конфигурации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b01e9-112">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="b01e9-113">Установка Lync Server 2013 на директоре</span><span class="sxs-lookup"><span data-stu-id="b01e9-113">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="b01e9-114">Настройка сертификатов для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b01e9-114">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="b01e9-115">Запуск служб в директоре в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b01e9-115">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="b01e9-116">Проверка директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b01e9-116">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="b01e9-117">Настройка автоматического входа клиента для использования директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b01e9-117">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

<span data-ttu-id="b01e9-118"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="b01e9-118"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

