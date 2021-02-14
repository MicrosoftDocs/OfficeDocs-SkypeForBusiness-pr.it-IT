---
title: Visualizzare le informazioni sui criteri PIN in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Riepilogo: visualizzare le informazioni sui criteri PIN di un utente per Skype for Business Server.'
ms.openlocfilehash: 4c223d5736df7f5f8ee1dbee11401a9fef2237cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806526"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="e2664-103">Visualizzare le informazioni sui criteri PIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e2664-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="e2664-104">**Riepilogo:** Visualizzare le informazioni sui criteri PIN di un utente per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2664-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="e2664-105">È possibile utilizzare la scheda **Criteri PIN** per visualizzare l'autenticazione tramite PIN degli utenti che si connettono a Skype for Business con telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="e2664-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="e2664-106">Per utilizzare l'autenticazione tramite PIN, verificare che sia selezionata l'opzione **Abilita autenticazione PIN** nelle impostazioni relative ai servizi Web.</span><span class="sxs-lookup"><span data-stu-id="e2664-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="e2664-107">Effettuare la procedura seguente per modificare i criteri PIN a livello di utente o a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="e2664-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="e2664-108">Per visualizzare informazioni su un criterio PIN nel Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e2664-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="e2664-109">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2664-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="e2664-110">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2664-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e2664-111">Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="e2664-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="e2664-112">Nella pagina **Criteri PIN** scegliere i criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="e2664-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e2664-113">Visualizzazione dei criteri PIN tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="e2664-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e2664-114">È inoltre possibile visualizzare i criteri PIN utilizzando Windows PowerShell e il cmdlet Get-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="e2664-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="e2664-115">Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2664-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e2664-116">Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="e2664-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e2664-117">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e2664-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="e2664-118">Per visualizzare i criteri PIN</span><span class="sxs-lookup"><span data-stu-id="e2664-118">To view PIN policies</span></span>

<span data-ttu-id="e2664-119">Per visualizzare informazioni su tutti i criteri PIN, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="e2664-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy
  ```

<span data-ttu-id="e2664-120">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2664-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="e2664-121">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e2664-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e2664-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2664-122">See also</span></span>

[<span data-ttu-id="e2664-123">Creare un nuovo criterio PIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e2664-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
