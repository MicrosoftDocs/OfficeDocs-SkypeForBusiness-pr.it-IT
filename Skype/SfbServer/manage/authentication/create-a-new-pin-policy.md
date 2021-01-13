---
title: Creare un nuovo criterio PIN in Skype for Business Server
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
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: 'Riepilogo: creare un nuovo criterio PIN in Skype for Business Server.'
ms.openlocfilehash: b0d1be74e509fbaddfc59250f4f5ce05a2021260
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828406"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="36dfa-103">Creare un nuovo criterio PIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="36dfa-103">Create a new PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="36dfa-104">**Riepilogo:** Creare un nuovo criterio PIN in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="36dfa-104">**Summary:** Create a new PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="36dfa-105">È possibile utilizzare la pagina **criteri PIN** per fornire l'autenticazione PIN (Personal Identification Number) agli utenti che si connettono a Skype for business con i telefoni IP.</span><span class="sxs-lookup"><span data-stu-id="36dfa-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="36dfa-106">Per utilizzare l'autenticazione tramite PIN, verificare che sia selezionata l'opzione **Abilita autenticazione PIN** nelle impostazioni relative ai servizi Web.</span><span class="sxs-lookup"><span data-stu-id="36dfa-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="36dfa-107">Per creare criteri PIN a livello di utente o di sito, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="36dfa-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="36dfa-108">Per creare criteri PIN a livello di utente o sito</span><span class="sxs-lookup"><span data-stu-id="36dfa-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="36dfa-109">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="36dfa-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="36dfa-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="36dfa-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="36dfa-111">Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="36dfa-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="36dfa-112">Nella pagina **Criteri PIN** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="36dfa-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="36dfa-p102">Per creare criteri a livello di utente fare clic su **Criteri utente**. In **Crea nuovi criteri PIN** digitare un nome descrittivo dei criteri in **Nome**.</span><span class="sxs-lookup"><span data-stu-id="36dfa-p102">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="36dfa-p103">Per creare criteri a livello di sito, fare clic su **Criteri sito**. Nel campo di ricerca **Seleziona un sito** digitare il nome del sito per cui si desidera creare i criteri, per intero o in parte. Fare clic sul sito desiderato nell'elenco dei siti risultante e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="36dfa-p103">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="36dfa-118">Nel campo **Descrizione** digitare una descrizione per i criteri PIN.</span><span class="sxs-lookup"><span data-stu-id="36dfa-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="36dfa-p104">Nel campo **Lunghezza minima PIN** digitare o selezionare la lunghezza minima che si desidera consentire per il PIN. La lunghezza minima predefinita è di cinque cifre.</span><span class="sxs-lookup"><span data-stu-id="36dfa-p104">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="36dfa-p105">Per poter specificare il numero massimo di tentativi di accesso prima che un utente venga bloccato, selezionare la casella di controllo **Specifica numero massimo di tentativi di accesso**. Se non si seleziona questa opzione, il numero massimo di tentativi consentiti viene determinato automaticamente in base alla lunghezza del PIN. Per impostazione predefinita, il numero massimo di tentativi viene determinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="36dfa-p105">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="36dfa-124">Se si seleziona la casella di controllo **Specifica numero massimo di tentativi di accesso**, in **Numero massimo di tentativi di accesso** digitare o selezionare il numero massimo di tentativi di accesso che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="36dfa-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="36dfa-p106">Per impostare una scadenza per i PIN, selezionare la casella di controllo **Abilita scadenza PIN**. Se non si seleziona questa opzione, i PIN non scadranno mai, come da impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="36dfa-p106">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="36dfa-128">Se si seleziona la casella di controllo **Abilita scadenza PIN**, in **Scadenza PIN dopo (giorni)** digitare o selezionare il numero di giorni trascorsi i quali scadranno i PIN.</span><span class="sxs-lookup"><span data-stu-id="36dfa-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="36dfa-p107">In **Conteggio cronologia PIN** digitare il numero di PIN che deve creare un utente prima che possa riutilizzare un PIN. Per impostazione predefinita, gli utenti possono riutilizzare i loro PIN.</span><span class="sxs-lookup"><span data-stu-id="36dfa-p107">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="36dfa-131">Per consentire modelli comuni di cifre nei pin, ad esempio "1234" e "8888", selezionare la casella di controllo **Consenti modelli comuni** .</span><span class="sxs-lookup"><span data-stu-id="36dfa-131">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box.</span></span> <span data-ttu-id="36dfa-132">Se non si seleziona questa opzione, saranno consentiti solo formati complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="36dfa-132">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="36dfa-133">Per impostazione predefinita, sono consentiti solo formati complessi di cifre.</span><span class="sxs-lookup"><span data-stu-id="36dfa-133">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="36dfa-134">È consigliabile evitare di consentire i formati comuni.</span><span class="sxs-lookup"><span data-stu-id="36dfa-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="36dfa-135">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="36dfa-135">Click **Commit**.</span></span>
    

