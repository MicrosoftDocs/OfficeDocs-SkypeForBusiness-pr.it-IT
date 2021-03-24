---
title: Gestire le applicazioni attendibili
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK considerato attendibile da Skype for Business Server.
ms.openlocfilehash: b99b1c989437e6f474a97463fc53d4179858346e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103162"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="0d7db-103">Gestire le applicazioni attendibili in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0d7db-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="0d7db-104">*Un'applicazione attendibile* è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK considerato attendibile da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d7db-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="0d7db-105">Per informazioni dettagliate sulle applicazioni UCMA, vedere "Unified Communications Managed API 3.0 Core SDK Documentation" all'indirizzo https://go.microsoft.com/fwlink/p/?linkId=210320 .</span><span class="sxs-lookup"><span data-stu-id="0d7db-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at https://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="0d7db-106">Per pubblicare, abilitare o disabilitare correttamente una topologia quando si aggiunge o si rimuove un ruolo del server, è necessario aver eseguito l'accesso come utente membro dei gruppi RTCUniversalServerAdmins e Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="0d7db-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="0d7db-107">Utilizzare questo articolo per informazioni su come configurare un nuovo server applicazioni attendibili, visualizzare un elenco di applicazioni attendibili e visualizzare informazioni sulle applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="0d7db-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="0d7db-108">Configurare un nuovo server applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="0d7db-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="0d7db-109">Accedere al computer in cui è installato Generatore di topologie come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0d7db-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="0d7db-110">Avviare Generatore di topologie: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business Server** e quindi Generatore di topologie di Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="0d7db-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="0d7db-111">Selezionare **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d7db-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="0d7db-112">Nella finestra **di dialogo Salva topologia** con nome fare clic sul file del Generatore di topologie che si desidera utilizzare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0d7db-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="0d7db-113">Nel riquadro sinistro fare clic con il pulsante destro del mouse su **Server applicazioni attendibili** e quindi scegliere Nuovo pool di applicazioni **attendibili.**</span><span class="sxs-lookup"><span data-stu-id="0d7db-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="0d7db-114">Immettere il valore di **FQDN pool** per il pool di applicazioni attendibili, specificare se sarà un pool a server singolo o a più server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0d7db-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="0d7db-115">Nella pagina **Selezionare l'hop successivo,** nell'elenco, selezionare il pool Front End di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d7db-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="0d7db-116">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="0d7db-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="0d7db-117">Selezionare il nodo principale **Skype for Business Server** e quindi scegliere Pubblica topologia dal menu **Azioni.** </span><span class="sxs-lookup"><span data-stu-id="0d7db-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="0d7db-118">Il **pool di** applicazioni attendibili dovrebbe essere stato creato correttamente e associato al pool Front End corretto.</span><span class="sxs-lookup"><span data-stu-id="0d7db-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="0d7db-119">Visualizzare un elenco di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="0d7db-119">View a list of trusted applications</span></span>

<span data-ttu-id="0d7db-120">Puoi usare il Pannello di controllo di Skype for Business Server per visualizzare un elenco delle applicazioni attendibili distribuite nell'ambiente Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d7db-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="0d7db-121">Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK considerato attendibile da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d7db-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="0d7db-122">Questa relazione di trust è riepilogata nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="0d7db-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="0d7db-123">Le applicazioni attendibili non vengono sfidate per l'autenticazione da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d7db-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="0d7db-124">Le applicazioni attendibili non vengono limitate da Skype for Business Server per le transazioni SIP, le connessioni o le chiamate VoIP (Voice over Internet Protocol) in uscita.</span><span class="sxs-lookup"><span data-stu-id="0d7db-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="0d7db-125">Le applicazioni attendibili possono rappresentare qualsiasi utente e possono partecipare a conferenze senza essere inserite negli elenchi dei partecipanti.</span><span class="sxs-lookup"><span data-stu-id="0d7db-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="0d7db-126">Le applicazioni attendibili sono resilienti e a disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="0d7db-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="0d7db-127">Nel Pannello di controllo di Skype for Business Server puoi visualizzare il nome delle applicazioni, il pool in cui vengono eseguite e la porta che usano.</span><span class="sxs-lookup"><span data-stu-id="0d7db-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="0d7db-128">Per visualizzare un elenco di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="0d7db-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="0d7db-129">Da un account utente assegnato al ruolo CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator, accedere a un computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0d7db-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="0d7db-130">Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Skype for Business Server, vedere [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="0d7db-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="0d7db-131">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d7db-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="0d7db-132">Sulla barra di spostamento sinistra fare clic **su Topologia** e quindi su **Applicazione attendibile.**</span><span class="sxs-lookup"><span data-stu-id="0d7db-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="0d7db-133">Nella pagina **Applicazione attendibile** fare clic sull'intestazione di una colonna per ordinare le applicazioni, se necessario.</span><span class="sxs-lookup"><span data-stu-id="0d7db-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="0d7db-134">Visualizzare informazioni sull'applicazione attendibile</span><span class="sxs-lookup"><span data-stu-id="0d7db-134">View trusted application information</span></span>

<span data-ttu-id="0d7db-135">È possibile visualizzare informazioni sulle applicazioni attendibili utilizzando Windows PowerShell e il cmdlet **Get-CsTrustedApplication.**</span><span class="sxs-lookup"><span data-stu-id="0d7db-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="0d7db-136">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d7db-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="0d7db-137">Per visualizzare le applicazioni affidabili</span><span class="sxs-lookup"><span data-stu-id="0d7db-137">To view trusted applications</span></span>

<span data-ttu-id="0d7db-138">Per visualizzare tutte le applicazioni attendibili, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="0d7db-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="0d7db-139">Il comando restituisce informazioni simili a questa, per ciascuna applicazione affidabile:</span><span class="sxs-lookup"><span data-stu-id="0d7db-139">This command returns information similar to the following for each trusted application:</span></span>
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   <span data-ttu-id="0d7db-140">For details, see [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="0d7db-140">For details, see [Get-CsTrustedApplication](/powershell/module/skype/Get-CsTrustedApplication).</span></span>