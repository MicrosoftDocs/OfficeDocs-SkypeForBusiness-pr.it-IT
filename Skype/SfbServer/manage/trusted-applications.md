---
title: Gestire le applicazioni attendibili
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK, considerato attendibile da Skype for Business Server.
ms.openlocfilehash: 272785cd1dcfe0bf21f7ac2b5ab64f36646237eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187073"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a><span data-ttu-id="cc5e7-103">Gestire le applicazioni attendibili in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cc5e7-103">Manage trusted applications in Skype for Business Server</span></span>

<span data-ttu-id="cc5e7-104">Un' *applicazione attendibile* è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK, considerato attendibile da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-104">A *trusted application* is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="cc5e7-105">Per informazioni dettagliate sulle applicazioni di UCMA, vedere "documentazione su Unified Communications Managed API 3,0 Core http://go.microsoft.com/fwlink/p/?linkId=210320SDK" at.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at http://go.microsoft.com/fwlink/p/?linkId=210320.</span></span>

<span data-ttu-id="cc5e7-106">Per pubblicare, abilitare o disabilitare correttamente una topologia durante l'aggiunta o la rimozione di un ruolo del server, è necessario essere connessi come utenti membri dei gruppi RTCUniversalServerAdmins e Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> 

<span data-ttu-id="cc5e7-107">Per informazioni su come configurare un nuovo server applicazioni attendibile, vedere un elenco di applicazioni attendibili e visualizzare le informazioni attendibili sull'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-107">Use this article to learn how to configure a new trusted application server, view a list of trusted applications, and view trusted application information.</span></span> 

## <a name="configure-a-new-trusted-application-server"></a><span data-ttu-id="cc5e7-108">Configurare un nuovo server applicazioni attendibile</span><span class="sxs-lookup"><span data-stu-id="cc5e7-108">Configure a new trusted application server</span></span>

1.  <span data-ttu-id="cc5e7-109">Accedere al computer in cui è installato Generatore di topologia come membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-109">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="cc5e7-110">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Skype for Business Server**e quindi fare clic su **Generatore di topologia di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Topology Builder**.</span></span>

3.  <span data-ttu-id="cc5e7-111">Selezionare **Scarica topologia da distribuzione esistente**e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-111">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="cc5e7-112">Nella finestra di dialogo **Salva topologia con nome** fare clic sul file di generatore di topologia che si vuole usare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-112">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="cc5e7-113">Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili**e quindi scegliere **nuovo pool di applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-113">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="cc5e7-114">Immettere il **nome di dominio completo del pool** di applicazioni attendibili, selezionare se si tratta di un server singolo o di più server e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-114">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="cc5e7-115">Nella pagina **selezionare l'hop successivo** , nell'elenco, selezionare il pool Front-End di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-115">On the **Select the next hop** page, from the list, select the Skype for Business Server Front End pool.</span></span>

8.  <span data-ttu-id="cc5e7-116">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-116">Click **Finish**.</span></span>

9.  <span data-ttu-id="cc5e7-117">Selezionare il nodo superiore di **Skype for Business Server**e quindi, nel menu **azioni** , fare clic su **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-117">Select the top node **Skype for Business Server**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="cc5e7-118">Il **pool di applicazioni attendibili** deve essere stato creato correttamente e associato al pool Front-end corretto.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-118">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>


## <a name="view-a-list-of-trusted-applications"></a><span data-ttu-id="cc5e7-119">Visualizzare un elenco di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="cc5e7-119">View a list of trusted applications</span></span>

<span data-ttu-id="cc5e7-120">Puoi usare il pannello di controllo di Skype for Business Server per visualizzare un elenco delle applicazioni attendibili distribuite nell'ambiente di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-120">You can use the Skype for Business Server Control Panel to view a list of the trusted applications that you have deployed in your Skype for Business Server environment.</span></span> <span data-ttu-id="cc5e7-121">Un'applicazione attendibile è un'applicazione basata su Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK, considerato attendibile da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-121">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Skype for Business Server.</span></span> <span data-ttu-id="cc5e7-122">Questa relazione di trust viene riepilogata nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="cc5e7-122">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="cc5e7-123">Le applicazioni attendibili non vengono contestate per l'autenticazione da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-123">Trusted applications are not challenged for authentication by Skype for Business Server.</span></span>

  - <span data-ttu-id="cc5e7-124">Le applicazioni attendibili non vengono strozzate da Skype for Business Server per le transazioni SIP, le connessioni o le chiamate VoIP (Voice over Internet Protocol) in uscita.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-124">Trusted applications are not throttled by Skype for Business Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="cc5e7-125">Le applicazioni attendibili possono rappresentare qualsiasi utente e possono partecipare a conferenze senza comparire in roster.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-125">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="cc5e7-126">Le applicazioni attendibili sono altamente disponibili e resilienti.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-126">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="cc5e7-127">Nel pannello di controllo di Skype for Business Server puoi vedere il nome delle applicazioni, il pool in cui vengono eseguite e la porta che usano.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-127">In the Skype for Business Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>


### <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="cc5e7-128">Per visualizzare un elenco di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="cc5e7-128">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="cc5e7-129">Da un account utente assegnato al ruolo CsServerAdministrator, CsAdministrator, CsHelpDesk o CsViewOnlyAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-129">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="cc5e7-130">Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Skype for Business Server, vedere [controllo di accesso basato sui ruoli (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="cc5e7-130">For details about the predefined administrative roles available in Skype for Business Server, see [Role-based access control (RBAC)](../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>

2.  <span data-ttu-id="cc5e7-131">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-131">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="cc5e7-132">Nella barra di spostamento sinistra fare clic \*\*\*\* su topologia e quindi su **applicazione attendibile**.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-132">In the left navigation bar, click **Topology**, and then click **Trusted Application**.</span></span>

4.  <span data-ttu-id="cc5e7-133">Nella pagina dell' **applicazione attendibile** fare clic su un'intestazione di colonna per ordinare le applicazioni, se necessario.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-133">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>


## <a name="view-trusted-application-information"></a><span data-ttu-id="cc5e7-134">Visualizzare le informazioni sull'applicazione attendibili</span><span class="sxs-lookup"><span data-stu-id="cc5e7-134">View trusted application information</span></span>

<span data-ttu-id="cc5e7-135">Per visualizzare informazioni sulle applicazioni attendibili, è possibile usare Windows PowerShell e il cmdlet **Get-CsTrustedApplication** .</span><span class="sxs-lookup"><span data-stu-id="cc5e7-135">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="cc5e7-136">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc5e7-136">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-trusted-applications"></a><span data-ttu-id="cc5e7-137">Per visualizzare le applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="cc5e7-137">To view trusted applications</span></span>

<span data-ttu-id="cc5e7-138">Per visualizzare tutte le applicazioni attendibili, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="cc5e7-138">To view all of your trusted applications, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
   <span data-ttu-id="cc5e7-139">Questo comando restituisce informazioni simili a quelle seguenti per ogni applicazione attendibile:</span><span class="sxs-lookup"><span data-stu-id="cc5e7-139">This command returns information similar to the following for each trusted application:</span></span>
    
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
    
   <span data-ttu-id="cc5e7-140">Per informazioni dettagliate, vedere [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span><span class="sxs-lookup"><span data-stu-id="cc5e7-140">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>
