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
description: In questo argomento viene descritto come abilitare gli utenti per il sistema telefonico con connettività PSTN locale. Prima di eseguire la procedura descritta in questo argomento, è consigliabile leggere quanto segue:.
ms.openlocfilehash: 9cd5fe66b6092b0ac21af4c425f662d18d96ab49
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221096"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="39f6d-104">Abilitare gli utenti per Sistema telefonico con connettività PSTN in locale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="39f6d-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="39f6d-105">In questo argomento viene descritto come abilitare gli utenti per il sistema telefonico con connettività PSTN locale.</span><span class="sxs-lookup"><span data-stu-id="39f6d-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="39f6d-106">Prima di eseguire la procedura descritta in questo argomento, è consigliabile leggere quanto segue:.</span><span class="sxs-lookup"><span data-stu-id="39f6d-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="39f6d-107">Per informazioni su come configurare la connettività ibrida, vedere Pianificare la connettività ibrida [tra Skype for Business Server e Skype for business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="39f6d-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="39f6d-108">Per ulteriori informazioni sulla pianificazione della distribuzione, vedere [Plan Phone System with on-premises Connectivity PSTN in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="39f6d-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="39f6d-109">Per ulteriori informazioni sul sistema telefonico, incluse le licenze e i piani, vedere [PSTN Calling plans for Skype for business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="39f6d-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="39f6d-110">Spostamento di utenti nel sistema telefonico con connettività PSTN locale</span><span class="sxs-lookup"><span data-stu-id="39f6d-110">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="39f6d-111">Prima di spostare gli utenti in Skype for business online, si consiglia di abilitare gli utenti in locale in Skype for Business Server o Lync Server 2013 e quindi spostarli online.</span><span class="sxs-lookup"><span data-stu-id="39f6d-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="39f6d-112">Per ulteriori informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e Skype for business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e la sezione Considerazioni speciali di [abilitare gli utenti per VoIP aziendale nei locali](enable-the-users-for-enterprise-voice-on-premises.md) (eseguiti mentre gli utenti sono ospitati in locale).</span><span class="sxs-lookup"><span data-stu-id="39f6d-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="39f6d-113">Tutti gli utenti devono essere creati in Active Directory in locale e sincronizzati con Microsoft 365 o Office 365 utilizzando la versione supportata di Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="39f6d-113">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="39f6d-114">Non è possibile abilitare gli utenti per il sistema telefonico in Office 365 che sono stati creati direttamente in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="39f6d-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="39f6d-115">Se si desidera abilitare il sistema telefonico con connettività PSTN locale per un utente che è stato creato in Azure AD, è necessario creare un nuovo account per tale utente nell'annuncio locale, configurare l'account locale e quindi sincronizzare l'account utilizzando una versione supportata dello strumento Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="39f6d-115">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="39f6d-116">L'abilitazione di un utente per il sistema telefonico con connettività PSTN locale e lo spostamento in Skype for business online richiede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="39f6d-116">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="39f6d-117">[Abilitare gli utenti per VoIP aziendale nei locali](enable-the-users-for-enterprise-voice-on-premises.md) (eseguiti mentre gli utenti sono ospitati in locale).</span><span class="sxs-lookup"><span data-stu-id="39f6d-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="39f6d-118">[Assegnare un criterio di routing vocale](assign-a-voice-routing-policy.md) (eseguito mentre gli utenti sono ospitati in locale).</span><span class="sxs-lookup"><span data-stu-id="39f6d-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="39f6d-119">[Sincronizzare gli utenti con il cloud e assegnare licenze](synchronize-users-to-the-cloud-and-assign-licenses.md) (eseguite con Office 365).</span><span class="sxs-lookup"><span data-stu-id="39f6d-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="39f6d-120">[Spostare gli utenti locali in Skype for business online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (eseguito utilizzando Windows PowerShell in locale, ma usando le credenziali di amministratore di Office 365).</span><span class="sxs-lookup"><span data-stu-id="39f6d-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="39f6d-121">[Abilitare gli utenti per la segreteria telefonica di VoIP aziendale e del sistema telefonico](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (eseguita tramite Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39f6d-121">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

