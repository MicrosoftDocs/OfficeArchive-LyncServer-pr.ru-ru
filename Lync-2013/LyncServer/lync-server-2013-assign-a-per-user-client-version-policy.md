---
title: 'Lync Server 2013: назначение политики клиентской версии для пользователя'
description: 'Lync Server 2013: назначение политики клиентской версии для пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ec2fcbf9c005806a97dfbdceb22095fe0ff8f33
ms.sourcegitcommit: 36fee89bb887bea4f18b19f17a8c69daf5bc423d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "49443190"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="dc9d1-103">Назначение политики клиентской версии для пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc9d1-103">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="dc9d1-104">Политика Client Version — это один из параметров учетной записи пользователя, которую можно настроить на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-104">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="dc9d1-105">Развертывание одной или нескольких политик клиентской версии для каждого пользователя является необязательным.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-105">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="dc9d1-106">Вы также можете развернуть только политику глобального уровня клиента или политики версии на уровне сайта или в пуле для клиента.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-106">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="dc9d1-107">Если выполняется развертывание политик на пользователя, необходимо явно назначить их пользователям, группам или контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-107">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="dc9d1-108">Если вы не назначили определенную политику на уровне сайта, в пуле или на уровне пользователя, в Lync Server 2013 используются клиенты по умолчанию, которые могут регистрироваться в соответствии с политикой версии глобального уровня в клиенте.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-108">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="dc9d1-109">После создания хотя бы одной политики клиентской версии для пользователей используйте процедуры из этого раздела, чтобы назначить политику, указывающую версии клиентов, которые нужно разрешить для регистрации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-109">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="dc9d1-110">Дополнительные сведения о создании политик клиентской версии для каждого пользователя можно найти в разделе [Определение клиентских приложений, которые могут использоваться для входа в Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="dc9d1-110">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="dc9d1-111">Назначение политики клиентской версии для пользователя</span><span class="sxs-lookup"><span data-stu-id="dc9d1-111">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="dc9d1-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc9d1-113">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dc9d1-114">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dc9d1-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dc9d1-115">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="dc9d1-116">Используйте один из следующих методов для обнаружения пользователя:</span><span class="sxs-lookup"><span data-stu-id="dc9d1-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="dc9d1-117">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, а затем щелкните **Найти**.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="dc9d1-118">Если у вас есть сохраненный запрос, щелкните значок **Открыть запрос**. С помощью диалогового окна **Открыть** загрузите запрос (файл .usf), а затем щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="dc9d1-119">(Необязательно) Задайте дополнительные критерии поиска, чтобы сократить количество результатов:</span><span class="sxs-lookup"><span data-stu-id="dc9d1-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="dc9d1-120">Щелкните **Добавить фильтр**.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="dc9d1-121">Введите свойства пользователя; для это введите его или щелкните стрелку в раскрывающемся списке, чтобы выбрать свойство.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="dc9d1-122">В раскрывающемся списке **Равно** щелкните оператор (например, **Равно** или **Не равно**).</span><span class="sxs-lookup"><span data-stu-id="dc9d1-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="dc9d1-123">В зависимости от выбранного свойства пользователя введите критерии, которые необходимо использовать для фильтрации результатов поиска; для это введите его или щелкните стрелку в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="dc9d1-124">Чтобы добавить в запрос дополнительные условия поиска, щелкните <STRONG>Добавить фильтр</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="dc9d1-125">Щелкните **Поиск**.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-125">Click **Find**.</span></span>

6.  <span data-ttu-id="dc9d1-126">Выберите пользователя в списке результатов поиска, щелкните **Действие**, а затем **Назначить политики**.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="dc9d1-127">Если вы хотите применить одну и ту же политику пользовательской версии для нескольких пользователей, выберите в результатах поиска нескольких пользователей, а затем нажмите кнопку <STRONG>действия</STRONG>и выберите команду <STRONG>назначить политики</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-127">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="dc9d1-128">В группе **назначение политик** в разделе **Политика версии клиента** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-128">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="dc9d1-129">Из <STRONG> &lt; - &gt; </STRONG> за нескольких политик, которые можно настроить с помощью диалогового окна <STRONG>назначение политик</STRONG> , по умолчанию для каждой политики в диалоговом окне выбрать пункт Сохранить как.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="dc9d1-130">Чтобы продолжить использование политики, назначенной пользователю ранее, не вносите никаких изменений в эти настройки.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="dc9d1-131">Разрешить Lync Server автоматический выбор политики глобального уровня или, если она определена, политики уровня сайта или политики уровня пула.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-131">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="dc9d1-132">Щелкните имя политики клиентской версии, которая ранее была определена на странице **политики Client Version** .</span><span class="sxs-lookup"><span data-stu-id="dc9d1-132">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="dc9d1-133">Чтобы с легкостью определить политику, которую необходимо назначить, после выбора названия политики щелкните <STRONG>Просмотр</STRONG> для просмотра прав и разрешений пользователя, заданных в политике.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="dc9d1-134">По завершении щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dc9d1-135">Назначение политики версии клиента Per-User с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc9d1-135">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dc9d1-136">Вы можете назначить политики клиентской версии для пользователей с помощью командлета Grant-CsClientVersionPolicy.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-136">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="dc9d1-137">Этот командлет можно выполнить из управляющей оболочки Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-137">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dc9d1-138">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на веб-сервере Lync Server Windows PowerShell [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="dc9d1-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="dc9d1-139">Назначение индивидуальной политики клиентской версии для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="dc9d1-139">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="dc9d1-140">Следующая команда назначает пользователю политику пользовательской версии для пользователя RedmondClientVersionPolicy, которая Кен Myer.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-140">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="dc9d1-141">Назначение политики клиентской версии для каждого пользователя нескольким пользователям</span><span class="sxs-lookup"><span data-stu-id="dc9d1-141">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="dc9d1-142">Эта команда назначает политику клиентской версии для пользователя RedmondClientVersionPolicy всем пользователям, которым в данный момент назначена политика голосовой связи RedmondVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-142">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="dc9d1-143">Дополнительные сведения о параметре фильтрации, используемом в этой команде, можно найти в документации по командлету [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="dc9d1-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="dc9d1-144">Отмена политики клиентской версии для пользователя</span><span class="sxs-lookup"><span data-stu-id="dc9d1-144">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="dc9d1-145">Следующая команда отменяет назначение любой политики клиентской версии для каждого пользователя, ранее назначенной для Кен Myer.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-145">The following command unassigns any per-user client version policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="dc9d1-146">После того как политика для пользователя не будет назначена, Кен Myer будет автоматически управляться с помощью глобальной политики, политики локального сайта (если она существует) или политики области действия, назначенной своему регистратору.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-146">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar.</span></span> <span data-ttu-id="dc9d1-147">Политика области обслуживания имеет приоритет над любой политикой сайта, а политика сайта имеет приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="dc9d1-147">A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="dc9d1-148">Дополнительные сведения можно найти в разделе справки о командлете [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="dc9d1-148">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc9d1-149">См. также</span><span class="sxs-lookup"><span data-stu-id="dc9d1-149">See Also</span></span>


[<span data-ttu-id="dc9d1-150">Назначение политик для пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc9d1-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="dc9d1-151">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc9d1-151">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

