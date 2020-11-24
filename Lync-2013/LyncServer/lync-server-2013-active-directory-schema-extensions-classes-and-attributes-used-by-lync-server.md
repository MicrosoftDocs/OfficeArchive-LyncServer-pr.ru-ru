---
title: 'Lync Server 2013: расширения схемы Active Directory, классы и атрибуты, используемые в Lync Server'
description: 'Lync Server 2013: расширения схемы Active Directory, классы и атрибуты, используемые в Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beac778d3315573f4d5cc6cb9c827a3a2fce9d0e
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "49398014"
---
# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="63c8a-103">Расширения схемы Active Directory, классы и атрибуты, используемые в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63c8a-103">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="63c8a-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="63c8a-104">

<span> </span></span></span>

<span data-ttu-id="63c8a-105">_**Тема последнего изменения:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="63c8a-105">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="63c8a-106">Этот справочный раздел содержит указанные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="63c8a-106">This reference section includes the following information:</span></span>

  - <span data-ttu-id="63c8a-107">Новые или измененные расширения схемы Active Directory для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63c8a-107">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="63c8a-108">Схема Active Directory включает в себя формальные определения всех классов объектов, которые можно создать в лесу Active Directory.</span><span class="sxs-lookup"><span data-stu-id="63c8a-108">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="63c8a-109">Схема также содержит формальные определения всех атрибутов, которые могут существовать в объекте Active Directory.</span><span class="sxs-lookup"><span data-stu-id="63c8a-109">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="63c8a-110">Глобальный каталог Active Directory включает в себя реплики всех объектов для леса, а также подмножество атрибутов для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="63c8a-110">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="63c8a-111">В этом разделе описаны классы и атрибуты, новые или измененные в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="63c8a-111">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="63c8a-112">Все классы, используемые в Lync Server, с описанием каждого из них.</span><span class="sxs-lookup"><span data-stu-id="63c8a-112">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="63c8a-113">Все атрибуты, используемые в Lync Server, с описанием каждого из них.</span><span class="sxs-lookup"><span data-stu-id="63c8a-113">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="63c8a-114">Список классов, используемых Lync Server, с атрибутами, которые могут содержать</span><span class="sxs-lookup"><span data-stu-id="63c8a-114">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="63c8a-115">Глобальные параметры и объекты, в дополнение к универсальным службам и группам администрирования, которые создаются во время подготовки леса</span><span class="sxs-lookup"><span data-stu-id="63c8a-115">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="63c8a-116">Элементы управления доступом (ACE), созданные в корне домена и встроенных контейнерах во время подготовки домена</span><span class="sxs-lookup"><span data-stu-id="63c8a-116">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="63c8a-117">Изменения, вносимые в подразделение службы каталогов Active Directory (OU) с помощью \_ командлета Grant CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="63c8a-117">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="63c8a-118">Изменения, вносимые в подразделение Active Directory с помощью \_ командлета Grant CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="63c8a-118">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="63c8a-119">Содержание</span><span class="sxs-lookup"><span data-stu-id="63c8a-119">In This Section</span></span>

  - [<span data-ttu-id="63c8a-120">Изменения схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63c8a-120">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="63c8a-121">Классы схем и описания в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63c8a-121">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="63c8a-122">Атрибуты и описания схемы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63c8a-122">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="63c8a-123">Атрибуты схемы по классу в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63c8a-123">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="63c8a-124">Изменения, внесенные в процессе подготовки леса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63c8a-124">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="63c8a-125">Изменения, внесенные в ходе подготовки домена в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63c8a-125">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="63c8a-126">Изменения, внесенные в Grant-CsSetupPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63c8a-126">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="63c8a-127">Изменения, внесенные в Grant-CsOUPermission в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63c8a-127">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

<span data-ttu-id="63c8a-128"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="63c8a-128"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

