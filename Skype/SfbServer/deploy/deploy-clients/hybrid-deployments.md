---
title: Distribuzioni ibride di Skype room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente ibrido.
ms.openlocfilehash: f6364f7bb96ddf2b25aaaef2a341fce5b71372f5
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003496"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="d189a-103">Distribuzioni ibride di Skype room System</span><span class="sxs-lookup"><span data-stu-id="d189a-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="d189a-104">Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente ibrido.</span><span class="sxs-lookup"><span data-stu-id="d189a-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="d189a-105">Distribuzioni ibride</span><span class="sxs-lookup"><span data-stu-id="d189a-105">Hybrid deployments</span></span>

<span data-ttu-id="d189a-106">Seguire questa procedura se la topologia include Skype for Business Server e Exchange Online e si vuole ospitare la cassetta postale delle risorse di sistema room Skype in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d189a-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="d189a-107">Questa sezione copre anche uno scenario ibrido in cui sono stati distribuiti sia Exchange Online che Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d189a-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="d189a-108">Per scopi illustrativi, usiamo LyncSample.com per il dominio locale e LyncSample.ccstp.net per il dominio online.</span><span class="sxs-lookup"><span data-stu-id="d189a-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="d189a-109">Creare una cassetta postale delle risorse nell'interfaccia di amministrazione di Exchange (LyncSample.ccsctp.net) connettendosi a Exchange Online Management Shell come descritto in provisioning di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d189a-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="d189a-110">Puoi verificare la connettività OWA usando lrstest5@LyncSample.ccsctp.net per accedere.</span><span class="sxs-lookup"><span data-stu-id="d189a-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="d189a-111">Nell'interfaccia di amministrazione di Exchange di Office 365 aggiungere un indirizzo di posta elettronica lrstest5@LyncSample.com (dominio su Prem) e impostarlo come indirizzo di risposta.</span><span class="sxs-lookup"><span data-stu-id="d189a-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="d189a-112">Creare un lrstest5@LyncSample.com utente di Active Directory on-Prem, impostare l'indirizzo di posta elettronica su lrstest5@LyncSample.com e impostare l'indirizzo di destinazione su lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="d189a-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="d189a-113">Attiva la sincronizzazione della directory e, dopo il completamento della sincronizzazione, verifica che gli utenti si fondono in AAD e che non sia possibile modificare le proprietà nelle risorse del destinatario nell'interfaccia di amministrazione di Exchange di Office365.</span><span class="sxs-lookup"><span data-stu-id="d189a-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="d189a-114">Verificare la connettività OWA con lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="d189a-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="d189a-115">Prima hai verificato la connettività OWA usando il dominio online.</span><span class="sxs-lookup"><span data-stu-id="d189a-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="d189a-116">Dopo aver creato la cassetta postale, è possibile usare Set-CalendarProcessing in Exchange Online Management Shell per configurare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="d189a-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="d189a-117">Fare riferimento ai passaggi da 3 a 6 in distribuzioni singole in una foresta per maggiori dettagli.</span><span class="sxs-lookup"><span data-stu-id="d189a-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="d189a-118">Se si ha un ambiente ibrido con Exchange Server ed Exchange Online, accedere a Exchange Management Shell e abilitare-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-room.</span><span class="sxs-lookup"><span data-stu-id="d189a-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="d189a-119">Attiva quindi la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="d189a-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="d189a-120">Se si vuole ospitare la cassetta postale di sistema Skype room in Exchange Online, questi passaggi di Exchange Management Shell non sono necessari ed è possibile procedere con il passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="d189a-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="d189a-121">Abilitare l'account di sistema room Skype per Skype for business eseguendo il cmdlet seguente in Skype for Business Management Shell:</span><span class="sxs-lookup"><span data-stu-id="d189a-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="d189a-122">Se si ha Skype for business online invece di Skype for Business Server nello scenario precedente, dopo aver provisionato la cassetta postale delle risorse di Exchange, eseguire il provisioning di un account Skype for business come descritto in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="d189a-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

