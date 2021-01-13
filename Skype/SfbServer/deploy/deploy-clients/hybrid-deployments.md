---
title: Distribuzioni ibride di Skype room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente ibrido.
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805896"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="073e5-103">Distribuzioni ibride di Skype room System</span><span class="sxs-lookup"><span data-stu-id="073e5-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="073e5-104">Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente ibrido.</span><span class="sxs-lookup"><span data-stu-id="073e5-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="073e5-105">Ambienti ibridi</span><span class="sxs-lookup"><span data-stu-id="073e5-105">Hybrid deployments</span></span>

<span data-ttu-id="073e5-106">Attenersi alla seguente procedura se la topologia include Skype for Business Server e Exchange Online e si desidera ospitare la cassetta postale per le risorse di sistema Skype room su Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="073e5-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="073e5-107">In questa sezione viene inoltre illustrato uno scenario ibrido in cui sono distribuiti sia Exchange Online che Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="073e5-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="073e5-108">A scopo illustrativo, viene utilizzato LyncSample.com per il dominio locale e LyncSample.ccstp.net per il dominio online.</span><span class="sxs-lookup"><span data-stu-id="073e5-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="073e5-109">Creare una cassetta postale per le risorse nell'interfaccia di amministrazione di Exchange (LyncSample.ccsctp.net) mediante la connessione a Exchange Online Management Shell, come descritto in Exchange Online provisioning.</span><span class="sxs-lookup"><span data-stu-id="073e5-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="073e5-110">È possibile verificare la connettività OWA utilizzando lrstest5@LyncSample.ccsctp.net per eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="073e5-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="073e5-111">Nell'interfaccia di amministrazione di Exchange di Microsoft 365 o Office 365, aggiungere un indirizzo di posta elettronica lrstest5@LyncSample.com (su-Prem Domain) e impostarlo come indirizzo di risposta.</span><span class="sxs-lookup"><span data-stu-id="073e5-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="073e5-112">Creare un utente di Active Directory lrstest5@LyncSample.com, impostare l'indirizzo di posta elettronica su lrstest5@LyncSample.com e impostare l'indirizzo di destinazione su lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="073e5-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="073e5-113">Attivare la sincronizzazione della directory e, dopo aver completato la sincronizzazione, verificare che gli utenti si fondono in AAD e che non sia possibile modificare le proprietà nelle risorse del destinatario nell'interfaccia di amministrazione di Microsoft 365 o Office 365 Exchange.</span><span class="sxs-lookup"><span data-stu-id="073e5-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="073e5-114">Verificare la connettività OWA mediante lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="073e5-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="073e5-115">(In precedenza, è stata verificata la connettività OWA utilizzando il dominio online).</span><span class="sxs-lookup"><span data-stu-id="073e5-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="073e5-116">Dopo aver creato la cassetta postale, è possibile utilizzare Set-CalendarProcessing su Exchange Online Management Shell per configurare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="073e5-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="073e5-117">Per ulteriori informazioni, fare riferimento ai passaggi da 3 a 6 nelle distribuzioni on-Prem di una foresta singola.</span><span class="sxs-lookup"><span data-stu-id="073e5-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="073e5-118">Se si dispone di un ambiente ibrido con Exchange Server ed Exchange Online, accedere a Exchange Management Shell e Enable-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-room.</span><span class="sxs-lookup"><span data-stu-id="073e5-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="073e5-119">Attivare quindi la sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="073e5-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="073e5-120">Se si desidera ospitare la cassetta postale del sistema Skype room in Exchange Online, questi passaggi di Exchange Management Shell non sono necessari ed è possibile procedere con il passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="073e5-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="073e5-121">Abilitare l'account di sistema della sala Skype per Skype for business eseguendo il cmdlet seguente su Skype for Business Management Shell:</span><span class="sxs-lookup"><span data-stu-id="073e5-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="073e5-122">Se si ha Skype for business online invece di Skype for Business Server nello scenario sopra riportato, dopo aver provisionato la cassetta postale per le risorse di Exchange, eseguire il provisioning di un account Skype for business come descritto in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="073e5-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

