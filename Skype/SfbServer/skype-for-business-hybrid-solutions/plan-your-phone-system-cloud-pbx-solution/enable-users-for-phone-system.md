---
title: Abilitare gli utenti per Sistema telefonico con connettività PSTN in locale in Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 'In questo argomento viene descritto come abilitare gli utenti per Sistema telefonico con connettività PSTN locale. Prima di eseguire la procedura descritta in questo argomento, leggere quanto segue: .'
ms.openlocfilehash: 0a843b49546bfc5451197a3ef8ca48799c194731
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120868"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="9af98-104">Abilitare gli utenti per Sistema telefonico con connettività PSTN in locale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9af98-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="9af98-105">In questo argomento viene descritto come abilitare gli utenti per Sistema telefonico con connettività PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="9af98-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="9af98-106">Prima di eseguire la procedura descritta in questo argomento, leggere quanto segue: .</span><span class="sxs-lookup"><span data-stu-id="9af98-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="9af98-107">Per informazioni su come configurare la connettività ibrida, vedere Pianificare la connettività ibrida tra Skype for Business Server e [Skype for Business online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e Distribuire la connettività ibrida tra Skype for Business Server e Skype for Business [online.](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="9af98-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>
    
- <span data-ttu-id="9af98-108">Per informazioni sulla pianificazione della distribuzione, vedere [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server.](plan-phone-system-with-on-premises-pstn-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="9af98-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="9af98-109">Per altre informazioni su Sistema telefonico, incluse le licenze e i piani, vedi Piani per chiamate [PSTN per Skype for Business.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)</span><span class="sxs-lookup"><span data-stu-id="9af98-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
> [!Important]
> <span data-ttu-id="9af98-110">Skype for Business Online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.</span><span class="sxs-lookup"><span data-stu-id="9af98-110">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="9af98-111">Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business online non sarà più supportata.</span><span class="sxs-lookup"><span data-stu-id="9af98-111">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="9af98-112">Informazioni su come connettere la rete di telefonia locale a Teams tramite [routing diretto.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="9af98-112">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="9af98-113">Spostamento degli utenti nel sistema telefonico con connettività PSTN locale</span><span class="sxs-lookup"><span data-stu-id="9af98-113">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="9af98-114">Prima di spostare gli utenti in Skype for Business online, è consigliabile abilitare gli utenti in locale in Skype for Business Server o Lync Server 2013 e quindi spostarli online.</span><span class="sxs-lookup"><span data-stu-id="9af98-114">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="9af98-115">Per ulteriori informazioni, vedere Plan [hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e la sezione considerazioni speciali di Enable the users for VoIP aziendale on [premises](enable-the-users-for-enterprise-voice-on-premises.md) (eseguita mentre gli utenti sono ospitati in locale).</span><span class="sxs-lookup"><span data-stu-id="9af98-115">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="9af98-116">Tutti gli utenti devono essere creati in Active Directory locale e sincronizzati con Microsoft 365 o Office 365 utilizzando la versione supportata di Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="9af98-116">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="9af98-117">Non è possibile abilitare gli utenti per Sistema telefonico in Office 365 creati direttamente in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9af98-117">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="9af98-118">Se si desidera abilitare Sistema telefonico con connettività PSTN locale per un utente creato in Azure AD, è necessario creare un nuovo account per tale utente nell'AD locale, configurare l'account locale e quindi sincronizzare l'account con una versione supportata dello strumento Connettore Di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9af98-118">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="9af98-119">Per abilitare un utente per Sistema telefonico con connettività PSTN locale e quindi spostarli in Skype for Business Online, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="9af98-119">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="9af98-120">[Abilitare gli utenti per VoIP aziendale locale](enable-the-users-for-enterprise-voice-on-premises.md) (eseguito mentre gli utenti sono ospitati in locale).</span><span class="sxs-lookup"><span data-stu-id="9af98-120">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="9af98-121">[Assegnare un criterio di routing vocale](assign-a-voice-routing-policy.md) (eseguito mentre gli utenti sono ospitati in locale).</span><span class="sxs-lookup"><span data-stu-id="9af98-121">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="9af98-122">[Sincronizzare gli utenti nel cloud e assegnare licenze](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (eseguite con Office 365).</span><span class="sxs-lookup"><span data-stu-id="9af98-122">[Synchronize users to the cloud and assign licenses](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (performed using Office 365).</span></span>
    
- <span data-ttu-id="9af98-123">[Spostare gli utenti locali in Skype for Business online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (eseguito Windows PowerShell locale, ma usando le credenziali di amministratore di Office 365).</span><span class="sxs-lookup"><span data-stu-id="9af98-123">[Move on-premises users to Skype for Business Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="9af98-124">[Abilitare gli utenti per VoIP aziendale segreteria telefonica online e](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) del sistema telefonico (eseguita tramite Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9af98-124">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
