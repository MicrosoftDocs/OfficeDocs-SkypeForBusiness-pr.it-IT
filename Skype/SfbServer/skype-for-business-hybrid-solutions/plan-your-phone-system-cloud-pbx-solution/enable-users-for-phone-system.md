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
description: 'In questo argomento viene descritto come abilitare gli utenti per Sistema telefonico con connettività PSTN locale. Prima di eseguire i passaggi descritti in questo argomento, leggere quanto segue: .'
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359142"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="11618-104">Abilitare gli utenti per Sistema telefonico con connettività PSTN in locale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="11618-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="11618-105">In questo argomento viene descritto come abilitare gli utenti per Sistema telefonico con connettività PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="11618-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="11618-106">Prima di eseguire i passaggi descritti in questo argomento, leggere quanto segue: .</span><span class="sxs-lookup"><span data-stu-id="11618-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="11618-107">Per informazioni su come configurare la connettività ibrida, vedere Pianificare la connettività ibrida tra Skype for Business Server e [Skype for Business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e Distribuire la connettività ibrida tra Skype for Business Server e Skype for Business [online.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="11618-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="11618-108">Per informazioni sulla pianificazione della distribuzione, vedere [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server.](plan-phone-system-with-on-premises-pstn-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="11618-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="11618-109">Per altre informazioni su Sistema telefonico, incluse licenze e piani, vedi Piani per chiamate [PSTN per Skype for Business.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)</span><span class="sxs-lookup"><span data-stu-id="11618-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
> [!Important]
> <span data-ttu-id="11618-110">Skype for Business online verrà ritirato il 31 luglio 2021 dopo il quale il servizio non sarà più accessibile.</span><span class="sxs-lookup"><span data-stu-id="11618-110">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="11618-111">Inoltre, la connettività PSTN tra l'ambiente locale tramite Skype for Business Server o Cloud Connector Edition e Skype for Business online non sarà più supportata.</span><span class="sxs-lookup"><span data-stu-id="11618-111">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="11618-112">Informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="11618-112">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="11618-113">Spostamento degli utenti in Sistema telefonico con connettività PSTN locale</span><span class="sxs-lookup"><span data-stu-id="11618-113">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="11618-114">Prima di spostare gli utenti in Skype for Business online, è consigliabile abilitare gli utenti in locale in Skype for Business Server o Lync Server 2013 e quindi spostarli online.</span><span class="sxs-lookup"><span data-stu-id="11618-114">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="11618-115">Per ulteriori informazioni, vedere Pianificare la connettività ibrida tra Skype for Business Server e [Skype for Business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e la sezione considerazioni speciali di Abilitare gli utenti per VoIP aziendale [in](enable-the-users-for-enterprise-voice-on-premises.md) locale (eseguito mentre gli utenti sono ospitati in locale).</span><span class="sxs-lookup"><span data-stu-id="11618-115">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="11618-116">Tutti gli utenti devono essere creati in Active Directory in locale e sincronizzati con Microsoft 365 o Office 365 utilizzando la versione supportata di Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="11618-116">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="11618-117">Non è possibile abilitare gli utenti per Sistema telefonico in Office 365 creati direttamente in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="11618-117">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="11618-118">Se si desidera abilitare Sistema telefonico con connettività PSTN locale per un utente creato in Azure AD, è necessario creare un nuovo account per tale utente in Active Directory locale, configurare l'account locale e quindi sincronizzare l'account con una versione supportata dello strumento Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="11618-118">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="11618-119">Per abilitare un utente per Sistema telefonico con connettività PSTN locale e quindi spostarlo in Skype for Business online, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="11618-119">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="11618-120">[Abilitare gli utenti per VoIP aziendale locale](enable-the-users-for-enterprise-voice-on-premises.md) (eseguito mentre gli utenti sono ospitati in locale).</span><span class="sxs-lookup"><span data-stu-id="11618-120">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="11618-121">[Assegnare un criterio di routing vocale](assign-a-voice-routing-policy.md) (eseguito mentre gli utenti sono ospitati in locale).</span><span class="sxs-lookup"><span data-stu-id="11618-121">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="11618-122">[Sincronizzare gli utenti nel cloud e assegnare le licenze](synchronize-users-to-the-cloud-and-assign-licenses.md) (eseguite con Office 365).</span><span class="sxs-lookup"><span data-stu-id="11618-122">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="11618-123">[Spostare gli utenti](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) locali in Skype for Business online (eseguito usando Windows PowerShell locale, ma usando le credenziali di amministratore di Office 365).</span><span class="sxs-lookup"><span data-stu-id="11618-123">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="11618-124">[Abilitare gli utenti per VoIP aziendale segreteria telefonica del sistema telefonico](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) e online (eseguita tramite Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11618-124">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

