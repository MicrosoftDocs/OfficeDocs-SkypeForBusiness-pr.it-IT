---
title: Modificare un criterio PIN esistente in Skype for Business Server
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
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: 'Riepilogo: modificare un criterio PIN esistente in Skype for Business Server.'
ms.openlocfilehash: d97d535c8930c1b9155da4f8c35171f2b70692e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828356"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="15eb1-103">Modificare un criterio PIN esistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="15eb1-103">Modify an existing PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="15eb1-104">**Riepilogo:** Modificare un criterio PIN esistente in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="15eb1-104">**Summary:** Modify an existing PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="15eb1-105">Puoi usare la scheda **Criteri PIN** per fornire l'autenticazione pin agli utenti che si connettono a Skype for Business con telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="15eb1-105">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="15eb1-106">Per utilizzare l'autenticazione tramite PIN, verificare che sia selezionata l'opzione **Abilita autenticazione PIN** nelle impostazioni relative ai servizi Web.</span><span class="sxs-lookup"><span data-stu-id="15eb1-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="15eb1-107">Eseguire questa procedura per modificare un criterio PIN a livello di utente o di sito.</span><span class="sxs-lookup"><span data-stu-id="15eb1-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="15eb1-108">Per modificare un criterio PIN esistente</span><span class="sxs-lookup"><span data-stu-id="15eb1-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="15eb1-109">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="15eb1-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="15eb1-110">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="15eb1-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="15eb1-111">Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="15eb1-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="15eb1-112">Nella pagina **Criteri PIN** fare clic su criterio, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="15eb1-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="15eb1-p102">In **Modifica criterio PIN**, in **Lunghezza minima PIN**, digitare o selezionare la lunghezza minima che si desidera consentire per il PIN. La lunghezza minima predefinita è di cinque cifre.</span><span class="sxs-lookup"><span data-stu-id="15eb1-p102">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="15eb1-p103">Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **Specifica numero massimo di tentativi di accesso**. Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="15eb1-p103">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="15eb1-118">Se si seleziona la casella di controllo **Specifica numero massimo di tentativi di accesso**, in **Numero massimo di tentativi di accesso** digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="15eb1-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="15eb1-p104">Per impostare una scadenza per i PIN, selezionare la casella di controllo **Abilita scadenza PIN**. Se non si seleziona questa opzione, i PIN non scadranno mai, come da impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="15eb1-p104">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="15eb1-122">Se si seleziona la casella di controllo **Abilita scadenza PIN**, in **Scadenza PIN dopo (giorni)** digitare o selezionare il numero di giorni trascorsi i quali scadranno i PIN.</span><span class="sxs-lookup"><span data-stu-id="15eb1-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="15eb1-p105">In **Conteggio cronologia PIN** digitare il numero di PIN che deve creare un utente prima che possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.</span><span class="sxs-lookup"><span data-stu-id="15eb1-p105">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="15eb1-p106">Per consentire schemi comuni di cifre nei PIN, ad esempio numeri progressivi o gruppi ripetuti di numeri, selezionare la casella di controllo **Consenti formati comuni**. Se non si seleziona questa opzione, saranno consentiti solo schemi complessi di cifre, come da impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="15eb1-p106">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="15eb1-128">È consigliabile evitare di consentire i formati comuni.</span><span class="sxs-lookup"><span data-stu-id="15eb1-128">We recommend that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="15eb1-129">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="15eb1-129">Click **Commit**.</span></span>
    

